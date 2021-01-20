---
wts:
    title: '20 - Utiliser la calculatrice de coût TCO Azure (10 min)'
    module: 'Module 06 : Décrire la gestion des coûts et les accords de niveau de service d’Azure'
---
# 20 - Utilisez la calculatrice TCO Azure


Dans cette procédure pas à pas, vous allez utiliser la Calculatrice de coût total de possession (TCO) pour générer un rapport de comparaison des coûts pour un environnement local.

**Remarque**: Cette procédure pas à pas fournit des exemples de définitions de l’infrastructure locale et des charges de travail dans un centre de données typique. Pour créer un rapport de calcul de coût TCO, utilisez les exemples de définitions ou fournissez des détails sur les éléments *réels* de votre infrastructure locale et de vos charges de travail.

# Tâche 1 : Configurer la calculatrice du coût total de possession (TCO) (10 min)

Dans cette tâche, nous ajouterons des informations d’infrastructure à la calculatrice. 

1. Dans un navigateur, accédez à la page de la [calculatrice du coût total de possession (TCO)](https://azure.microsoft.com/fr-fr/pricing/tco/calculator/).

2. Pour ajouter des détails sur votre infrastructure de serveur locale, cliquez sur **+ Ajouter une charge de travail de serveur** dans le volet **Définissez vos charges de travail**.

    | Paramètres | Valeur |
    | -- | -- |
    | Nom | **Serveurs : Machines virtuelles Windows** |
    | Charge de travail | **Serveur Windows / Linux** |
    | Environnement | **Machines virtuelles** |
    | Système d’exploitation | **Windows** |  
    | Machines virtuelles | **50** |
    | Virtualisation | **Hyper-V** |
    | Noyau(x) | **8**|
    | RAM (Go) | **16** |
    | Optimiser par | **Processeur** |
    | Windows Server 2008 / 2008 R2 | **Off** |
    | | |

3. Sélectionnez **+ Ajouter une charge de travail de serveur** pour créer une ligne pour une nouvelle définition de charges de travail de serveur. 

    | Paramètres | Valeur |
    | -- | -- |
    | Nom | **Serveurs : Machines virtuelles Linux** |
    | Charge de travail | **Serveur Windows / Linux** |
    | Environnement | **Machines virtuelles** |
    | Système d’exploitation | **Linux** |  
    | Machines virtuelles | **50** |
    | Virtualisation | **VMware** |
    | Noyau(x) | **8**|
    | RAM (Go) | **16** |
    | Optimiser par | **Processeur** |
    | Windows Server 2008 / 2008 R2 | **Off** |
    | | |

4. Dans le volet **Stockage**, cliquez sur **Ajouter du stockage**.

    | Paramètres | Valeur |
    | -- | -- |
    | Nom | **Stockage serveur** |
    | Type de stockage | **Disque local / SAN** |
    | Type de disque | **HDD** |
    | Capacité | **60 To** |  
    | Sauvegarder | **120 To** |
    | Archive | **0 To** |
    | | |

5. Dans le volet **Mise en réseau**, ajoutez de la bande passante. 

    | Paramètres | Valeur |
    | -- | -- |
    | Bande passante sortante | 15 To|
    | | |

6. Cliquez sur **Suivant**.

7. Parcourez les options et effectuez les ajustements nécessaires. 

    | Paramètres | Valeur |
    | -- | -- |
    | Devise | **Euro** |
    | | |

8. Cliquez sur **Suivant**.

# Tâche 2 : Vérifier les résultats et enregistrer une copie

Dans cette tâche, nous évaluerons les suggestions de réduction des coûts et téléchargerons un rapport. 

1. Consultez les recommandations et les exemples de réduction des coûts Azure.

    | Paramètres | Valeur |
    | -- | -- |
    | Délais| **3 ans** |
    | Région | **Europe Nord** |
    | | |


2. Pour modifier les informations que vous avez fournies, accédez au bas de la page et cliquez sur **Retour**. 

3. Pour enregistrer ou imprimer une copie PDF du rapport, cliquez sur **Télécharger**.

    ![Capture d’écran du volet de rapport de la calculatrice de coût TCO dans Azure. Les champs de saisie mis en évidence et complétés indiquent comment définir le délai de la calculatrice de coût TCO sur trois ans et la région sur Europe du nord. Graphique présentant le coût de l’infrastructure locale et des charges de travail compensés par rapport au coût réduit de l’utilisation d’Azure.](../images/2001.png)

Félicitations ! Vous avez utilisé la calculatrice de coût TCO pour générer un rapport de comparaison des coûts pour un environnement local.
