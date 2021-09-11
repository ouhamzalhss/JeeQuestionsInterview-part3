## <samp>Les Questions pour un entretien profile JAVA/JEE!</samp>

#### Partie 4: Persistence de données ( JDBC, JPA, Hibernate, Spring data)

- 1 . JDBC (Java DataBase Connectivity) est une API fournie avec Java permettant de développer des applications capables de se connecter à des bases de données relationnelles (SGBDR).

- 2 .	JPA : Java persistence Api : C’est une spécification pour le mapping objet relationnel ORM, vient pour standariser différents framework ORM comme Hibernate, ExlepseLink.

- 3 .	Hibernate : le framework de mapping objet relationnel le plus populaire, c’est l’implémentation de JPA.

- 4 .	Avantages d'ORM :
  *  Code généré automatiquement
  *  Cache, performance
  *  HQL ou JPQL
  *  Indépendant de la base de données.

- 5 . Qu'est-ce que HQL ?
Hibernate Query Language (HQL) est utilisé comme une extension de SQL. HQL est la représentation orientée objet du langage de requête, c'est-à-dire qu'au lieu d'utiliser le nom de la table, nous utilisons le nom de la classe qui rend ce langage indépendant de toute base de données.

- 6 .	Spring data : Module de Spring, contient les interfaces et implémentations génériques qui utilisent JPA pour faire le mapping Objet Relationnel.

- 7 .	Quelques Annotations JPA: @Entity, @Id, @GeneratedValue, @Table, @Column, @Inheritance, @JoinColumn, @ManyToMany, @Transient

- 8 . Quelques contraintes sur une entité JPA : Une classe d'entité doit remplir les conditions suivantes :
  *  La classe doit avoir un constructeur sans parametres.
  *  La classe ne peut pas être "final".
  *  La classe doit être annotée avec l'annotation @Entity et @Id.
  
- 9 .	Cycle de vie d'une entité JPA : 
  *  Transient, [new()]
  *  Persistent, [save(), persist(), saveOrUpdate(), load(), get() ]
  *  Detached, [update(), merge(), saveOrUpdate()]

- 10 . Quelle est la différence entre persist, save, merge and update? 
  *  Vous pouvez utiliser les méthodes persist, save pour stocker une nouvelle entité (Transient) dans la base de données.
  *  Et merge, update pour enregistrer les modifications d'une entité détachée (detached, Removed) dans la base de données.

- 11 .	Quelle est la différence entre load() et get()?
Lorsque l'objet n'est disponible ni dans le cache ni dans la base de données,
  *  load() : lève une exception (ObjectNotFoundException).
  *  get() : renvoie null.
  
- 12 .	Différentes stratégies de Mapping d’héritage : @Inheritance(strategy= SINGLE_TABLE)
  *  Une table par hiérarchie : SINGLE_TABLE  (plus utilisé) 
 		 @DiscriminatorColumn ajouter cette annotation dans la class mere, et @DiscriminatorValue dans les class filles.
  *  Une table pour chaque classe concrète : TABLE_PER_CLASS
  *  Une table pour la classe parente et une table pour chaque classe fille: JOINED_TABLE

- 13 .	le fetch par défaut : JPA 2.0 +
  *  @OneToMany: LAZY
  *  @ManyToMany: LAZY
  *  @ManyToOne: EAGER
  *  @OneToOne: EAGER

- 14 .	Les niveaux de cache JPA : 
  *  L1 est activé par défaut, et réside dans l'objet de session d'hibernation. 
  *  L2 (cache hibernate) Ceci n'est pas activé par défaut. Il doit être configuré explicitement, et réside dans l'objet SessionFactory et de ce fait, les données sont accessibles par l'ensemble de l'application. parmi les implémentations on trouve ehcache (Easy Hibernate cache).

- 15 .	Transaction : Traiter un ensemble d’opérations comme une seule pour avoir des données cohérentes,

- 16 .	Qu'est-ce qu'une session Hibernate ?
Une session est un objet qui maintient la connexion entre l'application objet Java et la base de données. Session a également des méthodes pour manipuler les données de la base de données à l'aide de méthodes telles que persist(), load(), get(), update(), delete(), etc.

- 17 .	Qu'est-ce qu'une SessionFactory ?
Est une classe qui permet de créer une instance de Session, afin d'établir la connexion à la base de données. Comme bonne pratique, l'application a généralement une seule instance de SessionFactory. 

- 18 . la différence entre les méthodes getCurrentSession et openSession ?
  *  getCurrentSession()	: Cette méthode renvoie la session liée au contexte. Cet objet de session est fermé une fois la SessionFactory est fermée.
  *  openSession() : Cette méthode ouvre toujours une nouvelle session. C'est le développeur qui va fermer cet objet une fois toutes les opérations de base de données terminées.

- 19 . Qu'est-ce qu'un Entitymanager ?
EntityManager est une API qui gère le cycle de vie des instances d'entité.

- 20 . Quelle est la différence entre JPA et JDO ?
JPA et Java Data Objects (JDO) sont deux spécifications permettant de stocker des objets Java dans des bases de données. Si JPA se concentre uniquement sur les bases de données relationnelles, alors JDO est une spécification plus générale qui décrit l'ORM pour toutes les bases et référentiels possibles.
