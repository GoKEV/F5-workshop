[![RedHatROoT/ansible](https://avatars2.githubusercontent.com/u/2985831?s=100)](https://github.com/redhatroot/ansible/) 

[![MattTheITGuru](https://avatars0.githubusercontent.com/u/22283700?s=100)](https://MattTheITGuru.com)


<div style="position: absolute; top: 40px; left: 200px;">

These are preconfigured projects, playbooks, credentials, job templates that bolt on top of an existing workshop.  The end result is a turnkey demo environment with working examples out of the box.


## Here's an example of how you could launch this process:
<pre>
ansible-playbook -i tower.hosts configurify.yml
</pre>

## With a hosts file called ```tower.hosts``` that looks like this:
<pre>

[rhpdstower]
tower1	ansible_host=1.2.3.444 ansible_ssh_user=student1

[rhpdstower:vars]
ansible_ssh_pass: ansible

</pre>

## And a variable in the playbook to include the license file:
## request this from https://store.ansible.com/tower/tower_license/
## paste in the resulted key as a variable, adding the line ```"eula_accepted": true,``` at the top, as shown below:

<pre>
license_file: |
  {
      "eula_accepted": true,
      "company_name": "TurnKeyDemos", 
      "contact_email": "kev@redhat.com", 
      "contact_name": "Kevin Holmes", 
      "features": {
          "activity_streams": true, 
          "rebranding": true, 
          "surveys": true, 
          "system_tracking": true, 
          "workflows": true
      }, 
      "hostname": "abcdefghijklmnopqrstuvexyz1234567890", 
      "instance_count": 15, 
      "license_date": 1234567890,
      "license_key": "abcdefghijklmnopqrstuvexyz1234567890abcdefghijklmnopqrstuvexyz1234567890",
      "license_type": "basic", 
      "subscription_name": "TurnKeyDemos"
  }

</pre>

## Troubleshooting & Improvements

- Not enough testing yet

## Notes

  - Not enough testing yet

## Author

This project was created in 2020 by [Kevin Holmes](http://GoKEV.com/) and [Matt St. Onge] (https://MattTheITGuru.com) 


