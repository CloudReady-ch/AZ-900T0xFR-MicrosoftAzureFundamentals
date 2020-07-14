---
wts:
    title: '22 - Calculer des SLA composites'
    module: 'Module 04 - Tarification et assistance Azure'
---
# 22 - Calculer des SLA composites


Dans cette procédure pas à pas, nous allons déterminer le contrat de niveau de service de disponibilité des services Azure, puis calculer la disponibilité attendue basée sur le contrat de niveau de service composite de l’application.

Notre exemple d’application se compose de ces services Azure. Nous n’entrerons pas dans une configuration et des considérations architecturales profondes. L’intention ici est de donner un exemple de haut niveau.

+ **App service** : Pour héberger l’application.
+ **Azure AD B2C** : Pour authentifier les connexions utilisateur et gérer les profils.
+ **Application Gateway** : Pour gérer l’accès aux applications et leur mise à l’échelle. 
+ **Base de données Azure SQL** : Pour stocker les données d’application. 

# Tâche 1 : Déterminer les valeurs de pourcentage de la durée active du contrat de niveau de service pour notre application

1. Dans un navigateur, accédez à la page [Résumé SLA pour les services Azure](https://azure.microsoft.com/fr-fr/support/legal/sla/summary/).

2. Localisez la valeur de durée active du contrat de niveau de service **App Service**, **99,95 %**. Cliquez sur **Voir tous les détails**, puis développez **Détails SLA**. Remarquez les **pourcentages de durée active mensuels** et les **crédits de service**.

3. Revenez à la page Web SLA et localisez le service **Azure Active Directory B2C** puis déterminez la valeur de durée active du contrat SLA, **99,9 %**. 

4. Localisez la valeur de durée active du contrat de niveau de service de l'**Application Gateway**, **99,95 %**. 

5. La base de données Azure SQL utilise des niveaux Premium mais n’est pas configurée pour les déploiements redondants de zone. Localisez la valeur de durée active du contrat de niveau de service de **base de données SQL Azure**, **99,99 %**. 

    **Remarque**: Il existe différentes valeurs de durée active pour divers déploiements et configurations de la base de données Azure SQL. Il est important que vous soyez clair sur vos valeurs de durée active requises, lorsque vous planifiez et évaluez votre déploiement et votre configuration. De petits changements dans la durée active peuvent avoir un impact sur les coûts de service et potentiellement augmenter la complexité de la configuration. Certains autres services intéressants apapraissent sur la page web du résumé SLA Azure : **Machines virtuelles**, **Comptes de stockage** et **Cosmos DB**.

# Tâche 2 : Calculer le pourcentage de temps de fonctionnement du contrat SLA composite de l’application

1. Si l’un des services qui composent notre application n’est pas disponible, notre application ne sera pas disponible pour la connexion et l’utilisation. En définitive, le temps de fonctionnement total de notre application se calcule sur la base des éléments suivants :

    **% de temps de fonctionnement d’App Service** X **% de temps de fonctionnement d’Azure AD B2C** X  **% de temps de fonctionnement d’Application Gateway Azure ** X **% de temps de fonctionnement de la base de données SQL Azure** = **% de temps de fonctionnement**

    qui, en pourcentage, est comme suit :

    **99,95 %** X **99,9 %** X **99,95 %** X **99,99 %** = **99,79 %**

    Il s’agit de la disponibilité attendue, telle que définie dans le contrat SLA de notre application, avec les services et l’architecture actuels.

Félicitations ! Vous avez déterminé la durée active basée sur le contrat SLA pour chacun des services de notre exemple d’application, puis calculé la disponibilité attendue basée sur le contrat SLA composite pour l’application.