# Aide-mémoire sur la ligne de commande VMware ESXi

L'utilisation de la ligne de commande offre plusieurs avantages pour un ingénieur, notamment :

1. **Automatisation** : La ligne de commande permet d'automatiser des tâches répétitives en écrivant des scripts ou en utilisant des outils de ligne de commande. Cela permet de gagner du temps et d'augmenter l'efficacité des processus de développement et de gestion.

2. **Contrôle précis** : La ligne de commande offre un contrôle précis sur le système d'exploitation et les logiciels. Les ingénieurs peuvent effectuer des actions spécifiques avec des options et des paramètres précis, ce qui peut être difficile ou impossible à réaliser via des interfaces graphiques.

3. **Flexibilité** : La ligne de commande est souvent plus flexible que les interfaces graphiques, car elle permet aux ingénieurs d'accéder à toutes les fonctionnalités d'un système ou d'un logiciel, y compris celles qui ne sont pas accessibles via une interface graphique.

4. **Efficacité des ressources** : Les interfaces en ligne de commande consomment généralement moins de ressources système que les interfaces graphiques, ce qui est important lorsque les ressources sont limitées, comme dans les environnements de serveur.

5. **Déploiement et gestion à distance** : La ligne de commande est souvent utilisée pour le déploiement et la gestion à distance des systèmes et des applications. Les ingénieurs peuvent se connecter à des serveurs à distance et effectuer des opérations de maintenance, de surveillance et de dépannage sans avoir besoin d'une interface graphique.

6. **Intégration avec d'autres outils** : La ligne de commande peut être facilement intégrée à d'autres outils et systèmes, ce qui permet aux ingénieurs de créer des pipelines complexes et des workflows automatisés.

En résumé, l'utilisation de la ligne de commande est importante pour un ingénieur car elle offre un contrôle précis, une flexibilité, une efficacité des ressources et la possibilité d'automatiser des tâches, ce qui est essentiel pour le développement, la gestion et le déploiement efficaces des systèmes et des applications.

La ligne de commande est souvent utilisée pour la gestion des ressources dans le contexte de la virtualisation pour plusieurs raisons :

1. **Accès à toutes les fonctionnalités** : Les plateformes de virtualisation telles que VMware, VirtualBox, et les solutions de cloud comme AWS, Azure et Google Cloud Platform offrent une gamme complète de fonctionnalités qui peuvent être contrôlées via des interfaces en ligne de commande. Cela inclut la création, la configuration, la surveillance et la gestion des machines virtuelles (VM), des réseaux virtuels, des disques virtuels, etc.

2. **Automatisation des tâches** : La virtualisation implique souvent des opérations répétitives telles que le provisionnement de VM, la migration de charges de travail, la gestion des snapshots, etc. L'utilisation de la ligne de commande permet d'automatiser ces tâches en écrivant des scripts, ce qui simplifie et accélère la gestion des ressources virtuelles.

3. **Contrôle précis des ressources** : La ligne de commande offre un contrôle précis sur les ressources virtuelles, permettant aux administrateurs de définir des paramètres spécifiques tels que la quantité de mémoire, de CPU et d'espace disque allouée à chaque machine virtuelle. Ce contrôle fin est crucial pour optimiser les performances et l'utilisation des ressources dans un environnement virtualisé.

4. **Gestion à distance** : Dans les environnements de virtualisation, il est courant d'avoir des infrastructures distribuées sur plusieurs serveurs physiques ou même sur des centres de données géographiquement dispersés. La ligne de commande permet une gestion à distance efficace de ces ressources, permettant aux administrateurs de se connecter à des serveurs distants et de gérer les VM sans avoir besoin d'une interface graphique.

5. **Intégration avec d'autres outils** : Les outils de ligne de commande des plateformes de virtualisation sont souvent conçus pour être facilement intégrés à d'autres outils de gestion, de surveillance et d'automatisation, ce qui permet aux administrateurs de créer des workflows personnalisés et des pipelines d'automatisation complets pour gérer efficacement leur infrastructure virtualisée.

En résumé, l'utilisation de la ligne de commande pour la gestion des ressources dans la virtualisation offre une automatisation, un contrôle précis, une gestion à distance et une intégration avec d'autres outils, ce qui en fait un choix privilégié pour les administrateurs qui cherchent à optimiser les performances et l'efficacité de leurs environnements virtualisés.

**Généralités**

Obtenir les numéros de build et de version d’ESXi :

`esxcli system version get`

Obtenir le nom d’hôte, le domaine et le nom de domaine complet de l’hôte :

`esxcli system hostname get`

Obtenir la date et l'heure d'installation d'ESXI :

`esxcli sytem stats istalltime get`

Répertorier les utilisateurs locaux sur l’hôte ESXi :

`esxcli system account list`

Créer un utilisateur ESXi local :

`esxcli system account add -d="Description" -i="username" -p="password" -c="password"`

Répertorier les commandes disponibles avec des descriptions :

` esxcli command getdetails `

Répertorier tous les espaces de noms disponibles avec les commandes correspondantes :

`  esxcli system maintenanceMode get `

Activer/Désactiver le mode de maintenance :

`  esxcli system maintenanceMode set -enable true  `

Redémarrer/redémarrer l’hôte ESXi :

` esxcli system shutdown reboot -r "message" `

Redémarrer/redémarrer l’hôte en mode de maintenance ESXi avec compte à rebours :

` esxcli system reboot -d 10 -r "Patch Updates" `

Obtenir des informations sur le processeur de l’hôte (famille, modèle et cache) :

` esxcli hardware cpu list `

Obtenir des informations sur la mémoire (accès à la mémoire disponible et non uniforme) :

`esxcli hardware memory get  `
