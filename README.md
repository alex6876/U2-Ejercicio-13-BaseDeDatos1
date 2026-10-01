# Ejercicio 11 — Base de Datos de Gestión de Alquiler de Vehículos (Rent a Car)



Proyecto enfocado en la modelación Entidad-Relación (DER / MER) e implementación de base de datos relacional para un sistema de alquiler de vehículos (rent-a-car), administrando sucursales, vehículos de la flota, clientes, contratos de alquiler y reporte de siniestros.

---

## Descripción

El sistema modela una estructura de datos relacional para la gestión operativa y comercial de una empresa de alquiler de autos. Permite catalogar la red de sucursales operativas, administrar el parque automotor asignado a cada sede, registrar la información de los clientes habilitados para conducir, formalizar los contratos de alquiler detallando puntos y tiempos de retiro y devolución, e historializar las incidencias o siniestros acontecidos durante los períodos de renta.

---

## Funcionalidades e Implementación

### Entidades y Atributos

* Sucursal:


* id_codigo sucursal: Clave primaria identificadora de la sede o filial.


* nombre: Denominación o nombre comercial de la sucursal.


* dirección: Ubicación física o domicilio de la sede.


* ciudad: Ciudad donde radica la sucursal.


* codigo postal: Código postal correspondiente a la ubicación.




* Vehiculo:


* id_Patente: Clave primaria única identificadora del vehículo.


* numero_chasis: Número de identificación del chasis (VIN).


* marca: Marca del automóvil.


* modelo: Modelo de la unidad.


* categoria: Gama o categoría del vehículo (ej. económico, SUV, premium).


* kilometraje: Lectura actual del odómetro.




* Cliente:


* id_DNI passaporte: Clave primaria identificadora del cliente.


* nombre: Nombre completo del cliente.


* teléfono: Número telefónico de contacto.


* tarjeta crédito: Registro de tarjeta de crédito como garantía o medio de pago.


* licencia conducir: Número de registro o carnet de conducir.


* fecha vencimiento licencia: Fecha de expiración de la licencia de habilitación.




* Contrato Alquiler:


* id_Contrato: Clave primaria única del contrato de alquiler.


* fecha-hora retiro: Fecha y hora programada o real de entrega de la unidad.


* fecha-hora devolución prevista: Fecha y hora estipulada para el retorno.


* fecha-hora devolucion real: Fecha y hora efectiva en que se restituye el vehículo.




* Siniestro:


* id_Siniestro: Clave primaria identificadora del reporte de siniestro.


* fecha: Fecha y/o hora de ocurrencia del incidente.


* descripción: Detalle e informe de los daños o sucesos acontecidos.


* costo estimado: Monto estimado para la reparación de los daños.


* compañía aseguradora: Entidad aseguradora que interviene en la cobertura.





---

## Relaciones del Modelo

1. Sucursal ↔ Vehiculo (Relación 1:N):


* Una sucursal posee múltiples vehículos asignados a su flota base, pero cada vehículo pertenece a una única sucursal de origen/radicación.




2. Cliente ↔ Contrato Alquiler (Relación 1:N):


* Un cliente puede celebrar múltiples contratos de alquiler a lo largo del tiempo, pero cada contrato se suscribe a nombre de un único cliente titular.




3. Sucursal ↔ Contrato Alquiler (Retiro y Devolución - Relaciones 1:N):


* Una sucursal puede registrar múltiples contratos como punto de retiro (origen) y/o como punto de devolución (destino) de los vehículos.




4. Vehiculo ↔ Contrato Alquiler (Relación 1:N):


* Un vehículo puede ser alquilado en múltiples contratos en distintas fechas, pero cada contrato de alquiler involucra a un único vehículo específico.




5. Contrato Alquiler ↔ Siniestro (Relación 1:N):


* Durante la vigencia de un contrato de alquiler se pueden registrar uno o más siniestros o incidentes. Cada siniestro queda vinculado a un único contrato de renta.
