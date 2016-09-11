# gcb-tutorial

## BiBiGrid
To start a BiBiGrid cluster in an OpenStack cloud computing environment
clone the github repository to your local machine.

  git clone https://github.com/BiBiServ/gcb-tutorial.git
  cd gcb-tutorial
  
You will be devided into two groups. One group will work on the
OpenStack Cloud in Bielefeld, the other group will work in Giessen.

### Bielefeld Setup

Copy the template to your working directory

  cp config/.bibigrid.properties.BIELEFELD ./bibigrid.properties
  
### Giessen Setup

Copy the template to your working directory

  cp config/.bibigrid.properties.GIESSEN ./bibigrid.properties
  
## Add credentials to properties file

Edit the `bibigrid.properties` file and add your OpenStack *credentials*.
You also need to specify the *SSH key name* and *SSH key file* in the
properties file. 

Edit the following lines in the properties file:

  openstack-username=# OPENSTACK USERNAME
  openstack-password=# OPENSTACK PASSWORD
  identity-file=#PATH TO PRIVATE SSH KEY
  keypair=# NAME OF KEYPAIR

## Start BiBiGrid cluster

Now you can start an OpenStack Cluster. Specifying your user name
during startup will make it easier to identify your cluster later.

  bin/bibigrid.sh -c -o bibigrid.properties -u USERNAME

Once the OpenStack instance is running, make sure you **take note of its IP
address**. We will need it later!

BiBiGrid will give you the necessary information you need to
login to the instance.

  export BIBIGRID_MASTER=<OPENSTACK INSTANCE IP ADDRESS>

You can then log on the master node with::

  ssh -i PATH_TO_YOUR_SECRET_SSH_KEY_FILE ubuntu@$BIBIGRID_MASTER


