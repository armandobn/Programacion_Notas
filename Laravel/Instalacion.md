# Requeriemientos
- Compouser
- NodeJS
- Xampp (php,mariadb/mysql, servidor apache)

**Nota:**
Checar en la documentacion de laravel:
- la version a utilizar
- la version minima de php que soporta

## Instalacion de Progamas Necesarios
- Instalar Nodejs:
	Solo darle siguiente: [Enlace NodeJs](https://nodejs.org/es/)
- Instalar Composer:
	Solo darle siguiente: [Enlace Composer](https://getcomposer.org/)

## Verificar que esten instalados

**Nota:**
Debes abrir la consola de tu preferencia para ejecutar los comandos
Ejemplos:
- CMD (Windows)
- Git Bash (Terminal de Git Integrada en Windows)
- Visual Studio Code (Terminal Integrada)

Ver la Version de nodejs
```
node -v
```

Ver la Version de npm
```
npm -v
```

Ver la Version de Composer
```
composer -v
```

## Instalar Laravel

1. Instalar Laravel
	```
	composer global require laravel/installer
	```
2. Crear proyecto
	```
	laravel new example-app
	```
3. Ejecutar la aplicacion de Laravel //manda una url
	```
	php artisan serve
	```

Cambiar el puerto
```
artisan serve --port=PORT_NUMBER
artisan serve --port=3040
```
