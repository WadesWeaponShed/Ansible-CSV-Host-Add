This is a sample on how to add CP Host objects using Ansible, but the objects are in a CSV file. All files are written in YAML.

## How to Use ##
 - Extract files to your Ansible server
 - Fill out hosts.csv_add
    format: name,ip,group_name
 - Execute csv_add.yml (ansible-playbook csv_add.ym)

## How it Works ##
csv_add.yml runs two separate playbooks.
1. First Playbook Executed is iterate_csv.yml
  - this also calls iterate_csv.j2 which is a jinja2 script to create the variable from hosts.csv
2. Second Playbook is add_hosts_csv.yml
  - this creates the hosts using the Infinity API
