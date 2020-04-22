# rpi3.inicial

Role de ansible para instalar y configurar Raspberry pi.

	- Crea usuario con el mismo nombre y password que el usuario de local host
	- Crusa key ssh del mismo
	- Instala Paquetes basicos
	- Setea vim como editor por defecto
	- configura sudo para que no pida password
	- instala docker desde repo oficial paquete de rasbian de la version de la distribucion instalada

Plataformas testeadas:
- raspbian

## Uso

- Crear o modificar el archivo requirements.yml en el directorio raiz de la receta para incluir el rol.

```
- src: 
  scm: git
  version: "master"
```

- Ejecutar el comando galaxy-install para instalar el rol.

```
ansible-galaxy install -r requirements.yml
```

- Incluir el rol en la receta y modificar de ser necesario el valor de las variables definidas en defaults/main.yml a traves del paso de parametros al rol.

```
- Se puede ejecutar desde carpeta test 

	- Mientras usuario "pi" se encuentra habilitado:
		ansible-playbook -i tests/test_inventory tests/test_playbook.yml -u pi -k

	- Una vez creado el usuario y cruzada la clave publica (necesita sudo habilitado):
		ansible-playbook -i tests/test_inventory tests/test_playbook.yml 


```

