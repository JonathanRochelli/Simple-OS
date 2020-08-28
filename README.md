# Simple OS

### Le bootloader
Lors de démarrage de l'ordinateur, le BIOS (ou UEFI) va réaliser des vérifications des composants matériels de la machine.
Lorsque cela est fait, un logiciel, écrit en assembleur, est chargé en mémoire : le **bootloader**.
Ce logicel à pour rôle de charger un programme plus complexe : **le kernel**.

Pour en savoir plus sur le bootloader et le démarrage d'un ordinateur, veuillez consulter cette [page](https://www.ionos.com/digitalguide/server/configuration/what-is-a-bootloader/).

### Compilation
Pour compiler le code assembleur, vous devez avoir **nasm** d'installer sur votre machine.
Si ce n'est pas fait : 
- Ouvrez un terminal
- Tapez la commande suivante : `sudo apt-get install nasm`
- Rendez-vous ensuite dans le dossier contenant le fichier **.asm** avec la commande `cd`
- Tapez la commande : `nasm -f bin -o bootloader.img bootloader.asm`
- Vous devriez voir apparaître un fichier **bootloader.img**

### Exécution
Pour exécuter ce fichier, vous devez créer une machine virtuelle. Pour cet exemple, j'ai choisi d'utiliser Oracle VM VirtualBox :
- Créez une nouvelle machine virtuelle
- Donnez lui un nom et choisissez (Other -> Other/Unknown )
- Cliquez sur Suivant -> Suivant -> Créer -> Suivant -> Suivant -> Créer
- Rendez-vous ensuite dans Configuration -> Stockage
- Ajoutez un Controller (Floppy)
- Ajoutez ensuite à ce controlleur l'image que vous venez de créer précédement : `bootloader.img`
- Démarrez ensuite la machine

 Vous devriez voir affiché la chaîne de caractère **Hello World**
