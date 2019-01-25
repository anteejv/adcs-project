# Computer System Administration Project

This project lets you configure a Java e-commerce application to be used over a secure protocol (provided by **Letsencrypt**), with a load balancer (**Nginx**) in case of one server's outage, and a server gathering stats about the usage of the system (**Grafana, InfluxDB, Telegraf**). It was prepared using **Ansible**.

### In order to successfully use this project, four machines are needed:
- 2 application machines
- 1 load balancing machine
- 1 stats gathering machine


### The following variables in *hosts.ini* have to be set:
- APP1 NODE PUBLIC IP - public IP of the first application machine
- APP2 NODE PUBLIC IP - public IP of the second application machine
- WEB NODE PUBLIC IP - public IP of the load balancing machine
- APP1 NODE PRIVATE IP - private IP of the first application machine
- APP2 NODE PRIVATE IP - private IP of the second application machine
- DOMAIN NAME - name of your domain that is going to be used by load balancer
- EMAIL ADDRESS - your email address (needed for Letsencrypt configuration)
- STATS NODE PUBLIC IP - public IP of the stats gathering machine
- STATS NODE PRIVATE IP - private IP of the stats gathering machine

Once everything is set up, run the following command on your machine:
```
ansible-playbook -i hosts.ini setup_digital_commerce.yml
```

Hopefully it works :cow:
