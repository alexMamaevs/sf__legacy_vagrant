### What is it?

A Vagrant configuration that starts up a PostgreSQL database in a virtual machine for local application development.

### Installation

First install [Vagrant] and [Virtual Box].

Then, run the following to create a new PostgreSQL app dev virtual machine:

### Usage

    # Start up the virtual machine:
    $ vagrant up

    # Stop the virtual machine:
    $ vagrant halt
	
	# Destroy the virtual machine:
	$ vagrant destroy

### What does it do?

It creates a virtual server running Ubuntu 16.04 with the version of PostgreSQL 8.4 installed. 
Edit the bootstrap.sh file to select a different PostgreSQL version.

Once it has started up it will print out how to access the database on the virtual machine. It will look something like this:

    $ vagrant up
    Bringing machine 'default' up with 'virtualbox' provider...

    Your PostgreSQL database has been setup and can be accessed on your local machine on the forwarded port (default: 5432)
      Host: localhost
      Port: 5432
      Database: postgres
      Username: postgres
      Password: 

    Admin access to postgres user via VM:
      vagrant ssh
      sudo su - postgres

