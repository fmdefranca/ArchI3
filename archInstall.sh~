########################################
# this is strictly for Arch linux only #
########################################


########################################
########### CUSTOM FUNCTIONS ###########
########################################

function pause(){
	read -p "$*"
}

################################################################################################################


# Reference = http://www.2daygeek.com/arch-linux-post-installation-30-things-to-do-after-installing-arch-linux/#
# check system is up to date
pacman -Syu

# adding a user
echo "Please enter your username"
read userName
useradd -m -G wheel -s /bin/bash $userName
echo "User $userName has been created successfully"
echo "NOw to enter your password"
password $userName
echo "Password has been changed successfully"
# now to uncomment wheel group for new user
# You need to look for this line in the file, %wheel ALL=(ALL) ALL
echo "Please look for this line \"%wheel ALL=(ALL) ALL\" and uncomment. use / or ? to find the word and n to go the next word if needed"
visudo
echo "Now to install sudo "
pacman -S sudo
echo "Sudo installed successfully"

# Enable multilib repo
echo "You need to open /etc/pacman.conf and remove the # from [multilib] and the include below."
echo "This is to allow 32bit software on a 64bit os"
echo "within the same pacman.conf file, add these lines"
echo "[archlinuxfr]"
echo "SigLevel = Never"
echo "Server = http://repo.archlinux.fr/\$arch"
echo "Then we will install yaourt"
pacman -Syu yaourt
echo "We will use yaourt using yaourt -Syu"
yaourt -Syu
