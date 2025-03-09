# How to setup the Development Desktop (Ubuntu 24.04)

## Install the required tools

### Nala

!!! note

    On older Ubuntu/Debian version the `nala` package is not always available.
    In these cases the [following guide][nala-install-guide] can be used to install `nala`.

#### Install the nala front-end
``` shell
sudo apt install nala
sudo nala upgrade
```

#### Configure to use the fastest mirror
``` shell
sudo nala fetch
```

### cURL

In certain Ubuntu installations cURL is not available. Since this guide uses cURL extensively,
we have to make sure it is installed first.

``` shell
sudo nala install curl
```

### Install internal Root CA certficate

!!! note
    If you don't use an internal root certificates skip this step.

``` shell
sudo nala install -y ca-certificates
sudo curl -skSL https://<url of the root cert> -o /usr/local/share/ca-certificates/<your root ca.pem.crt
sudo update-ca-certificates
```

### GnuPG

#### Install the required packages
``` shell
sudo nala install -y gnupg gnupg-agent scdaemon pcscd
```

#### Import the private keys
``` shell
curl -sSL https://<url hosting the keys> | gpg --import 

# Set the ${KEYID} to your key's id
export KEYID=<your key id>
gpg --command-fd=0 --pinentry-mode=loopback --edit-key "$KEYID" <<EOF
uid *
trust
5
y
save
EOF
```

### YubiKey

#### Check the key status

Before we can use the YubiKey we have to make sure it is accessible. Connect the key to the machine and run the following command. This should show some basic information about your YubiKey card.

``` shell
gpg --card-status
```

``` shell
❯ gpg --card-status
Reader ...........: Yubico YubiKey FIDO CCID 00 00
Application ID ...: D276##################################
Application type .: OpenPGP
Version ..........: 3.4
Manufacturer .....: Yubico
Serial number ....: 1########
Name of cardholder: [not set]
Language prefs ...: [not set]
Salutation .......: 
URL of public key : [not set]
[...]
General key info..: sub  ed25519/#################################
❯ 
```

If the above command didn't work try creating the following file before retrying.

``` shell
cd ~/.gnupg
touch scdaemon.conf
echo "disable-ccid" >>scdaemon.conf
gpg --card-status
```

### Use GPG for SSH keys

#### Download the agent config template
``` shell
cd ~/.gnupg
curl -sSLO https://raw.githubusercontent.com/drduh/config/master/gpg-agent.conf
gpg-connect-agent /bye
```

#### Replace agents

In order to use the GPG connect agent to use with SSH add the following lines to you `rc` file:

``` shell
cat >> ~/.bashrc <<EOF
export GPG_TTY="\$(tty)"
export SSH_AUTH_SOCK=\$(gpgconf --list-dirs agent-ssh-socket)
gpgconf --launch gpg-agent
<<EOF
```

### Chezmoi

``` shell
sh -c "$(curl -fsLS get.chezmoi.io)" -- init --apply ${GITHUB_USERNAME}
sudo nala install zsh
chsh
```

### Gogh - Terminal Color schemes

``` shell
sudo nala install dconf-cli uuid-runtime
bash -c "$(wget -qO- https://git.io/vQgMr)"
```

### Install Commitizen

``` shell
sudo nala install pipx
pipx ensurepath
```

At this point logout and log back in to make sure the variables are working.

``` shell
pipx install commitizen
```

[nala-install-guide]: https://gitlab.com/volian/nala/-/wikis/Installation
