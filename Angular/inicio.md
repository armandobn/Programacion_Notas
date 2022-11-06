
Creacion de Proyecto
```
ng new nombreDeProyecto
```

ejecutar el servidor

```
ng serve -o
```

Crear componentes
```
ng generate component heroes
```

Crear un Servicio
```
ng generate service hero
```


1.  `app.component.ts`— Este es el código para la clase de componente escrita en TypeScript.
2.  `app.component.html`— Este es el componente Plantillas escrito en HTML.
3.  `app.component.css`— CSS solo para este componente.

Siempre Importa el símbolo `[Component](https://docs.angular.lat/api/core/Component)` de la biblioteca pricipal de Angular, y realiza la anotación a la clase del component con `@[Component](https://docs.angular.lat/api/core/Component)`.

`@[Component](https://docs.angular.lat/api/core/Component)` es una decoradoro que especifica metadatos Angular para un componente.

La CLI generó 3 propiedades de metadatos:

1.  `selector`— El selector de elementos CSS para el componente
2.  `templateUrl`— La ubicación del archivo plantilla para el componente
3.  `styleUrls`— La ubicación de los estilos CSS privados del componente.