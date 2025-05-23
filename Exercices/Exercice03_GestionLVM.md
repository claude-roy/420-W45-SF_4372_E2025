# Exercice 3 – Gestion des disques LVM

### Informations
- Évaluation : formative
- Type de travail : individuel
- Durée : 1 heure
- Système d'exploitation : Linux Ubuntu client et Ubuntu serveur
- Environnement : virtuel, vSphere

### Objectifs :

Cet exercice a pour objectifs :

- Pouvoir ajouter des disques durs dans LVM

**Attention : cet exercice se fait sur le client et sur le serveur.**


## Partie 1 : Vérification de vos disques

Vérifier l'état de votre système avant de débuter.

Les commandes suivantes permettent de garder une trace des informations. 

```bash
echo --- Avant modification --- > FichierDesTraces.txt
date >> FichierDesTraces.txt
df -H >> FichierDesTraces.txt
lsblk >> FichierDesTraces.txt
cat /etc/fstab >> FichierDesTraces.txt
```

## Partie 2 : État du stockage LVM

Taper les commandes suivantes et garder une trace des informations :

```bash
echo --- Avant modification --- > FichierLVM.txt
date >> FichierLVM.txt
sudo pvs >> FichierLVM.txt
sudo vgs >> FichierLVM.txt
sudo lvs >> FichierLVM.txt
```

## Partie 3 : Modification de votre stockage LVM

D'abord il faut ajouter le disque <code>sdb</code> dans le "physiqual volume" : 

```bash
sudo pvcreate /dev/sdb # Si sdb est bien le nouveau disque vérifier avec la commande lsblk de la partie 1
sudo pvs
```

Par la suite, nous pouvons ajouter le disque dans le "volume group" :


```bash
sudo vgs  
sudo vgextend ubuntu-vg /dev/sdb # Attention: prenez le nom que la commande sudo vgs vous retourne pour le bon nom de VG.
sudo vgs  
```

Maintenant, nous allons étendre le "logical volume" :


```bash
df -h
sudo lvextend -l +100%FREE /dev/mapper/ubuntu--vg-ubuntu--lv
# ici j'utilise le nom complet de la partition logique renvoyé par la commande df.
```


Vérifier le résultat et placer l'information dans votre fichier : 

#### Vérification de vos disques

```bash
echo --- Après modification --- >> FichierDesTraces.txt
date >> FichierDesTraces.txt
df -H >> FichierDesTraces.txt
lsblk >> FichierDesTraces.txt
cat /etc/fstab >> FichierDesTraces.txt
```

#### État du stockage LVM

```bash
echo --- Après modification --- >> FichierLVM.txt
date >> FichierLVM.txt
sudo pvs >> FichierLVM.txt
sudo vgs >> FichierLVM.txt
sudo lvs >> FichierLVM.txt
```

## Partie 4: Ajuster votre fichier /etc/fstab

Débutons par une vérification de l'état du fichier /etc/fstab avec la commande df :

```bash
df -H 
```

Remarqué l'entré pour votre partition lvm dont le point de montage est <code>/</code> (root). C'est-à-dire celle que nous avons étendue. Elle n'est pas étendue.  

Le <code>resize2fs</code> est un utilitaire en ligne de commande qui vous permet de redimensionner des systèmes de fichiers ext2, ext3 ou ext4.  

<code>sudo resize2fs /dev/VG1/LV1</code>

Pour que le système de fichiers utilise la totalité de l'espace disponible, exécutez la commande :

```bash
sudo resize2fs /dev/mapper/ubuntu--vg-ubuntu--lv #Le nom de la partition monté dans le fstab.
df -H
```



Note : L'extension d'un système de fichiers est une opération à risque modéré. Il est donc recommandé de sauvegarder l'intégralité de votre partition pour éviter toute perte de données.
 
## Pour vérification

Remettre une capture d’écran des trois commandes suivantes, et ce pour les deux VMs (dans un seul fichier).

```bash
sudo pvs 
sudo vgs 
sudo lvs 
```

## Compétences développées


00Q1 - Effectuer l’installation et la gestion d’ordinateur :

    2 installer le système d’exploitation.
    4 Effectuer des tâches de gestion du système d’exploitation.

00SF - Évaluer des composants logiciels et matériels.

    1 Rechercher des composants logiciels et matériels.
    2 Formuler des avis sur les composants logiciels et matériels.

Note : les compétences sont développées en partie.

## Référence

- Formater un disque dur : [https://lecrabeinfo.net/formater-un-disque-dur-ssd-cle-usb-sur-ubuntu-linux.html#methode-n2-avec-gnome-disques](https://lecrabeinfo.net/formater-un-disque-dur-ssd-cle-usb-sur-ubuntu-linux.html#methode-n2-avec-gnome-disques)
- LVM : [https://access.redhat.com/documentation/fr-fr/red_hat_enterprise_linux/6/html/logical_volume_manager_administration/index](https://access.redhat.com/documentation/fr-fr/red_hat_enterprise_linux/6/html/logical_volume_manager_administration/index)

