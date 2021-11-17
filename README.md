# Ansible boilerplate for webapps with Docker, Traefik and Let's Encrypt

## How to use it?
You have to set your own host in the [hosts](https://docs.ansible.com/ansible/latest/user_guide/intro_inventory.html) file. After that you can run the playbook.

```
ansible-playbook site.yml
``` 

The playbook will install Docker and the other requisites on the machine.

## How to deploy on app
The boilerplate contains an example app (roles/example-app). You can rename or copy it as a starting point, make sure you replace all "example-app" occurences in the folder with your new chosen name. After that you can edit the docker-compose.yml file in the templates directory and add your own services.

Replace the domain in the following line ``"traefik.http.routers.example-app.rule=Host(`example.jurrevriesen.nl`)"`` with the domain that is pointed to your webserver to make sure a Let's Encrypt SSL certificate is requested.

After you added the new role in site.yml, you can run the playbook again and the new app should be deployed.
