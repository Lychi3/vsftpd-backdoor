# Exploit para el Backdoor vsftpd 2.3.4 (CVE-2011-2523)

Este exploit aprovecha un backdoor en la versión 2.3.4 del servicio FTP vsftpd. El backdoor fue introducido en el código fuente de manera maliciosa y permite la ejecución remota de comandos como root en el servidor afectado

![Exploit](/image.png)

## Funcionamiento
El backdoor se activa al enviar un nombre de usuario que contenga los caracteres `:)` seguido de cualquier contraseña. Esto hace que el servidor abra una conexión en el puerto 6200, donde se puede obtener una shell interactiva

## Requisitos:
- Python 3
- pwntools

## Instalación
```
git clone https://github.com/Lychi3/vsftpd-backdoor.git
cd vsftpd-backdoor
pip install pwntools
```

## Uso
Ejecuta el script proporcionando la dirección IP del servidor vulnerable:
```python
python3 vsftpd_exploit.py <dirección_ip>
```
Si el servidor es vulnerable, se abrirá una shell interactiva
