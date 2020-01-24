[![RedHatROoT/ansible](https://avatars2.githubusercontent.com/u/2985831?s=100)](https://github.com/redhatroot/ansible/) 

[![MattTheITGuru](https://avatars0.githubusercontent.com/u/22283700?s=100)](https://MattTheITGuru.com)


<div style="position: absolute; top: 40px; left: 200px;">

These are preconfigured projects, playbooks, credentials, job templates that bolt on top of an existing workshop.  The end result is a turnkey demo environment with working examples out of the box.


## Summary - This project piggybacks on top of the F5 LinkLight Workshop for use as a repeatable demo

## Here's an example of how you could launch this process:
<pre>
ansible-playbook -i ~/networking-workshop/lab_inventory/hosts configurify.yml -e this_git_url='https://github.com/GoKEV/F5-workshop.git'
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
<pre>ansible-playbook -i ~/networking-workshop/lab_inventory/hosts configurify.yml -e this_git_url='https://github.com/SomeOtherUser/ClonedVersionOfThisRepo.git</pre>





















## Troubleshooting & Improvements

- Not enough testing yet

## Notes

  - Not enough testing yet

## Author

This project was created in 2020 by [Kevin Holmes](http://GoKEV.com/) and [Matt St. Onge](https://MattTheITGuru.com) 


