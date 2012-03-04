# Lab Exercise: Data Bags

## Lab Objectives

* Create a data bag of users
* Manage users on the system
* Create a new data bag with information about an application to deploy

## Acceptance Criteria

* Example user(s) are created on the system in the sysadmin group
* The example application code is described in a data bag and cloned on the system

## Download Users Cookbook

Download the `users` cookbook from the Chef Community site and extract it into the `cookbooks` directory. Add the `users::sysadmins` recipe to the `base` role's run list, as all the users should exist on every system.

## Create a Users Data Bag

Create a `data_bags` directory in the root of the `chef-repo`, then create a `users` directory that will hold the `users` data bag items.

Create a new user data bag item. Replace USERNAME below with any username you'd like to use. The `ssh_keys` field must be present, but the value can be empty, or you can generate an SSH key pair.

    {
      "id": "USERNAME",
      "groups": "sysadmin",
      "comment": "USERNAME",
      "uid": 2003,
      "shell": "/bin/bash",
      "ssh_keys": "ssh-rsa SSH Public Key"
    }

Save this as `data_bags/users/USERNAME.json` in the Chef Repository. Create the data bag on the Chef Server and upload the data bag item.

## Questions

How many users were created on the system?


What are the results of using knife to search for users? (`knife search users "*:*"`)?


Modify the data bag item .json file in your Chef Repository and remove a trailing comma. What happens when you try to upload the data bag item again? (be sure to fix this and add the comma back)


Bonus: How could the data bag item and corresponding recipe be modified to account for deleting a user?


Bonus: Attempt to create a new data bag item without creating the data bag first. What happens? What is the HTTP status code and why?
