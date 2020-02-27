#### Packages

List installed packages `yum list installed`, or `rpm -qa`.

List available packages `yum list available`.

List installed *and* available `yum list all`.

List packages installed but not found in any repos `yum list extras`.

Get package info `yum info <package>` or `rpm -qi <package>`.

Count number of packages installed `rpm -qa | wc -l`.

Count number of files of all installed packages `rpm -qal | wc -l`.

List dependencies of a package `yum deplist <package> | grep provider | awk '{ print $2 }'| sort | uniq`

List files intalled by a package `rpm -ql <package>`, for config files only `rpm -qlc <package>`

Get which package a file belongs to `rpm -qf <file>`. Or `yum provides "*/<filename>"`.

Install an RPM file `rpm -Uvh <package.rpm>`

List files that will be installed by an RPM file `rpm -qpl <package.rpm>`.

Search package names and summaries `yum search <keyword>`.

Search everything `yum search all <keyword>`.

#### Repos

List repos `list repo [-v]`.

List enabled repos `yum repolist enabled`.

Add repo `yum-config-manager --add-repo <url_to_repo>`.

Config files
* Global `/etc/yum.conf`
* Individual repo `/etc/yum.repos.d/*.repo`

After updating `.repo` files, `yum makecache`.

#### Plugins 

Plugins extend yum commands and options. 

List of plugins `yum search yum-plugin`.

#### Cleaning

Leaf packages. Those not installed by user and not required by any other packges.

#### Updating

Check for updates `yum check-update`.

Update a package `yum update <package>`. Update all packages `yum update`.

`yum updateinfo`

#### Groups

List of available groups `yum groups list`.

