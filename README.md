# Cobbler Helper Scripts

These are some simple scripts that I use with cobbler to help keep it
clean, reuse the data contained in it and customise my work flow.

They all assume `http://cobbler/cobbler_api` works. In some cases you can
pass regexs in as options and the scripts will pass them to the cobbler
API for processing.

## profile-members

Show the FQDN of all the hosts assigned to the given profile

## hosts-with-base-profile

We have some base profiles that exist only to hold common, top level,
information that's too generic for any real machines to be based on. Any
hosts in these groups should be reassigned.

## overloaded-systems

We try and keep all our config generic, and assigned by profiles. Any
machines with their own management classes, or kick start meta data set
need to be investigated and the config "pushed up" the inheritance
tree to a role. No host should be special.

## no-parent-profile

Only a small number of profiles should be top level ones. This check
shows all profiles that lack a parent profile.

## cobbler-profile-cssh

Runs `cssh` (ClusterSSH) against all the hosts in the given profile. The
hosts can be filtered, very basically, with a second (string) argument.

## cobbler-profile-cssh-menu

Shows a command line dialog menu that allows you to choose the profile
you want to run cssh against. It works but it's very basic.
Requires the `dialog` package (tested on Ubuntu 10.10)


### Author
 * [Dean Wilson](https://www.unixdaemon.net)
