# cattleworks

Macbook automation & configuration

## Initial Setup

1. Install the Xcode Command Line Tools by running `xcode-select --install`.
2. Install [Ansible](https://docs.ansible.com/ansible/latest/installation_guide/intro_installation.html#installing-and-upgrading-ansible-with-pip):
   
   1. Add python3 / homebrew to path: `export PATH="$HOME/Library/Python/3.8/bin:/opt/homebrew/bin:$PATH"`
   2. Upgrade pip: `sudo pip3 install --upgrade pip`
   3. Install ansible: `pip3 install ansible`

3. Run `git clone git@github.com:brianpham/cattleworks.git && cd "$(basename "$_" .git)"`
4. Run `cd ansible && ansible-galaxy install -r requirements.yml`
5. Run `ansible-playbook main.yaml --ask-become-pass`

## Manual Setup

todo: Add instructions for ohmyzsh and pk10

## Store your GPG key passphrase so you don't need to enter everytime you sign a commit using gpg-agent

brew install pinentry-mac
echo "pinentry-program $(brew --prefix)/bin/pinentry-mac" | tee ~/.gnupg/gpg-agent.conf
pkill -TERM gpg-agent


echo test | gpg -e -r brianpham@gmail.com | gpg -d