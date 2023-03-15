### Dependencias necesarias
```
python3 -m pip install --user ansible
export PATH=$PATH:/home/user/.local/bin
ansible-galaxy collection install google.cloud
ansible-galaxy collection install ansible.posix
ansible-galaxy collection install ansible.netcommon
sudo apt-get install libldap2-dev libsasl2-dev
python3 -m pip install python-ldap
python3 -m pip install google-api-core google-api-python-client google-auth
```

### Variables y credenciales

Este scrip necesita algunas variables de entorno para funionar
* LDAP_ADMIN_PASSWORD=xxx
* LDAP_ADMIN_USER=cn=admin,dc=domain,dc=ext
* LDAP_BASE_DN=ou=unit,dc=domain,dc=ext
* LDAP_SERVER=ldap://ip:port/

Para el playbook de google es necesario bajar el archivo de credenciales de la cuenta de servicio ansible de google console
* Accedemos a la consola de Google
* APIs y Servicios -> Credenciales -> Cuentas de servicio -> ansible -> Generamos nueva clave

La clave debe estar en este directorio con el nombre `service_account_credentials.json`

### Ejecución
* Comando para crear usuario: `ansible-playbook create.yml`
* Comando para crear usuario: `ansible-playbook google.yml`
