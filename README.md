Description
-----------
Hosts file LWRP
Manages individual entries in /etc/hosts without effecting other entries


REQUIREMENTS
------------
Unix platform with /etc/hosts file


Resources/Providers
-------------------

hosts
=====
### Actions
* `:create`
  Add / Create entry in the host file
* `:remove`
  Remove entry from the hosts file

### Parameters

* `ip`   The IPV4 adress for this entry (defaults to name)
* `entries`  The list of entries for this ip.
* `force` Force the action even reguardless if entries match.  I.e. only match ip and force the new requested state 


Examples
--------

Create/modify Localhost entries 

      hosts "127.0.0.2" do
        entries %w/testlocal localtest test.localdomain.com/
      end

Force remove some entry
     
      hosts "127.1.1.3" do
        action :remove
        force  true
      end

See the example.rb  recipe for examples
