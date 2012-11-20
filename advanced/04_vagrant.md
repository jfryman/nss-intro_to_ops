!SLIDE

# Vagrant

![Vagrant Logo](../images/vagrant_logo.png)

<!SLIDE smaller>

# Vagrant's Power 
## Quick Iteration with Configuration Management

- Puppet
- Chef
- CFEngine
- Shell

<!SLIDE smaller>

# Typical Vagrant Workflow:

+ Model Environment 
+ _vagrant up_
+ Make change to Puppet Code
+ _vagrant provision_
+ Validate changes (either via debug or SSH)
+ Commit to git
+ Repeat (Change/Provision/Validate/Commit)s

!SLIDE

Let's try it!

!SLIDE

![ZOMG!](../images/zomg_kitteh.jpeg)

ZOMG! What is happening?!

<!SLIDE smaller>

- Vagrant unpacks box
  - Think VMWare Template/Amazon AMI
- Imports into VirtualBox/Boots
- Identifies Provisioner (Puppet) and executes (site.pp)
- Attempts to identify node, executs Puppet code
  - --debug --verbose
- Outputs a Dependency Graph (vagrant-hitch)

!SLIDE
# Stroller

- Converts Vagrantfile into YAML files
- Makes declaring multiple nodes/provisioners a snap
- All of this is included in the
[Stroller](https://github.com/jfryman/stroller) git repo.
  - Clone away!

!SLIDE
![doitlive](../images/doitlive.jpeg)


<!SLIDE small>

# Vagrant Limitations

+ Cannot facilitate Puppet Server functionality natively
  + Solved with [_puppet
server_](http://vagrantup.com/v1/docs/provisioners/puppet_server.html) provisioner
+ Vagrant boxes must be built outside of Vagrant
  + [Hand build a box](http://vagrantup.com/v1/docs/base_boxes.html) or Automate with [Veewee](https://github.com/jedi4ever/veewee)
+ Only can use VirtualBox as Hypervisor
  - Support for VMWare Fusion comming soon!


!SLIDE

If you want to learn more, visit
[http://vagrantup.com](http://www.vagrantup.com)

