Tareas a desarrollar 
Armando

-   Validación de los mimes y nombres de archivos
-   Modulo de CO estado 
validar imagenes=jpg,png 



co - estado
- generar expedientes en el sistema
- 

Se hara para prueba piloto:
- Regulacion de aportaciones en el ISSTE


pendientes
- agregar campo de ingreso
- generar la solicitud en el modulo de RH
- expedir el pdf

estados “solicitud, proceso, terminado, rechazado “hoja de servicio.

Habilitar el storage
php artisan storage:link


libreria: carbon (laravel integrado)
https://carbon.nesbot.com/


Algolia client
SCOUT_DRIVER=database
Configuracion de busqueda: Coloca en el archivo .env hasta abajo

composer require algolia/algoliasearch-client-php

  public function generarSolicitud(Request $request)
    {
        $request->f_solicitud = str_replace('-', '/', $request->f_solicitud);
        $pdf = App::make('dompdf.wrapper');
        $pdf->setOption(['dpi' => 150, 'defaultFont' => 'sans-serif']);
        $pdf->loadHTML(view('modules.ocestado.formatoPDF', compact('request')));
        return $pdf->stream();
        // return $pdf->download();
    }



-----------
24/10/2022

- Hacer el diagrama de flujo de como son los  calculos de cada una de las solicitudes
- Armar Catalogos, anotar el nombre del catalogo y el porque.
- Haran una tabla de alsa de salarios
En espera
- falta añadir validaciones
- aplicar a las vistas un order by por cosas resientes
- separar el js
- anotara algunas instrucciones cuando suba el github de lo que ya tiene

Eventual
Separacion por roles de los usuarios

---------------------------
1- Requsitos
2- desarrollo de los calculos
3- mostralos antes  de imprimirlos
4- anotaciones de restricciones

-          DOC (Plazas Docentes)
-          ADMVO (Plazas Administrativas)
-          TABLA DE CAL. DE QS (Quinquenios Docentes/Administrativos)

--------------------------
Tabla en mysql
- Sueldos administrativo/docente
- quinqueneos


