# Reglas del Proyecto

## Proyecto

`Project_D` es un videojuego de acción y combate inspirado en juegos como `Mortal_Kombat_Shaolin_Monks`.

El proyecto utiliza principalmente:

* Blueprints.
* Sistemas de combate.
* Habilidades de movimiento.
* Interacción entre personajes.
* Cámaras de gameplay.
* Animaciones.
* Cinemáticas.

No agregar sistemas que no hayan sido solicitados.

## Motor

* Unreal Engine `5.3.2`.
* No actualizar ni cambiar la versión del motor.
* No convertir el proyecto a otra versión.
* No modificar el render pipeline.
* No cambiar configuraciones generales sin autorización.
* No activar plugins sin permiso.

## Idioma y nombres

* Las explicaciones deben escribirse en español.
* Los archivos, carpetas, assets, Blueprints, clases, variables y funciones deben nombrarse en inglés.
* No usar espacios en nombres.
* Usar nombres cortos, claros y descriptivos.
* Usar `_` para separar palabras cuando sea necesario.
* No traducir nombres técnicos de Unreal Engine.

Ejemplos correctos:

* `BP_Player`
* `BP_Enemy`
* `BP_Platform_Abilities`
* `Combat_System`
* `Camera_Manager`
* `Double_Jump`
* `Can_Use`
* `Has_Double_Jump`

Ejemplos incorrectos:

* `Personaje Principal`
* `Sistema de Combate`
* `Blueprint Movimiento Del Jugador`
* `FunctionToCheckIfThePlayerCanUseDoubleJump`

## Prefijos

Usar prefijos simples y consistentes:

* `BP_` para Blueprint Classes.
* `BPC_` para Actor Components.
* `BPI_` para Blueprint Interfaces.
* `WBP_` para Widgets.
* `ABP_` para Animation Blueprints.
* `BT_` para Behavior Trees.
* `BB_` para Blackboards.
* `E_` para Enums.
* `S_` para Structs.
* `DT_` para Data Tables.
* `DA_` para Data Assets.
* `M_` para Materials.
* `MI_` para Material Instances.
* `T_` para Textures.
* `SM_` para Static Meshes.
* `SK_` para Skeletal Meshes.
* `A_` para Audio assets.

No crear prefijos nuevos sin necesidad.

## Modo Plan

Cuando estés en modo `Plan`:

* No modificar archivos ni assets.
* Analizar primero la estructura existente.
* Revisar los Blueprints relacionados.
* Identificar clases padre, componentes, interfaces y dependencias.
* Explicar el plan en español.
* Indicar qué archivos o assets serían creados o modificados.
* Describir los nodos, variables y funciones necesarias.
* Explicar los riesgos o posibles conflictos.
* Mantener el plan limitado a lo solicitado.
* No asumir que el proyecto está vacío.
* No proponer una reconstrucción completa si puede ampliarse el sistema existente.
* Esperar una orden explícita antes de implementar.

## Modo Build

Cuando estés en modo `Build`:

* Revisar primero los archivos y assets relacionados.
* Aplicar solamente el plan aprobado o la solicitud explícita.
* Realizar cambios pequeños y reversibles.
* No modificar sistemas que no estén relacionados.
* No agregar funcionalidades adicionales.
* No cambiar nombres existentes sin autorización.
* No borrar ni mover assets.
* No reemplazar sistemas funcionales sin permiso.
* Verificar errores después de cada cambio importante.
* Informar qué archivos o assets fueron creados o modificados.
* Informar qué pruebas fueron realizadas.
* Informar cualquier paso manual pendiente dentro de Unreal Editor.

## Reglas para Blueprints

* Blueprints es el sistema principal del proyecto.
* Preferir Blueprints antes que C++ cuando la tarea pueda resolverse de forma clara y segura.
* No crear una versión C++ de un sistema Blueprint sin autorización.
* No duplicar variables, funciones, eventos o componentes existentes.
* Revisar el Blueprint antes de agregar nuevos nodos.
* Mantener los gráficos organizados y legibles.
* Usar funciones para separar lógica reutilizable.
* Usar macros solamente cuando sean realmente necesarias.
* Evitar gráficos excesivamente grandes.
* Evitar cadenas innecesarias de `Cast`.
* Evitar usar `Event_Tick` cuando un evento o timer pueda resolverlo mejor.
* No utilizar `Delay` como solución permanente para problemas de inicialización.
* No crear managers o singletons innecesarios.
* No inventar nodos, funciones, propiedades o APIs.
* Toda solución debe existir y ser compatible con Unreal Engine `5.3.2`.

## Modificación de Blueprints

