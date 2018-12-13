# ckan-source-installation-guide
A guide to make key configurations on ckan while installing from source

## Basic Setup
* Setup CKAN Locally using https://docs.ckan.org/en/2.8/maintaining/installing/install-from-source.html
  * Skip the Solr Installation Setup from source
* Setup Solr from https://github.com/tanvirchahal/docker-ckan-solr
* Run: `docker-compose -f docker-compose.yml up`
* development.ini file replace solr_url with this solr_url = http://127.0.0.1:8986/solr/ckan
  * Note: The port would change depending upon the version of solr you want to use. All the ports are defined in solr docker file

## Activate Virtual Env
* `. /usr/lib/ckan/default/bin/activate`

## Create new sysadmin
Setting up sysadmin based on https://docs.ckan.org/en/2.6/maintaining/getting-started.html#create-admin-user
* `paster sysadmin add ckan_admin -c /etc/ckan/default/development.ini`
* Enter password: `test1234`

## Run CKAN
`paster serve /etc/ckan/default/development.ini`

## Install CKAN extenstion
* Move to the src folder of /usr/lib/ckan/default/src/
* Clone the ckanext-*** extension
* `pip install -r requirements.txt`
* `python setup.py develop`






