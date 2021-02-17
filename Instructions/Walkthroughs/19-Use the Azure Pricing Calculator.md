---
wts:
    title: '19 - Utiliser la calculatrice de prix Azure (10 minutes)'
    module: 'Module 06 : Description de la gestion des coûts Azure et des contrats de niveau de service'
---
# 19 - Utilisation du calculateur de prix appliqués

Dans cette procédure pas à pas, nous utiliserons la calculatrice de prix Azure pour générer une estimation des coûts pour une machine virtuelle Azure et les ressources réseau associées.

# Tâche 1 : Configurer la calculatrice de prix (10 minutes)

Dans cette tâche, nous allons estimer le coût d’un échantillon d’infrastructure à l’aide de la calculatrice de prix Azure. 

**Remarque** : Pour créer une estimation de la calculatrice de prix Azure, cette procédure pas à pas donne des exemples de configurations pour la machine virtuelle et les ressources associées. Utilisez cet exemple de configurations ou fournissez au calculateur de prix appliqués Azure des détails sur vos besoins *réels* en ressources.

1. Dans un navigateur, accédez à la page Web [Calculateur de prix appliqués Azure](https://azure.microsoft.com/fr-fr/pricing/calculator/).

2. Pour ajouter des détails sur votre configuration de machine virtuelle, cliquez sur **Machines virtuelles**, sous l’onglet **Produits**. Faites défiler vers le bas pour afficher les détails de la machine virtuelle. 

3. Remplacez le texte **Votre estimation** et **Machines virtuelles** avec des noms plus descriptifs pour votre estimation du calculateur de prix appliqués Azure et votre configuration de machine virtuelle. Cet exemple pas à pas utilise **Mon estimation de la calculatrice de prix** pour l’estimation, et **Machine virtuelle Windows** pour la configuration de la machine virtuelle.

   ![Capture d’écran de la zone de configuration de la machine virtuelle dans la page Web d’estimation de la calculatrice de prix Azure. Le nom d’estimation et le nom de configuration de la machine virtuelle en surbrillance indiquent comment ajouter un nom d’estimation et un nom de configuration de la machine virtuelle à une estimation du calculateur de prix appliqués Azure.](../images/1901.png)

4. Modifiez la configuration de la machine virtuelle par défaut.

    | Région | Système d’exploitation | Type |
    |------|----------------|----|
    | Europe Nord | Windows | (OS uniquement) |
    | | |

    | Niveau | Instance |
    |----|--------|
    | Standard | A2 : 2 cœurs, 3,5 Go de RAM, 135 Go de stockage temporaire |
    | | |

   ![Capture d’écran de la zone de configuration de la machine virtuelle dans la page Web d’estimation de la calculatrice de prix Azure. Les exemples en surbrillance de valeurs de propriété de configuration de la machine virtuelle saisies par l’utilisateur indiquent comment spécifier une configuration de la machine virtuelle dans une estimation de la calculatrice de prix Azure.](../images/1902.png)

    **Remarque** : Les spécifications et les prix appliqués des instances de machine virtuelle peuvent différer de ceux de cet exemple. Suivez cette procédure pas à pas en choisissant une instance qui correspond le plus possible à l'exemple. Pour afficher les détails des différentes options de machine virtuelle, choisissez **Détails du produit** dans le menu **Plus d’informations** affiché dans le volet de droite.

5. Définissez la valeur de l’option **Facturation** sur **Paiement à l’utilisation**.

   ![Capture d’écran de la zone des options de facturation de la machine virtuelle dans la page web d’estimation de la calculatrice de prix Azure. L’option de facturation au fur et à mesure en surbrillance indique comment spécifier une option de facturation pour une machine virtuelle dans une estimation de la calculatrice de prix Azure.](../images/1903.png)

6. Dans Azure, un mois est défini comme 730 heures. Si votre machine virtuelle doit être disponible 100 %du temps chaque mois, vous devez définir la valeur des heures par mois sur `730`. Cet exemple pas à pas nécessite qu’une machine virtuelle soit disponible 50 % du temps chaque mois.

    Laissez le nombre de machines virtuelles défini sur `1` et modifiez la valeur des heures par mois sur `365`.

   ![Capture d’écran de la zone des options de facturation de la machine virtuelle dans la page web d’estimation de la calculatrice de prix Azure. Le nombre d’instances de machines virtuelles et d’heures par mois en surbrillance indique comment spécifier le nombre d’instances et d’heures par mois pour une machine virtuelle dans une estimation de la calculatrice de prix Azure.](../images/1904.png)

7. Dans le volet **Disques de système d'exploitation gérés**, modifiez la configuration de stockage de la machine virtuelle par défaut.

    | Niveau | Taille du disque | Nombre de disques | Instantané | Transactions de stockage |
    | ---- | --------- | --------------- | -------- | -------------------- |
    | HDD Standard | S30 : 1024 Gio | 1 | Désactivé | 10 000 |

   ![Capture d’écran de la zone d’options des disques du système d’exploitation gérés sur la page web d’estimation de la calculatrice de prix Azure. Les options mentionnant le type de niveau, la taille du disque, le nombre de disques et le nombre de transactions de stockage qui sont mises en surbrillance indiquent comment spécifier une configuration de stockage pour une machine virtuelle dans une estimation de la calculatrice de prix Azure.](../images/1905.png)

8. Pour ajouter de la bande passante de mise en réseau à votre estimation, accédez au haut de la page Web Calculateur de prix appliqués Azure. Cliquez sur **Mise en réseau** dans le menu produit à gauche, puis cliquez sur la mosaïque **Bande passante**. Dans la boîte de dialogue **Bande passante ajoutée**, cliquez sur **Vue**.

   ![Capture d’écran de la zone des produits de mise en réseau sur la page web de la calculatrice de prix Azure. Les mosaïques de mise en réseau, d’ajout de bande passante et d’affichage de bande passante en surbrillance indiquent comment ajouter et afficher les détails d’une configuration de bande passante de mise en réseau dans une estimation de la calculatrice de prix Azure.](../images/1906.png)

9. Ajoutez un nom pour votre configuration de bande passante de la machine virtuelle. Cet exemple pas à pas utilise le nom **Bande passante : Machine virtuelle Windows**. Modifiez la configuration de bande passante par défaut en ajoutant les détails suivants.

    | Région | Montant du transfert de données sortantes de la zone 1 |
    | ------ | -------------------------------------- |
    | Europe Nord | 50 Mo |

   ![Capture d’écran de la zone de configuration de la bande passante de mise en réseau dans la page web d’estimation de la calculatrice de prix Azure. Les exemples mis en évidence de valeurs de propriété de bande passante saisies par l’utilisateur indiquent comment spécifier une configuration de bande passante pour une machine virtuelle dans une estimation de la calculatrice de prix Azure.](../images/1907.png)

10. Pour ajouter une Application Gateway, revenez en haut de la page Web de la calculatrice de prix appliqués Azure. Dans le menu de produit **Mise en réseau**, cliquez sur la mosaïque **Application Gateway**. Dans la boîte de dialogue **Application Gateway**, cliquez sur **Vue**.

    ![Capture d’écran de la zone des produits de mise en réseau sur la page web de la calculatrice de prix Azure. Les mosaïques mise en réseau, ajouter une Application Gateway et afficher une Application Gateway en surbrillance indiquent comment ajouter et afficher les détails d’une configuration d’Application Gateway dans une estimation de la calculatrice de prix appliqués Azure.](../images/1908.png)

11. Ajoutez un nom pour votre configuration Application Gateway. Cette procédure pas à pas utilise le nom **App Gateway : Machine virtuelle Windows**. Modifiez la configuration Application Gateway par défaut en ajoutant les détails suivants.

    | Région | Niveau | Taille |
    | ------ | ---- | ---- |
    | Europe Nord | De base | Petite |
    | | |

    | Instances | Heures |
    | ------- | ------- |
    | 1 | 365 |
    | | |

    | Données traitées |
    | -------------- |
    | 50 Mo |
    | | |

    | Zone 1 : Amérique du Nord, Europe |
    | ----------------------------- |
    | 50 Mo |
    | | |

    ![Capture d’écran de la zone de configuration de l’Application Gateway dans la page Web d’estimation de la calculatrice de prix appliqués Azure.](../images/1909.png)


# Tâche 2 : Revoir l’estimation des prix appliqués

Dans cette tâche, nous allons examiner les résultats de la calculatrice de prix appliqués Azure. 

1. Faites défiler vers le bas de la page Web de la calculatrice de prix appliqués Azure pour afficher le total du **Coût mensuel estimé**.

    **Remarque** : Explorez les différentes options disponibles dans la calculatrice de prix Azure. Par exemple, cette procédure pas à pas vous oblige à mettre à jour la devise en Euro.

2. Modifiez la devise en Euro, puis sélectionnez **Exporter** pour télécharger une copie de l’estimation pour une consultation hors ligne au format Microsoft Excel (`.xlsx`).

    ![Capture d'écran du total des coûts mensuels estimés sur la page web d’estimation de la calculatrice de prix Azure. L’option de devise Euro mise en évidence indique comment modifier la devise utilisée dans une estimation de la calculatrice de prix Azure. L’option d’exportation en surbrillance illustre comment télécharger une copie d’une estimation pour une consultation hors ligne.](../images/1910.png)

    ![Capture d’écran d’un exemple d’estimation de la calculatrice de prix Azure dans Microsoft Excel.](../images/1911.png)

Félicitations ! Vous avez téléchargé une estimation à partir de la calculatrice de prix Azure.