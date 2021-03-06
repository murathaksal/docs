﻿#Installer

Since version 2.5 the installation of RavenDB can be accomplished by using a GUI installer. The setup wizard will guide you through an installation process where you just need to
select the type of an installation and provide configuration options.

![Figure 1: Welcome screen](images/installer_welcome_screen.png)

##Target environment

You need to choose what kind of the environment you are targeting. The licensing requirements are different depending on the selected option:

* Production / Test - you have to provide a valid license in next step,
* Development - no license is required.

##Installation type

You can install the RavenDB either as a Windows service or as IIS application. Next steps will guide you through a configuration of a chosen deployment strategy. 

##Windows Service configuration

The configuration of the RavenDB service is straight-forward. You only have to provide the name and the port number of the service.

![Figure 2: Windows Service](images/installer_windows_service.png)

##IIS Application configuration

The configuration of RavenDB run on IIS requires you to go throught a few screens. 

###Web site
In the first dialog you need to enter a web site configuration. You have here two possibilities:

* Create a new web site
* Use an existing one

If you choose first option you will need to fill up the following fields:

![Figure 3: New IIS site configuration](images/installer_iis_new_site.png)

If you decided to use the already existing site you just need to choose which one:

![Figure 4: Existing IIS site](images/installer_iis_existing_site.png)

The _Virtual Directory_ field can be empty. Then it means that RavenDB will be installed at the root of the web site.

Optionally you can select a checkbox to configure a custom application pool for RavenDB application instead of using the default one configured for the web site.

###Application Pool (optional)

This optional dialog (shown when the checkbox on the previous screen was selected) allows you to set up a custom application pool. As previously you can either create a new or use an existing one.

![Figure 5: Application Pool](images/installer_iis_application_pool.png)

##Performance counters

The next screen is to configure permissions of the application pool user to the [performance counters access](../administration/perf-counters). This is needed to ensure that RavenDB hosted by IIS
will be able to create own counters and provide performance stats there.

![Figure 6: Performance counters](images/installer_iis_performance_counters.png)

##Upgrade

The RavenDB installer supports upgrades. The previously used settings (like a service name or an installation path) will be recovered by the wizard. The installation process first will 
automatically remove the old version and then will install the new one.

##Uninstall

Uninstallation can be accomplished by _Programs and Features_ in _Control Panel_ . Only the files created during an installation process will be removed, so all of database data will remain untouched on a disk.