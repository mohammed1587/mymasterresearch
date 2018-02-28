# Vers l'interopérabilité et la mise en œuvre des services Web RESTful: une approche guidée par les modèles

## 1. INTRODUCTION
les services REST ont gangé une grande réputation au détirment de SOAP à cause de son intéropérabilité, car un client, qui utilise une plate-forme spécifique, peut établir une communication avec un serveur qui utilise une plate-forme différente.
Mais, la fonctionnalité d'interopérabilité est juste au niveau de la communication, car les deux parties communiquent via la couche <abbr title="Hypertext Transfer Protocol">HTTP</abbr>, qui est la norme pour la communication Internet.<br>
Dans cet article, nous proposons une approche basée sur MDE pour résoudre le problème du manque d'interopérabilité dans le niveau Application de la technologie RESTful Web Services, à l'aide du WSSR métamodèle qui aide à implementer des interoperables RESTful Web Services sans avoir problème avec les spécification techniques des langages de programmation

## 2. CONTEXTE TECHNOLOGIQUE
### a. Services Web RESTful
l'architecture principale pour les services web est <abbr title="Remote Procedure Call/Simple Object Access Protocol">RPC/SOAP</abbr> est considérée comme architecture principale, car elle est standarisé du W3C pour l'échange d'informations entre les services Web. RPC/SOAP basée XML pour assurer l'intéroperabilité indépendamment de la technologie utilisée.
Cependant, l'architecture RPC / SOAP présente également des inconvénients. L'utilisation excessive d'enveloppes SOAP complique le trafic et entraîne l'ajout de calculs inutiles, de faibles performances et une faible évolutivité.

l'architecture REST a gagné de l'importance en raison en raison du fait que la communication se produit directement sur la couche HTTP, sans besoin d'encapsulation ou utilisation d'enveloppes, elle utilise les éléments de base du protocole, comme les verbes et les codes d'état.<br>
REST est visée pour les applications qui s'interesse par l'intéropérabilité au détriment d'un contrat formel.

### b. Implémentation du service RESTful
RESTful fournit une architecture Web multi-tier composée des tiers Client, Application et Données. L'indépendance de ces niveaux offre une flexibilité à ces applications Web dynamiques.

Le niveau Application fournit une couche Présentation, une couche métier et une couche Database Connector. La couche métier est considérée comme intérmediaire entre Présentation et Database Connector. Les données sont fournies à la couche Présentation dans la structure des objets.

La variété des langages de programmation empêche également la réutilisation de l'implémentation de la logique métier et réduit l'interopérabilité due aux différents formats et spécifications utilisés pour implémenter les services.

### c. Approche dirigée modèle
Model-Driven Engineering (MDE) est une approche de génie logiciel où le modèle est la figure centrale dans le développement des applications. Le code source est généré automatiquement depuis l'application des règles de transformation sur des modèles prédéfinis.

La figure 1 montre comment la MDA implique l'utilisation de langages de modélisation, les niveaux d'abstraction et l'indépendance de la plate-forme et des langages de programmation. 

+ Couche M0: Représente les objets du monde réel.
+ Couche M1: Modélisation de la couche précédente par un langage de modélisation.
+ Couche M2: Modélisation des règles d'utilisation est concepts utilisés dans M1 (metamodèles).
+ Couche M3: Modélisation et définition des règles d'utilisation et concepts utilisés dans M2 (meta-metamodèles).

![Niveaux d'Abstraction](https://i.imgur.com/IwffJnZ.png "Niveaux d'Abstraction pour la MDA")

En MDA, les transformations sont effectuées à partir de modèles sources vers des modèles cibles selon des mappages, qui sont créés par l'identification de correspondances sémantiques entre les éléments présents dans les deux modèles.

Le développement de modèles ne contient que la logique métier indépendante des détails technologiques (plate-forme, langages de programmation et architectures) rend le logiciel plus portable. Ces modèles de gestion ne peuvent être mappés à de nombreuses plateformes que par la création de nouvelles règles de transformation.

## 3. Services WEB RESTful dirigés modèle
Cet article, prèsente une approche pour le développement dirigé par le modèle dans le niveau d'application de service Web RESTful.
Le métamodèle WSSR peut être mappé à un langage de description sémantique, à un langage de description syntaxique et à un langage de mise en œuvre.Cet article discute la mise en œuvre.

Le métamodèle WSSR est responsable de la définition de la logique métier du service dans le niveau applicatif, de la plateforme d'abstraction (technologies, langages de programmation, etc.). Ensuite, un métamodèle de technologie spécifique doit être défini comme la plate-forme cible choisie par le programmeur pour implémenter le service. De plus, l'identification des correspondances, appelée opération de mappage, sera définie entre les deux métamodèles.

Les règles de transformation, écrites dans un langage de transformation, définissent quels éléments d'un métamodèle source seront transformés en quels éléments du métamodèle cible.

Les règles de transformation sont appliquées au niveau du modèle, c'est-à-dire dans les instances de services. Un modèle source doit être conforme au WSSR et le modèle cible sera généré par le moteur de transformation, et il se conforme à son métamodèle cible.

![Approach](https://i.imgur.com/es2pK8a.png "Diagramme d'activité de l'approche")
![WSSR](https://i.imgur.com/ysucKZ6.png "WSSR")