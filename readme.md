## Cas d’utilisation
<br>
### Cas d'utilisation

* [Cas 1: Inscrire un utilisateur](usercases/usercase1.md)
*
<br>

#### Cas 1: Inscrire un utilisateur
<br>

#### Nom
Inscrire un utilisateur

#### But
Permettre à une personne d’utiliser le système

#### Acteur principal ou acteurs principaux

* Préposé à l’inscription

#### Parties prenantes et intérêts

#### Sommaire

* Un Préposé à l’inscription du système demande, obtient la liste des utilisateurs du système. Par la suite il demande, obtient, remplit et envoie un formulaire de création d’utilisateur qui spécifie les informations de connexion de l’utilisateur. Le système enregistre le nouvel utilisateur ».

Préconditions et garanties de succès (postconditions)
Préconditions :

* Le système fonctionne
* Le Préposé à l’inscription est inscrit dans le système
* Le Préposé à l’inscription est authentifié
* Le Préposé à l’inscription détient le rôle « Le Préposé à l’inscription du système »
Postconditions :
* Un utilisateur est enregistré dans le système.

#### Déroulement nominal
<br>

|       |       |
| ---   | --- |
| 1.	Le Préposé à l’inscription déclenche le cas d’utilisation |  |
| 2.	Le Préposé à l’inscription indique au système<br>qu’il souhaite la liste des utilisateurs |  |
|  | 3.	Le système vérifie que Le Préposé à l’inscription<br>détient le rôle « Préposé à l’inscription » dans le système |
|  | 4.	Le système envoie la liste des utilisateurs au préposé à l’inscription |
| 5.	Le Préposé à l’inscription indique au système<br>qu’il souhaite créer un utilisateur |  |
|  | 6.	Le système vérifie que Le Préposé à l’inscription<br>du détient le rôle « Préposé à l’inscription » dans le système |
|  | 7.	Le système envoie un formulaire de création d’utilisateur à l’employé |
| 8.	Le Préposé à l’inscription remplit le formulaire en spécifiant<br>le nom de l’utilisateur, ses informations de connexion<br>et envoie ensuite le formulaire au système |  |
|  | 9.	Le système vérifie que Le Préposé à l’inscription<br>du détient le rôle « Préposé à l’inscription » dans le système |
|  | 10.	Le système vérifie que l’utilisateur détient un identifiant de connexion unique |
|  | 11.	Le système enregistre le nouvel utilisateur |
|  | 12.	Le système envoie une représentation du nouvel utilisateur |

[![uncached image](http://www.plantuml.com/plantuml/proxy?cache=no&src=https://raw.githubusercontent.com/pierrelucueisd/testUml/master/diagram2.md)](diagram2.md "voir le diagramme")