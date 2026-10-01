# Laboratorio - Modelo C4 para un proceso logístico
## Integrantes
- Luis Carlos Marín Mayo
- Jorge Andrés Carvajal Sepúlveda
## 1. Comprensión del problema

            Elemento                                                        Decisión del equipo   
            
                                                               Plataforma de gestión logística de LogiTrack:
    Sistema que se está modelando                Sera una plataforma que permitirá gestionar el proceso de distribución de los pedidos,   
                                                desde que están preparados para ser enviados hasta que son entregados al cliente.      
                                                
                                                Coordinador logístico: Asigna los pedidos a un vehículo y a un conductor disponible.
     Actores principales                        Conductor: Consulta los pedidos que tiene asignados, revisa la información necesaria para realizar las entregas y actualiza su estado.
                                                Cliente: Puede consultar el estado de su pedido.   

                                                ERP: es donde la empresa ya genera los pedidos y administra la información comercial. 
     Sistemas externos                          La plataforma logística debe consultar los pedidos desde allí y posteriormente enviarle información sobre las entregas realizadas.
                                                Servicio externo de mapas y geolocalización: se utilizará para las funciones relacionadas con mapas y ubicación.
  
     Responsabilidad principal                  Gestionar y dar seguimiento al proceso de entrega de los pedidos, desde que están preparados hasta que son entregados al cliente, 
                                                permitiendo realizar asignaciones, actualizar estados, registrar novedades y guardar la evidencia de entrega.

     Información administrada                   Pedidos, vehículos, conductores, asignaciones de pedidos, estados de los pedidos, novedades durante las entregas, evidencias de entrega, 
                                                información de quien recibe el pedido, observaciones, fecha y hora de la entrega.    

                                                El ERP proporciona los pedidos a la plataforma logística.
                                                El coordinador logístico toma los pedidos preparados y los asigna a un vehículo y a un conductor.
                                                El conductor consulta sus pedidos asignados.
                                                El conductor realiza la entrega y va actualizando el estado del pedido.
    Principales interacciones                   Si ocurre algún problema, el conductor registra la novedad correspondiente.
                                                Cuando entrega el pedido, registra la evidencia de entrega, incluyendo fotografía, nombre de quien recibe, observaciones, fecha y hora.
                                                El cliente consulta el estado de su pedido.
                                                La plataforma informa al ERP sobre las entregas que ya fueron realizadas.
                                                La plataforma utiliza el servicio de mapas y geolocalización para las funciones relacionadas con ubicación.  

    
Respondan:    
¿Dónde termina la responsabilidad de la plataforma logística y dónde comienzan las responsabilidades de los sistemas externos?   

R//: La responsabilidad de la plataforma logística termina en todo lo relacionado con la organización y seguimiento de las entregas, como asignar los pedidos, permitir que el conductor los consulte y actualice su estado, 
registrar las novedades y guardar la evidencia de la entrega.

La responsabilidad de los sistemas externos comienza cuando se necesita información o servicios que la plataforma no maneja directamente. El ERP se encarga de generar los pedidos y manejar la información comercial de la empresa, 
mientras que el servicio de mapas se encarga de proporcionar la información relacionada con mapas y ubicación. La plataforma se comunica con estos sistemas para obtener o enviar la información que necesita.



## 2. C4 Nivel 1 - Contexto

![](Imagenes_C4/C4_Nivel_1.svg)


## 3. C4 Nivel 2 - Contenedores

            | Contenedor                    | Responsabilidad                                                                                                                                             | Tecnología propuesta                   | Comunicación                                                                                  |
            | ----------------------------- | ----------------------------------------------------------------------------------------------------------------------------------------------------------- | -------------------------------------- | ----------------            ----------------------------------------------------------------------------- |
            | Aplicación web administrativa | Permite al coordinador gestionar los pedidos, asignar vehículos y conductores y revisar el estado de las entregas.                                          | Aplicación web (React).                | Se comunica con el Backend/API para enviar y consultar información.                           |
            | Aplicación para conductores   | Permite consultar los pedidos asignados, actualizar su estado, registrar novedades y guardar las evidencias de entrega.                                     | Aplicación móvil (Flutter).            | Se comunica con el Backend/API para consultar y actualizar información.                       |
            | Backend/API                   | Se encarga de procesar las solicitudes y manejar la lógica principal del sistema, como pedidos, asignaciones, entregas, novedades e integración con el ERP. | Java con Spring Boot.                  | Se comunica con las aplicaciones, la base de datos, el ERP y el servicio de mapas.            |
            | Base de datos                 | Guarda la información de pedidos, vehículos, conductores, asignaciones, entregas, novedades y evidencias.                                                   | PostgreSQL.                            | Se comunica con el Backend/API, que consulta y guarda la información.                         |
            | Servicio de seguimiento       | Permite manejar la información del estado y ubicación de las entregas.                                                                                      | Funcionalidad interna del Backend/API. | El Backend/API utiliza el servicio externo de mapas cuando necesita información de ubicación. |
            | Servicio de notificaciones    | Se encarga de las notificaciones relacionadas con los pedidos y las entregas.                                                                               | Funcionalidad interna del Backend/API. | El Backend/API             gestiona las notificaciones cuando ocurre alguna acción importante.            |

![](Imagenes_C4/C4_Nivel_2.svg)

Pregunta crítica
¿Qué criterio utilizaron para decidir que un elemento debía ser un contenedor
independiente?

R//: Para decidir qué elementos serían contenedores independientes, tuvimos en cuenta la función que cumple cada uno y si era necesario separarlo de los demás para realizar su trabajo. Por eso elegimos la aplicación web administrativa, la aplicación para conductores, el Backend/API y la base de datos, ya que cada uno cumple una función diferente dentro de la plataforma. En el caso del seguimiento y las notificaciones, consideramos que por ahora pueden manejarse desde el Backend/API, porque no vemos necesario separarlos como servicios independientes para cumplir con lo que solicita el caso.

## 4. C4 Nivel 3 - Componentes
## 5. C4 Nivel 4 - Código
## 6. Uso y validación de IA
## 7. Auditoría de coherencia
## 8. Conclusiones
