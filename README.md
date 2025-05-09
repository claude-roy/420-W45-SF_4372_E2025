# Installation des serveurs et des services - 420-W45-SF
## UBR4372, été 2025

### CALENDRIER

Ce calendrier est donné à titre indicatif et peut être modifié en fonction des circonstances. Dans le cas des examens, les étudiants seront toujours avisés dans un délai raisonnable.  

|Cours	|Date cours |Contenu|Évaluations|  Remise exercice   |
|----------:|:-------------:|----------------|:------:|------:|
|1|	 mai |Présentation du plan de cours |||
| || Présentation des concepts de bases||
| ||Exercice 1 : Installation Ubuntu |[Ex1](Exercices/)| 14 nov|
|2|	14 nov|Installation d'un serveur Linux avec LVM et configuration réseau	 |[Ex2](Exercices/Exercice02_InstallationServeur.md) et [Ex3](Exercices/)| 20 nov|
|3| 21 nov|Accès distant, les protocoles SSH/SCP et Git accès distant |[Ex4](Exercices/Exercice04_PriseEnMainSrv.md)| 22 nov.
|4|	22 nov|Admin système les droits et accès |[Ex5](Exercices/Exercice05_AdminSysLinux.md)|26 nov.
|5|	26 nov|Admin système Noyau, processus et logs |[Ex6](Exercices/Exercice06_InstallationEnvTest.md)|27 nov. |
|6|	28 nov|**Travail pratique 1 : Installation d'un serveur** |**[Tp1](TPs/TravailPratique01.md)**|3 déc, 12h30|
|7|	3 déc|Docker	 |[Ex7](Exercices/Exercice07_PriseEnMainConteneur.md)|6 déc, 12h30|
|8|	6 déc|Docker file	 |[Ex8](Exercices/Exercice08_DockerImage.md) |10 déc, 8h30|
|9|	10 déc|Docker Réseau et volume	 |[Ex9](Exercices/Exercice09_DockerRzEtVolume.md) |17 déc, 12h30|
|10| 17 déc|**Travail pratique 2 : Docker**	 |**[Tp2](TPs/TravailPratique02.md)**||
|11| 19 déc |**Travail pratique 2 : Docker**	 | |20 décembre fin de journée|
|12|7 jan|Docker compose |[Ex10](Exercices/Exercice10_DockerCompose.md)|14 jan., 12h30 |
|13|14 jan|	Présentation du service de résolution de nom DNS	|[Ex11](Exercices/Exercice11_DNS.md)|16 janv, 12h30 |
|14|16 jan| Révision	 |||
|15|23 jan|	**Examen partiel** |**Examen 1**|
|16|28 jan|	Apache, installation, config de base	 |[Ex12](Exercices/Exercice12_Apache.md)|3 fév., 12h30 |
|17|3 fev|	Apache, modules et SSL	 |[Ex13](Exercices/Exercice13_Apache_modules-SSL.md)|6 fév., 12h30 |
|18|6 fev|	Apache, installation d’un site Web et site virtuel	 |[Ex14](Exercices/Exercice14_Apache_SiteVirtuel.md)|11 fév., 8h30 |
|19|11 fev|	Nginx, installation, config de base	|[Ex15](Exercices/Exercice15_nginx.md)|13 fév., 12h30|
|20|13 fev|	Nginx, configurations avancées (reverse proxy et load balancer) |[Ex16](Exercices/Exercice16_NginX-equilibreur-repartiteur-de-charge.md)|20 fév., 12h30|	
|21|20 fev| TP3- Mise en place d’un service Web (Docker Compose)|[TP3](TPs/TravailPratique03.md)||
|22|27 fev|	TP3	|[TP3](TPs/TravailPratique03.md)|	|
|23|3 mar| TP3	|[TP3](TPs/TravailPratique03.md)|3 mars fin de journée|
|24|6 mar| Automatisation et Ansible|[Ex17](Exercices/Exercice17_AnsibleMiseEnPlace.md)|13 mars 12h30|
|25|13 mar|Automatisation mode AdHoc|[Ex18](Exercices/Exercice18_AnsibleModeAdHoc.md)|20 mars 12h30|
|26|20 mar|	Automatisation PlayBook	|[Ex19](Exercices/Exercice19_AnsiblePlaybook.md)|24 mars 12h30|
|27|24 mar|	 TP4 automatisation	|[TP4](TPs/TravailPratique04.md)||
|28|25 mar|	 TP4 automatisation	|[TP4](TPs/TravailPratique04.md)|26 mars fin journée|
|29|27 mar|	**Évaluation finale à caractère synthèse**|[Examen final](EFCS/EFCSA2024_4364.md)|||
|30|3 avr|	**Évaluation finale à caractère synthèse** |[Examen final](EFCS/EFCSA2024_4364.md)|3 avril 15h30|

### Récapitulatif de la pondération des évaluations sommatives

|Évaluation | Pondération (en %) |
|:-------------|:------:|
|TP1 – Déploiement d’un système d’exploitation	| 10|
|TP2 – Docker	|10|
|TP3 - Mise en place d’un service Web (Docker compose)	| 10|
|TP4 – Automatisation	| 10|
|Examen partiel	| 20|
|Évaluation finale à caractère synthèse	 |30|
|Réalisation des exercices	|10|
