### Installation de OpenSSH sur Linux et Windows

#### Linux

Pour installer OpenSSH sur Linux, suivez ces étapes selon votre distribution :

##### Debian/Ubuntu

1. **Mettre à jour la liste des paquets :**
   ```sh
   sudo apt update
   ```

2. **Installer le serveur OpenSSH :**
   ```sh
   sudo apt install openssh-server
   ```

3. **Vérifier le statut du service SSH :**
   ```sh
   sudo systemctl status ssh
   ```

4. **Démarrer le service SSH (si nécessaire) :**
   ```sh
   sudo systemctl start ssh
   ```

5. **Activer le service SSH au démarrage :**
   ```sh
   sudo systemctl enable ssh
   ```

##### Fedora/CentOS/RHEL

1. **Mettre à jour la liste des paquets :**
   ```sh
   sudo dnf update
   ```

2. **Installer le serveur OpenSSH :**
   ```sh
   sudo dnf install openssh-server
   ```

3. **Vérifier le statut du service SSH :**
   ```sh
   sudo systemctl status sshd
   ```

4. **Démarrer le service SSH (si nécessaire) :**
   ```sh
   sudo systemctl start sshd
   ```

5. **Activer le service SSH au démarrage :**
   ```sh
   sudo systemctl enable sshd
   ```

##### Arch Linux

1. **Mettre à jour la liste des paquets :**
   ```sh
   sudo pacman -Syu
   ```

2. **Installer OpenSSH :**
   ```sh
   sudo pacman -S openssh
   ```

3. **Vérifier le statut du service SSH :**
   ```sh
   sudo systemctl status sshd
   ```

4. **Démarrer le service SSH (si nécessaire) :**
   ```sh
   sudo systemctl start sshd
   ```

5. **Activer le service SSH au démarrage :**
   ```sh
   sudo systemctl enable sshd
   ```

#### Windows

Pour installer OpenSSH sur Windows 10 et versions ultérieures, suivez ces étapes :

1. **Ouvrir les Paramètres :**
   Cliquez sur le bouton Démarrer, puis sélectionnez **Paramètres** (icône de roue dentée).

2. **Accéder à la section des fonctionnalités optionnelles :**
   Allez dans **Applications** > **Fonctionnalités facultatives**.

3. **Ajouter une fonctionnalité :**
   Cliquez sur **Ajouter une fonctionnalité** en haut de la page.

4. **Rechercher OpenSSH :**
   Dans la liste, trouvez **Client OpenSSH** et **Serveur OpenSSH**. Vous pouvez installer les deux selon vos besoins. Sélectionnez-les et cliquez sur **Installer**.

5. **Vérifier l'installation :**
   Après l'installation, vous pouvez vérifier que les fonctionnalités sont bien installées en ouvrant une fenêtre PowerShell et en exécutant les commandes suivantes :
   ```sh
   ssh -V  # pour vérifier le client
   ```

6. **Démarrer et configurer le serveur (si installé) :**
   Si vous avez installé le **Serveur OpenSSH**, vous devez démarrer le service et le configurer pour démarrer automatiquement :
   ```sh
   Start-Service sshd
   Set-Service -Name sshd -StartupType 'Automatic'
   ```

Avec ces étapes, vous devriez pouvoir installer et configurer OpenSSH sur Linux et Windows.
