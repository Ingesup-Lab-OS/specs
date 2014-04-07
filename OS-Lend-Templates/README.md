#### Specs OS-Lend-Templates ####

Specifications de l'application de location de VM pour développement.

## Création d'une stack via Heat ##

![decomposition](stack_hierarchy.jpg)

## But des templates ##

Créer une infrastructure de développement entièrement automatisée.

## Templates Heat ##

Le but des templates Heat est de fournir l'ensemble des ressources virtualisées
nécessaires à la production d'un environnement de développement.
Elles sont aussi responsables de fournir les fichiers cloud_config responsables
de la première passe de configuration logicielle.

## Fichiers cloud_config ##

Ils ne disposeront que de peu d'intelligence, afin de démarrer le processus de
configuration. Ils pourront être responsables des opérations de configuration
de bas niveau, tel que le formatage d'un volume.
Leur opération finale sera de lancer le manifest puppet responsable de la
configuration de l'instance.

## Les manifests Puppet ##

Les manifests puppet sont responsables de la configuration finale de l'instance
(installation des services, configuration, etc). Ils seront récupérés
directement depuis github et lancé en mode standalone. Le fonctionnement sera
donc masterless, comme les instances sont destinées à faire du cloud, la
conservation des états n'est pas important.

## Github ##

Tous les fichiers de templates (manifests et heat) sont stockés via github pour
permettre un versionnement et une gestion centralisée des configurations.