Los archivos `.uasset` son assets binarios.

* No editar directamente el contenido binario de archivos `.uasset`.
* No abrir un `.uasset` como texto para modificarlo.
* No reemplazar bytes ni intentar reconstruir un `.uasset` manualmente.
* No afirmar que un Blueprint fue modificado si no se pudo verificar dentro de Unreal Editor.

Los Blueprints solo pueden modificarse mediante:

* Unreal Editor.
* APIs oficiales del editor.
* Python dentro de Unreal Editor.
* Editor Utility Blueprints.
* Editor Utility Widgets.
* Plugins de editor autorizados.
* Herramientas C++ de editor autorizadas.
* Texto de nodos compatible con el portapapeles de Unreal, cuando sea seguro.

Si no existe una herramienta para modificar el Blueprint automáticamente:

* Explicar claramente la limitación.
* Proporcionar la secuencia exacta de nodos.
* Indicar nombres de nodos, pines y conexiones.
* No fingir que el asset fue modificado.
* No intentar editar el `.uasset` directamente.

## Código C++

Usar C++ solamente cuando:

* Sea solicitado explícitamente.
* Blueprints no pueda resolver la tarea de forma segura.
* Sea necesario crear una herramienta de editor.
* Sea necesario exponer funcionalidad a Blueprints.

Reglas:

* Mantener el código simple.
* Respetar Unreal Engine `5.3.2`.
* No usar APIs inexistentes o de versiones posteriores.
* No crear arquitecturas complejas innecesarias.
* No modificar módulos sin autorización.
* No agregar dependencias sin permiso.
* Exponer a Blueprints solamente lo necesario.
* No reemplazar sistemas Blueprint existentes automáticamente.

## Seguridad

* No modificar archivos sin una solicitud explícita.
* No borrar, renombrar ni mover archivos existentes.
* No realizar cambios masivos.
* No instalar plugins ni paquetes sin permiso.
* No modificar el archivo `.uproject` sin permiso.
* No modificar `Config` sin permiso.
* No modificar `Plugins` sin permiso.
* No modificar `Source` sin permiso cuando la tarea sea solamente Blueprint.
* No modificar `Binaries`.
* No modificar `DerivedDataCache`.
* No modificar `Intermediate`.
* No modificar `Saved`.
* No modificar archivos generados automáticamente.
* No ejecutar packaging completo sin autorización.
* No realizar `commit`, `merge`, `rebase`, `push` o `reset` automáticamente.
* Se permite usar `git_status` y `git_diff` para inspección.
* No ocultar warnings o errores.
* Explicar la causa de cada warning relevante.
* No asumir que un cambio funciona sin verificarlo.

## Inspección del Proyecto

Antes de crear algo nuevo:

1. Buscar si ya existe un sistema similar.
2. Revisar la carpeta correspondiente.
3. Revisar el Blueprint padre.
4. Revisar componentes existentes.
5. Revisar interfaces y event dispatchers.
6. Revisar variables y funciones.
7. Confirmar que no se duplicará lógica.
8. Proponer el cambio mínimo necesario.

## Organización

Mantener una estructura clara dentro de `Content`.

Ejemplo:

```text
Content/
    Characters/
        Player/
        Enemies/
    Combat/
    Abilities/
    Animation/
    Cameras/
    Cinematics/
    Maps/
    UI/
    Audio/
    Materials/
    Blueprints/
```

No reorganizar carpetas existentes sin autorización.

No crear carpetas nuevas para un único asset si no son necesarias.

## Estado Actual

El proyecto utiliza Unreal Engine `5.3.2`.

El trabajo actual se concentra principalmente en:

* Blueprints.
* Habilidades de movimiento.
* Sistemas del jugador.
* Sistemas de combate.
* Organización de lógica mediante funciones.
* Reutilización de sistemas existentes.

Uno de los Blueprints principales es:

```text
BP_Platform_Abilities
```

Antes de modificar este Blueprint:

* Revisar sus variables existentes.
* Revisar sus funciones.
* Revisar cómo se consulta cada habilidad.
* No duplicar habilidades existentes.
* Mantener las funciones booleanas simples.
* Conectar cada resultado con su variable correspondiente.
* No agregar lógica adicional sin solicitarla.

## Resultado Esperado

Cada tarea debe terminar con un resumen en español que indique:

* Qué se analizó.
* Qué se modificó.
* Qué archivos o assets fueron afectados.
* Qué quedó pendiente.
* Qué debe verificarse dentro de Unreal Editor.
* Qué errores o warnings fueron encontrados.

Esperar instrucciones explícitas antes de implementar sistemas nuevos.
