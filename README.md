Currently maintained by [![GoKEV](https://avatars2.githubusercontent.com/u/2985831?s=100)](https://github.com/redhatroot/ansible/)  and   [![MattTheITGuru](https://avatars0.githubusercontent.com/u/22283700?s=100)](https://MattTheITGuru.com)


<div style="position: absolute; top: 40px; left: 200px;">

These are preconfigured projects, playbooks, credentials, job templates that bolt on top of an existing workshop.  The end result is a turnkey demo environment with working examples out of the box.


## Summary - This project piggybacks on top of the F5 LinkLight Workshop for use as a repeatable demo

## Here's an example of how you could launch this process:
<pre>
ansible-playbook -i ~/networking-workshop/lab_inventory/hosts configurify.yml
</pre>

# Provision a new F5 RHPDS workshop
* Once you receive the SSH information, connect as 'studentX' user provided.
* From the home directory of 'studentX', clone this repo (or your forked version of it)
<pre>git clone https://github.com/GoKEV/F5-workshop.git</pre>

* CD into the directory
<pre>cd ~/F5-workshop/</pre>

* Launch the playbook using the defaults as so:
<pre>ansible-playbook -i ~/networking-workshop/lab_inventory/hosts configurify.yml</pre>

* Alternatively, if you clone this repo, you can pass the URL for **your** repo.  This is the repo that will be populated into Ansible Tower.
<pre>ansible-playbook -i ~/networking-workshop/lab_inventory/hosts configurify.yml -e this_git_url='https://github.com/SomeOtherUser/ClonedVersionOfThisRepo.git'</pre>


# Launching the demo (work in progress, more info to follow).
# Here are the basic steps
* Navigate in Ansible Tower to Job Templates -> Manage F5 Apps.  Notice this job template has been created automatically for you in the directory of `REPOSITORY_ROOT/demolabs/01_Apps/` -- this is where the playbook is located.  

<img src="https://raw.githubusercontent.com/GoKEV/F5-workshop/master/screenshots/f5_job_template.png" width="600">

One directory below that, you'll find the directory `REPOSITORY_ROOT/demolabs/01_Apps/varfiles/` where the F5 app configuration files are stored.  The playbook looks dynamically in this directory each time it runs.

<img src="https://raw.githubusercontent.com/GoKEV/F5-workshop/master/screenshots/f5_tree.png" width="300">

Inside this directory, **only** the files named **app_** will be used.  The template file, though named in a way that it won't be discovered, provides the necessary information to create a new app, using these fields.  Please see `REPOSITORY_ROOT/demolabs/01_Apps/varfiles/template.yml` for details.

<img src="https://raw.githubusercontent.com/GoKEV/F5-workshop/master/screenshots/f5_template.png"  width="180">

This project comes pre-populated with four different APP definitions:
* app_a.yml (enabled by default)
* app_b.yml (enabled by default)
* app_c.yml (disabled by default)
* app_http_pool.yml (enabled by default)

Once you have added / modified the files to your desire, commit your changes and click the rocket icon to LAUNCH the job template.

<img src="https://raw.githubusercontent.com/GoKEV/F5-workshop/master/screenshots/f5_launch.png">

You will automatically be redirected to the job logging in realtime and you will see the playbook creating and removing the apps, based on the criteria in the files within the directory `REPOSITORY_ROOT/demolabs/01_Apps/varfiles/`

<img src="https://raw.githubusercontent.com/GoKEV/F5-workshop/master/screenshots/f5_tower_job_log.png">

Once this playbook completes, the last line will be a debug message, telling you the IP address and login information for your Big IP virtual appliance.  Log in to the virtual appliance, then navigate to see your network traffic:
* Local Traffic -> Network Map 

<img src="https://raw.githubusercontent.com/GoKEV/F5-workshop/master/screenshots/f5_network_traffic.png">









## Troubleshooting & Improvements

- Not enough testing yet

## Notes

  - Not enough testing yet

## Author

This project was created in 2020 by [Kevin Holmes](http://GoKEV.com/) and [Matt St. Onge](https://MattTheITGuru.com) 


