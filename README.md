# udemy-ansible-assignment

#Infrastructure

I chose GCP

#Development Environment

I set up a local VM on Oracle Virtual Box as my Ansible Controller. There are some pre-requisites required on the Ansible Controller system to work with Google Cloud. Details are documented here Once the Ansible Controller was setup I proceeded to develop my project.

#Ansible Project

I decided to use tasks file for deploying VMs and create my own roles to configure those VMs with Application.​

Tasks: A role to deploy necessary compute instances on on Google Cloud
Roles: ansible-role-mysql: A role to install and configure MySQL on any given systems
Roles: ansible-role-flask-web: A role to install and configure Flask application on multiple
Tasks: Configure native Google Load Balancing and firewalls
Tasks: Send email notification
Group Variables to have following properties:

project_id: ID of my GCP project

service_account_email: ​ Service Account to connect to GCP

credentials_file: ​​ Credentials file to connect to GCP

num_web_instances: ​ Number of web instances to deploy

db_name: Database name

db_user: Database user to create

db_password: Password for the Database user

machine_type: Type of machine to deploy eg: n1-standard-1
​- image: Image of instance to deploy debian-7

instance_list: An array containing list of servers to deploy

   - web-server-1,web-server-2
   - db-server
db_name: Database name

db_user: Database user

db_user_password: Database user password

ansible_user: User to connect to Compute Instances using gcloud compute ssh

ansible_ssh_private_key_file: Private key file to connect to Compute Instances using gcloud compute ssh
