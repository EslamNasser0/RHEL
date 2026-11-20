## Using yum
### Install the google chrome package using dnf [two methods].
#### local package
``` bash
sudo dnf localinstall /home/eslamnasser/Downloads/google-chrome-stable_current_x86_64.rpm
```
#### package url link
``` bash
sudo dnf install https://dl.google.com/linux/direct/google-chrome-stable_current_x86_64.rpm
```
### Create the file /etc/yum.repos.d/cdrom.repo to enable install from the iso of Red Hat
``` bash
sudo vim /etc/yum.repos.d/cdrom.repo

[BaseOS]
name = BaseOS
baseurl = file:///run/media/eslamnasser/RHEL-9-8-0-BaseOS-x86_64/BaseOS
enabled = 1

[AppStream]
name = AppStream
baseurl = file:///run/media/eslamnasser/RHEL-9-8-0-BaseOS-x86_64/AppStream
enabled = 1
```
### Try to install any package from the new repository
``` bash
sudo yum repolist --ablerepo=rhel-9-for-x86_64-appstream-rpms,rhel-9-for-x86_64-baseos-rpms

sudo yum install ansible
```

## Using rpm
### List all installed packages in your system.
``` bash
sudo rpm -qa
```

### View the files in the httpd package
``` bash
sudo rpm -i httpd
```

### Get general information about httpd.
``` bash
rpm -ql httpd
```

### Have the files from the pam package changed since it was installed.
``` bash
rpm -V pam
```
