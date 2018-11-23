# openshift_playbooks
Various Openshift playbooks

- monitor_cluster.yml

A simple playbook to monitor the status of the ocp cluster in terms of nodes, pod and api health. Also monitors critical systemd services such as ntp, firewalld, NetworkManager, dnsmasq
,atomic-openshift-node. It requires the openshift ansible inventory. In addition Docker stoarge utilization is monitored.
Moidify the web_conole_url and apps_wildcard_url variables in the playbook with environment specific values or run with ansible-playbook -e options.
Bases on 
http://v1.uncontained.io/playbooks/operationalizing/monitoring_guide.html

- validate_prereqs.yml

A simple playbook to validate ocp install prerequisites based on ocp 3.10 documentation,
https://docs.openshift.com/container-platform/3.10/install/prerequisites.html
Checks for NetworkManager, ntp, selinux, ip forwarding , dns resolution , rhel version and minimum hardware requirements.
It requires the openshift ansible inventory.
Moidify the master_min_cpu, master_min_ram and rhel_version variables in the playbook with environment specific values or run with ansible-playbook -e options.

## Todo
- complete minimum hw requirement checks
- complete checks for all the mount points required etc.. /etc/origin, /var/lib/origin
