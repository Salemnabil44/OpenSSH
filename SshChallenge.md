Pour configurer un serveur OpenSSH avec les spécifications mentionnées, vous devez modifier le fichier de configuration `sshd_config`, généralement situé dans `/etc/ssh/sshd_config`. Voici un fichier de configuration correspondant à vos exigences :

```plaintext
# Chemin du fichier de configuration : /etc/ssh/sshd_config

# Écouter uniquement sur IPv6 sur le port 222
Port 222
AddressFamily inet6
ListenAddress ::

# Restriction de l'accès à un seul utilisateur
AllowUsers wilder

# Désactiver l'authentification par mot de passe
PasswordAuthentication no

# Autoriser uniquement l'authentification par clé publique
PubkeyAuthentication yes

# Spécifier le fichier d'autorisation des clés publiques (optionnel, par défaut .ssh/authorized_keys dans le home de l'utilisateur)
# AuthorizedKeysFile .ssh/authorized_keys

# Autres configurations de sécurité recommandées
PermitRootLogin no
ChallengeResponseAuthentication no
UsePAM yes
```

### Explications :

1. **Port 222** :
   - `Port 222` spécifie que le serveur SSH écoute sur le port 222 au lieu du port par défaut (22).

2. **AddressFamily inet6** et **ListenAddress ::** :
   - `AddressFamily inet6` force le serveur à utiliser uniquement IPv6.
   - `ListenAddress ::` écoute sur toutes les adresses IPv6 disponibles.

3. **AllowUsers wilder** :
   - `AllowUsers wilder` permet uniquement à l'utilisateur nommé "wilder" de se connecter.

4. **PasswordAuthentication no** et **PubkeyAuthentication yes** :
   - `PasswordAuthentication no` désactive l'authentification par mot de passe.
   - `PubkeyAuthentication yes` active l'authentification par clé publique.

5. **Security Recommendations** :
   - `PermitRootLogin no` désactive la connexion directe en tant que root.
   - `ChallengeResponseAuthentication no` désactive les méthodes d'authentification basées sur des défis/réponses.
   - `UsePAM yes` permet l'utilisation de PAM (Pluggable Authentication Modules), qui peut gérer l'authentification via des modules configurables.

Assurez-vous que l'utilisateur "wilder" a configuré correctement ses clés publiques dans le fichier `~/.ssh/authorized_keys`. 

Pour appliquer les modifications, redémarrez le service SSH :

```bash
sudo systemctl restart sshd
```

Ou, selon votre distribution Linux, le service peut s'appeler `sshd` ou `ssh`.

```bash
sudo service ssh restart
```

Vérifiez également que le port 222 est ouvert et accessible via votre pare-feu et que l'écoute sur IPv6 est correctement configurée.
