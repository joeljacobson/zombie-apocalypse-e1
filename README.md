#Zombie Apocalypse

VM for Zombie Apocalypse episode one.

##Prerequisites

Make sure all of these are installed and up-to-date.

* [Virtualbox](https://www.virtualbox.org/)
* [Vagrant](https://www.vagrantup.com/downloads.html)
* [Ansible](http://docs.ansible.com/intro_installation.html)

##Provisioning

Clone the project: `git clone https://github.com/joeljacobson/zombie-apocalypse-e1.git`

In the project directory enter: `vagrant up`

Your DataStax node will be ready shortly depending on your internet connection. The initial boot takes some time as Ansible has to download, install and configure DataStax Enterprise. Subsequent reboots are fast. If you experience any errors, destroy and recreate the vm.

When successful, halt the VM ready for the exercises `vagrant halt`

---

#Episode One

To be completed with slides.

##Ingest the dataset

Start the already provisioned VM with `vagrant up`

SSH into the VM with `vagrant ssh`

Ensure DataStax Enterprise is running `nodetool status`

Start a CQL Shell `cqlsh 192.168.56.10`

Create the CDC keyspace `CREATE KEYSPACE IF NOT EXISTS cdc WITH replication = {'class': 'SimpleStrategy', 'replication_factor': 1 };`

Create the CDC patient table `SOURCE '~/schema.cql'`

Ingest the patient data `COPY cdc.patient_data ( last_name, dob, patient_id,  first_name, job, ssn,  building_number, street_name, city, state, zipcode, company, latitude, longitude, blood_type ) FROM 'citizens.csv' WITH HEADER = true ;`
