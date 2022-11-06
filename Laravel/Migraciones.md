# Migraciones
**Carpeta:** config/database.php
**Carpeta:** database/migrations

Hacer una migracion
```
php artisan migrate
```

Crear migraciones nuevas
```
php artisan make:migration cursos
php artisan make:migration create_cursos_table
php artisan make:migration add_avatar_to_users_table
```

Regresar cambios en la tabla
```
php artisan migrate:rollback
```
Regresa cambios las veces que necesitas en total
```
php artisan migrate:rollback --step5
```


Elimina todas las trablas y las crea denuevo
```
php artisan migrate:fresh
php artisan migrate:refresh
```

Necesitamos esta dependencia para poder cambiar los valores de las tablas
**composer require doctrine/dbal**


php artisan make:migration cambiar_propiedades_to_users_table

Elimina todas las tablas
```
php artisan migrate:reset
```






## Factory's

Crear Factory
```
php artisan make:factory CursoFactory
```

Crear 50 elementos...
```
Curso::factory(50)->create();
```
 




