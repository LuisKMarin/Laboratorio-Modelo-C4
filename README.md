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
¿Dónde termina la responsabilidad de la plataforma logística y dónde comienzan   
las responsabilidades de los sistemas externos?   
R//: La plataforma se encarga de manejar todo lo relacionado con la entrega de los pedidos. Esto incluye asignar los pedidos a los conductores, permitirles ver y actualizar la información, 
registrar cualquier problema que ocurra durante la entrega y guardar la evidencia cuando el pedido sea entregado. Por otro lado, el ERP se encarga de crear los pedidos y manejar la información comercial de la empresa. 
El servicio de mapas se utiliza para todo lo relacionado con los mapas y la ubicación. 
La plataforma simplemente se conecta con estos sistemas cuando necesita obtener o enviar información.


## 2. C4 Nivel 1 - Contexto
## 3. C4 Nivel 2 - Contenedores
## 4. C4 Nivel 3 - Componentes
## 5. C4 Nivel 4 - Código
## 6. Uso y validación de IA
## 7. Auditoría de coherencia
## 8. Conclusiones
