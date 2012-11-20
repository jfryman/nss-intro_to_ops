!SLIDE
# Configuration Management
* Manage Server State
* Many Tool Options (Puppet/Chef/CFEngine)

!SLIDE
# Which one should I use?
* Puppet if you want the sysadmin POV
* Chef if you want a tool as a developer
* CFengine if you're a glutton for pain.

!SLIDE
![puppetlabs](../images/puppetlabs.png)

!SLIDE
## Puppet assigns and maintains Desired State
![desiredState](../images/Provision-Configure-Puppet.png)

!SLIDE
## Puppet Manages Configuration Drift
![configdrift](../images/config_drift.png)

!SLIDE
## Breaks down system concepts into resources
    @@@ Ruby
	user { 'jamison':
	  ensure => present,
	  gid    => 'bofh',
	}
	
!SLIDE
## Uses a Resource Abstraction Layer
![ral](../images/RAL_resource-types.png)
	
!SLIDE small
## Package-File-Service
	@@@ Ruby	
	package { 'ntp':
	  ensure => present,
	}
	file { '/etc/ntp.conf':
	  owner   => 'root',
	  group   => 'root',
	  mode    => '0644',
	  source  => 'puppet:///modules/ntp/ntp.conf',
	  require => Package['ntp'],
	}
	service { 'ntpd':
	  ensure    => running,
	  enable    => true,
	  subscribe => File['/etc/ntp.conf'],
	}

!SLIDE
# When do I use this?
* When trying to programatically manage resources on a system
* Building out large infrastructures (200+ nodes)

!SLIDE
# Caveats
* Limited support for network devices
* Limited support for cloud providers
* Must build-out own infrastructure to use Puppet (Master/Agent)
