``` plantuml
@startuml
title Diagrame de séquence: \n Cas 2: Modifier la liste des rôles d’un utilisateur pour un projet

participant "Angular UI"    as A
participant "Contrôleur"    as C
participant "Métier"        as M
participant "persistance"   as P

A ->  C     : getUsersOfProjectWithRole(\n\t Chaine cleUser, Projet projet \n) : Map(User => ProjetcRole[])
C ->  M     : isProjectExist(Projet projet) : Boolean
M ->  P     : countProjectWithId(int) : int
P --> M     : int
M --> C     : boolean
C ->  M     : isProjectManagerOf(Chaine cleUser, Int projet.id) : Boolean
M ->  P     : countRoleAttributionFromCleAndPid(Chaine cleUser, Int projet.id) : int
P --> M     : int
M --> C     : boolean
C ->  M     : getUsersOfProjectWithRole(\n\t projet.pid \n) : Map(User => ProjetcRole[])
M ->  P     : selectUserRoleFromPidGoupedByUserId(\n\tprojet.id\n) : User+RoleAttribution
P --> M     : int
M --> C     : Map(User => ProjetcRole[])
C --> A     : HTTP response 200 OK, Map(User => ProjetcRole[])
A ->  C     : getPutUserProjectRolesForm(\n\t Chaine cleUser, \n\t User user, \n\t Projet projet \n) : PutUserProjectRolesForm
C ->  C     : isProjectExist(Projet projet) : Boolean
C ->  C     : isProjectManagerOf(Chaine cleUser, Projet projet) : Boolean
C ->  M     : isUserExist(User user) : Boolean
M ->  P     : countUserWithId(user.id) : int
P --> M     : int
M --> C     : boolean
C ->  M     : isUserNotOriginalOrAnonymous(user.id) : Boolean
M --> C     : boolean
C ->  M     : getPutUserProjectRolesForm(\n\t User user, \n\t Projet projet \n) : PutUserProjectRolesForm
M ->  P     : selectRoleAttributionFromUIDAndPID(user.id, projet.id) : RoleAttribution[]
P --> M     : RoleAttribution[]
M --> C     : PutUserProjectRolesForm
A ->  C     : PutUserProjectRoles(\n\t Chaine cleUser, \n\t ProjectUserRole selectedRoles, \n\t Projet projet \n) : Status
C ->  M     : isValideProjectUserRoles(\n\t Chaine cleUser, ProjectUserRole selectedRoles \n) : Boolean
M ->  P     : countRoleWithName(Chaine selectedRole.name) : int
P --> M     : int
M --> C     : boolean
C ->  M     : PutUserProjectRoles(\n\t ProjectUserRole selectedRoles \n ) : Status
M --> P     : deleteRoleAttributionFromUidAndPid(user.id, projet.id) : status
P --> M     : status
M --> P     : insertRoleAttibution(Projet projet, Chaine rolename, User user): Status
P --> M     : status
M --> C     : status
C --> A     : HTTP response 201 Created
@enduml
```