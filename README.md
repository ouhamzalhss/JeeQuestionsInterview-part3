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

- 9 .	Les niveaux de cache JPA : L1 (activé par défaut), L2 (cache hibernate) parmi les implémentations on trouve ehcache.

- 10 .	Transaction : Traiter un ensemble d’opérations come une seule pour avoir des données cohérentes,

- 11 .	Quelle est la différence entre load() et get()?
Lorsque l'objet n'est disponible ni dans le cache ni dans la base de données,
  *  Load() : lève une exception.
  *  Get() : renvoie null
