![img](https://awebytes.wordpress.com/wp-content/uploads/2020/06/cap_win32.png)

Demo: https://www.youtube.com/watch?v=8i_xkEyCjq8

### Consideraciones de uso:

– En *Windows* sobre la ruta de archivos, se usa un sistema de valores estándar para equivalencia con Unix por tanto si la ruta a compartir es `C:\Users\Me` 
para evitar fallo en lectura del valor en el `config.json` su conversión válida seria `C:/Users/Me` y en el caso el valor de la ubicación ingresada 
en consola no es necesario reemplazo de `\` por `/` en la ruta indicada.

– Tanto en *Windows* como en *Linux* si no se agrega una terminación de la ruta se considera a compartir la ubicación padre de la ruta indicada. 
Por ejemplo `C:/Users/Me` mostrará acceso en `C:/Users/` que es donde se encuentra Me dando acceso a todos los directorios con archivos a nivel de `Me`, 
en cambio `C:/Users/Me/` desciende exactamente a `/Me` como raíz de acceso y sólo mostrará los archivos contenido ahí.

Configuración por default:
Agregar un archivo config.json junto con el ejecutable descargado con el siguiente contenido:

```json
{
"HttpPort": "1234",
"DirShared": "../"
}
```
