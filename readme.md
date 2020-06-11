

![uncached image](http://www.plantuml.com/plantuml/proxy?cache=no&src=https://github.com/pierrelucueisd/testUml/blob/master/diagram.txt)
aaaaaaaaaaa


![Diagrame de séquence   Cas 1  Inscrire un utilisateur](https://www.plantuml.com/plantuml/png/xLPDRzf04BtxLumucOYWf4TKeXZZA6umM63AeVIms5jOrQpT_L3BJyez_u0_rbql43Qu2Jta5YHaUT-ycNblnh9lkK1Co7Nk229o37s2bWojCMGO-FRnbyGqnHsOK_0HX-iEX9IdZ30Cae8K92SS2IoPuvGg3qb9YQY01g9BcIC6qx01YkVPQ5fGmRPFkU9Li6_3w-sZ8DX0aGsLc772XMwgWcCBxlSS3-3o1i07zUl04WilpwTSiLn_XGZ5aEPOtpSLgg_VlZk-eKI6GdZCS5bmx0sCr5AGWjQmUqMHOqIToD1ZGqyBIOKEcH6nUi0RZsPZ5UVEwLpio2reJEI2fu8iTEe8KRHKQkTKPoLKEB79sEzL6IV18F0Jy4VJOU9UD27ij-1kF8ggza7gqOJ3OJ26BwDm2BgO9mGZ2wcJWwuBeo6mjWuFC-Y2R9DCisRtmJY0JVidtgXJrPoZAbwgoZif3FEoe1nN_QZZlK6gmyYSx5pUEs4RUUozLZPGS_kiRszUMFPAOAqJ5y_op-luHUNdney0tm2U0UwJ93vaWqzNLp1wQEttvMJ5ue9N8xyhsBeQjBqiPh37GHyhzsuhPytYn7SxoSb8tbe0Ys2lGRc3QkRVsjbsM8M9G4BoZoLudoKWV4g9Uc_fkdv1AVwZ-WdfZy8zZE4C6_MVglTWPQ3cjENkv7_ygbomJPkji7vvjlS5eDi5A_-f6p8NRtgngFNYi9MMz4MjzDTZRQtXS1AC4tL9HaQP5khk9Qa71N7-ks1PKm5VlS4qc81hYMmPpUK-xXpHnstN2__tytiDFiFgGoLpRZ7DrEVENm00 "Diagrame de séquence   Cas 1  Inscrire un utilisateur")
```plantuml
@startuml
title Diagrame de séquence: \n Cas 1: Inscrire un utilisateur

participant "angular UI" as A
participant "contrôleur" as C
participant "métier" as M
participant "persistence" as P
participant DB
A  ->  C    : getAllUsers(Chaine cleUser) : User[]
C  ->  M    : isPreposeALInscription(Chaine cleUser) : Boolean
M  ->  P    : countUserWithKeyAndRole(\n\tcleUser, "SubsctibtionManager"\n) : int
P  ->  DB   : SELECT COUNT(*) ID, FROM User u \n INNER JOIN RoleAttribution \n\t ON r.UserId = u.id \n WHERE y.key = cle
DB --> P    : response
P  --> M    : int
M  --> C    : Boolean
C  ->  M    : getAllUsers() : List<User>
M  ->  P    : getAllUsers() : List<User>
P  ->  DB   : SELECT * FROM User
DB --> P    : response
P  --> M    : List<User>
M  --> C    : List<User>
C  --> A    : HTTP response 200 OK, User[]
A  ->  C    : getPostUserForm(\n\tChaine cleUser\n) : PostUserForm
C  ->  M    : isPreposeALInscription(Chaine cleUser) : Boolean
M  ->  P    : countUserWithKeyAndRole(\n\tcleUser, "SubsctibtionManager"\n) : int
P  ->  DB   : SELECT COUNT(*) ID, FROM User u \n INNER JOIN RoleAttribution \n\t ON r.UserId = u.id \n WHERE y.key = cle
DB --> P    : response
P  --> M    : int
M  --> C    : Boolean
C  ->  M    : getPostUserForm() : PostUserForm
M  --> C    : PostUserForm
C  --> A    : HTTP response 200 OK, PostUserForm
A  ->  C    : postUser(\n\tChaine cleUser, User user\n) : Status
C  ->  M    : isPreposeALInscription(Chaine cleUser) : Boolean
M  ->  P    : countUserWithKeyAndRole(\n\tcleUser, "SubsctibtionManager"\n) : int
P  ->  DB   : SELECT COUNT(*) ID, FROM User u \n INNER JOIN RoleAttribution \n\t ON r.UserId = u.id \n WHERE y.key = cle
DB --> P    : response
P  --> M    : int
M  --> C    : Boolean
C  ->  M    : isUniqueUserConnexionInfo(User user) : Boolean
M  ->  P    : countUserUsername(\n\tuser.username\n) : int
P  ->  DB   : SELECT COUNT(*) ID, \n\t FROM User u \nWhere u.Username == user.username
DB --> P    : result
P  --> M    : int
M  --> C    : boolean
C  ->  M    : postUser(User user) : boolean
M  ->  P    : postUser(User user) : boolean
P  ->  DB   : INSERT INTO User \n\t(Username, Password) \nVALUES (user.username, user.password)
DB --> P    : result
P  --> M    : boolean
M  --> C    : boolean
C  --> A    : HTTP response 201 Created
@enduml
```

![readme-1](https://www.plantuml.com/plantuml/png/SoWkIImgAStDuN9KqBLJSE9oICrB0N81 "readme-1")
```plantuml
@startuml
A -> B
@enduml
```
