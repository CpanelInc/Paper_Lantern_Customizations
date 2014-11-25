# Example Paper Lantern Customizations

Paper Lantern, the newest user interface for cPanel, provides the means to create beautiful customizations for your end users. This project intends to gather examples which cPanel customers can reference when implementing their own customizations of Paper Lantern.

## How to use

### Before you get started

These styles are for use with cPanel & WHM version 11.46 or higher. Before beginning, ensure that you have an installation of cPanel & WHM that has completed the Getting Started Wizard and license check. For more information about how to get set up, please reference http://documentation.cpanel.net/display/ALD/Installation+Guide

The following instructions assume that you have root access to your cPanel & WHM server, that you have the means of using SSH and that you are familiar with the BASH command line.

### Steps
1. SSH into your cPanel & WHM server and 
2. Create the ``/var/cpanel`` directory if it doesn't already exist: ``mkdir -p /var/cpanel/`` 
3. ``cd /var/cpanel``
4. Copy the github clone URL from the project's page on github. Be ready to use it in the next step in place of the ``{github url}`` value
5. ``git clone {github url} customizations``

### Verifying the installation
In order to verify that you have installed these styles correctly, log into a cPanel account on your machine and click the 'Change Styles' menu item in the User Preferences pulldown.  Styles from this project should now appear in the list.

## How to contribute

TODO: write this

## Licensing

The MIT License (MIT) Copyright (c) 2014 cPanel, Inc. - for more information about the licensing of this document, please review the LICENSE.md file in the project root
