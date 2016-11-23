FROM oneview:latest

RUN cat /var/lib/gems/2.1.0/gems/chef-provisioning-oneview-1.2.0/lib/chef/provisioning/create_machine.rb | grep -v san > /tmp/fix
RUN mv /tmp/fix /var/lib/gems/2.1.0/gems/chef-provisioning-oneview-1.2.0/lib/chef/provisioning/create_machine.rb
