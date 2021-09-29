### What is it?

A Vagrant configuration that starts up a PostgreSQL database in a virtual machine for local application development.

### Installation

First install [Vagrant] and [Virtual Box].

Then, run the following to create a new PostgreSQL app dev virtual machine:

### Usage

    # Optionally edit the database username/password:
    $ $EDITOR Vagrant-setup/bootstrap.sh

    # Start up the virtual machine:
    $ vagrant up

    # Stop the virtual machine:
    $ vagrant halt

### What does it do?

It creates a virtual server running Ubuntu 14.04 with the latest version of PostgreSQL (*as of writing 9.4*) installed. 
It also edits the PostgreSQL configuration files to allow network access and creates a database user/database for your application to use.

Once it has started up it will print out how to access the database on the virtual machine. It will look something like this:

    $ vagrant up
    Bringing machine 'default' up with 'virtualbox' provider...

    Your PostgreSQL database has been setup and can be accessed on your local machine on the forwarded port (default: 15432)
      Host: localhost
      Port: 5432
      Database: myapp
      Username: myapp
      Password: dbpass

    Admin access to postgres user via VM:
      vagrant ssh
      sudo su - postgres

    psql access to app database user via VM:
      vagrant ssh
      sudo su - postgres
      PGUSER=myapp PGPASSWORD=dbpass psql -h localhost myapp

    Env variable for application development:
      DATABASE_URL=postgresql://myapp:dbpass@localhost:15432/myapp

    Local command to access the database via psql:
      PGUSER=myapp PGPASSWORD=dbpass psql -h localhost -p 5432 myapp

