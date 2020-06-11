### Cas 2: Modifier la liste des rôles d’un utilisateur pour un projet

#### Nom

Modifier la liste des rôles d’un utilisateur pour un projet

#### But

Modifier la liste des rôles d’un utilisateur pour un projet

#### Acteur principal ou acteurs principaux

* Gestionnaire de projet

#### Parties prenantes et intérêts

#### Sommaire

* Un gestionnaire de projet, demande et obtient la liste des utilisateurs du système trié selon les rôles associés à un projet en spécifiant le projet. Par la suite le gestionnaire de projet, demande, obtient et remplit un formulaire de modification de la liste des rôles d’un utilisateur par rapport à son projet en spécifiant le projet et l’utilisateur. Le système enregistre la nouvelle liste de rôle de l’utilisateur pour le projet ».

Préconditions et garanties de succès (postconditions)
Préconditions :

* Le système fonctionne
* Le gestionnaire de projet est inscrit dans le système
* Le gestionnaire de projet est authentifié
* Le gestionnaire de projet détient le rôle « gestionnaire de projet » pour chaque projet spécifié par le rôle
-	L’utilisateur spécifié par un rôle existe dans le système
-	L’utilisateur spécifié par un rôle n’est pas l’utilisateur originel
-	L’utilisateur spécifié par un rôle n’est pas l’utilisateur anonyme

Postconditions :
* L’utilisateur spécifié détient l’ensemble des rôles-projet dans le système tel que spécifié par le gestionnaire de projet.

#### Déroulement nominal

|  |  |
| --- | --- |
| 1.	Le gestionnaire de projet déclenche le cas d’utilisation |  |
| 2.	Le gestionnaire de projet indique au système qu’il souhaite la liste des utilisateurs du système trié selon la liste des rôles qu’ils détiennent par rapport à un projet spécifié |  |
|  | 3.	Le système vérifie que le projet spécifié existe |
|  | 4.	Le système vérifie que gestionnaire de projet détient le rôle « gestionnaire de projet » dans le système, pour le projet spécifié |
|  | 5.	Le système envoie la liste des utilisateurs du système trié selon la liste des rôles qu’ils détiennent par rapport au projet spécifié |
| 6.	Le gestionnaire de projet demande un formulaire de modification de la liste des rôles d’un utilisateur par rapport à son projet en spécifiant le projet et l’utilisateur |  |
|  | 7.	Le système vérifie que le projet spécifié existe |
|  | 8.	Le système vérifie que gestionnaire de projet détient le rôle « gestionnaire de projet » dans le système, pour le projet spécifié |
|  | 9.	Le système vérifie que l’utilisateur spécifié existe dans le système |
|  | 10.	Le système vérifie que l’utilisateur spécifié n’est pas l’utilisateur originel ou l’utilisateur anonyme |
|  | 11.	Le système envoie un formulaire de modification de la liste des rôles détenus par l’utilisateur spécifié pour le projet spécifié |
| 12.	Le gestionnaire de projet remplit le formulaire et l’envoie ensuite au système |  |
|  | 13.	Le système vérifie que chaque rôle spécifie un projet existant pour lequel le gestionnaire de projet détient le rôle « gestionnaire de projet » |
|  | 14.	Le système vérifie que chaque rôle spécifie un utilisateur existant dans le système |
|  | 15.	Le système vérifie que chaque rôle ne spécifie pas l’utilisateur originel ou l’utilisateur anonyme |
|  | 16.	Le système enregistre la nouvelle liste de rôles de l’utilisateur spécifié par rapport au projet spécifié |
|  | 17.	Le système envoie une représentation de cette liste au gestionnaire de projet |

#### Exceptions
* Le gestionnaire de projet n’est pas authentifié
* Le gestionnaire de projet ne détient pas le rôle « gestionnaire de projet » pour le projet spécifié
* L’utilisateur spécifié n’existe pas dans le système
* L’utilisateur spécifié est l’utilisateur originel
* L’utilisateur spécifié est l’utilisateur anonyme

#### Exigences spécifiques autres que fonctionnelles
aucune

#### diagramme de séquence complet

[![uncached image](http://www.plantuml.com/plantuml/proxy?cache=no&src=https://raw.githubusercontent.com/pierrelucueisd/testUml/master/usercases/uc2/sequence.md)](sequence.md "voir le diagramme")

[Retour](../../readme.md)