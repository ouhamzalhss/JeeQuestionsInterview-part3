## <samp>Les Questions pour un entretien profile JAVA/JEE!</samp>

#### Partie 4: Persistence de données( JPA, Hibernate, Spring data)

- 1 .	JPA : Java persistence Api : C’est une spécification pour le mapping objet relationnel, vient pour standariser différents framework ORM comme Hibernate, ExlepseLink.

- 2 .	Hibernate : le framework de mapping objet relationnel le plus populaire, c’est l’implémentation de JPA.

- 3 .	Avantages dORM :
  *  Code généré automatiquement
  *  Cache, performance
  *  HQL
  *  Le code généré par ORM ne dépend pas du fournisseur. Ceci afin d'augmenter la portabilité de l'application.

- 4 .	Spring data : Module de Spring, contient les interfaces et implémentations génériques qui utilisent JPA pour faire le mapping Objet Relationnel.

- 5 .	Fetch Eager : cas de relation (ManyToMany ou OneToMany) il faut toujours initialiser les arrayList avec le mot clé : new 

- 6 .	Différentes stratégies de Mapping d’héritage : @Inheritance(strategy= SINGLE_TABLE)
  *  Une table par hiérarchie : SINGLE_TABLE  (plus utilisé) 
 		 @DiscriminatorColumn ajouter cette annotation dans la class mere, et @DiscriminatorValue dans les class filles.
  *  Une table pour chaque classe concrète : TABLE_PER_CLASS
  *  Une table pour la classe parente et une table pour chaque classe fille: JOINED_TABLE

- 7 .	Default fetch type : JPA 2.0 +
  *  OneToMany: LAZY
  *  ManyToMany: LAZY
  *  ManyToOne: EAGER
  *  OneToOne: EAGER

- 8 .	Cycle de vie dune entité JPA : New, Managed, Detached, Removed.

- 9 .	Les niveaux de cache JPA : 
  *  L1 est activé par défaut, et réside dans l'objet de session d'hibernation. 
  *  L2 (cache hibernate) Ceci n'est pas activé par défaut. Il doit être configuré explicitement, Le cache de deuxième niveau réside dans l'objet SessionFactory et de ce fait, les données sont accessibles par l'ensemble de l'application. parmi les implémentations on trouve ehcache (Easy Hibernate cache).

- 10 .	Transaction : Traiter un ensemble d’opérations come une seule pour avoir des données cohérentes,

- 11 .	Quelle est la différence entre load() et get()?
Lorsque l'objet n'est disponible ni dans le cache ni dans la base de données,
  *  Load() : lève une exception.
  *  Get() : renvoie null

- 12 .	Qu'est-ce qu'une session Hibernate ?
Une session est un objet qui maintient la connexion entre l'application objet Java et la base de données. Session a également des méthodes pour manipuler les données de la base de données à l'aide de méthodes telles que persist(), load(), get(), update(), delete(), etc.

- 13 .	Qu'est-ce qu'une SessionFactory ?
Est une classe qui permet de créer une instance de Session en fonction des paramètres de configuration afin d'établir la connexion à la base de données.
Comme bonne pratique, l'application a généralement une seule instance de SessionFactory. 

- 14 . la différence entre les méthodes getCurrentSession et openSession ?
  *  getCurrentSession()	: Cette méthode renvoie la session liée au contexte. Cet objet de session est fermé une fois la session factory fermée.
  *  openSession() : Cette méthode ouvre toujours une nouvelle session.C'est le développeur qui va fermer cet objet une fois toutes les opérations de base de données terminées.

- 15 . Qu'est-ce que HQL ?
Hibernate Query Language (HQL) est utilisé comme une extension de SQL. Il est très simple, efficace et très flexible pour effectuer des opérations complexes sur des bases de données relationnelles sans écrire de requêtes compliquées. HQL est la représentation orientée objet du langage de requête, c'est-à-dire qu'au lieu d'utiliser le nom de la table, nous utilisons le nom de la classe qui rend ce langage indépendant de toute base de données.
