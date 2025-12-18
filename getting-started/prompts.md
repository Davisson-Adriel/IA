# Prompts Sistema de gestión de motocicletas

Instrucción: Define con claridad la tarea o acción que se desea que el modelo realice.

Contexto: Dependerá del caso de uso; en algunos casos no es necesario, como en una clasificación simple de texto.

Datos de entrada (Input Data): La información que se proporciona al modelo, formateada según el caso de uso.

Indicador de salida (Output Indicator): Especifica el formato de salida esperado, por ejemplo, 'sentiment' en un análisis de sentimientos.

## 1. Registro

**Instrucción:** Registra una nueva motocicleta en la base de datos.

**Contexto:** El sistema debe almacenar toda la información relevante de la motocicleta, incluidos los datos adicionales entregados por el usuario. Si faltan datos obligatorios, el sistema debe solicitar al usuario que los proporcione. Si la motocicleta ya existe, el sistema debe notificar al usuario. Los parametros de kilometraje y año deben ser numeros enteros positivos.

**Datos de entrada:**
- Marca: Yamaha
- Modelo: YZF-R3
- Año: 2021
- Cilindrada: 321 cc
- Kilometraje Actual: 5000 km
- Aceite: Sintético
- Neumáticos: Michelin Pilot Street
- Valor de Compra: 5500.00
- Datos adicionales: Color azul

**Indicador de salida:** Confirmación de registro, solicitud de datos faltantes, notificación de existencia previa o error en los datos.

## 2. Actualización

**Instrucción:** Actualiza la información de una motocicleta existente en la base de datos.

**Contexto:** El sistema debe permitir la actualización de cualquier campo de la motocicleta, incluidos los datos adicionales. Si la motocicleta no existe, el sistema debe notificar al usuario. Los parametros de kilometraje y año deben ser numeros enteros positivos y el kilometraje no puede ser menor al registrado previamente. El ID de la motocicleta es obligatorio para realizar la actualización, y debe ser un número entero positivo.

**Datos de entrada:**
- ID de la Motocicleta: 12345
- Parametros a actualizar:
  - Kilometraje Actual: 6000 km
  - Aceite: Semisintético
  - Datos adicionales: Color rojo

**Indicador de salida:** Confirmación de actualización, solicitud de correcciones o notificación de inexistencia.

## 3. Eliminación

**Instrucción:** Elimina una motocicleta específica de la base de datos.

**Contexto:** El sistema debe eliminar la motocicleta de la base de datos. Si la motocicleta no existe, el sistema debe notificar al usuario. El ID de la motocicleta es obligatorio para realizar la eliminación, y debe ser un número entero positivo. El sistema debe solicitar confirmación antes de proceder con la eliminación, mostrando un resumen de la información de la motocicleta.

**Datos de entrada:**
- ID de la Motocicleta: 12345

**Indicador de salida:** Confirmación de eliminación, solicitud de confirmación o notificación de inexistencia.

- Marca: Yamaha
- Modelo: YZF-R3
- Año: 2021
- Cilindrada: 321 cc
- Kilometraje Actual: 5000 km

## 4. Mantenimiento

**Instrucción:** Programa una tarea de mantenimiento para una motocicleta específica.

**Contexto:** El sistema debe permitir programar mantenimientos, especificando el tipo de mantenimiento, la fecha y cualquier nota adicional. Si la motocicleta no existe, el sistema debe notificar al usuario. El ID de la motocicleta es obligatorio para programar el mantenimiento, y debe ser un número entero positivo. La fecha debe estar en formato AAAA-MM-DD y no puede ser una fecha pasada. El estado predefinido del mantenimiento es "pendiente". El valor del mantenimiento debe ser un número decimal positivo.

Los mantenimientos a seleccionar son:
- Cambio de aceite
- Revisión de frenos
- Inspección general
- Sincronización
- Ajuste de cadena
- Cambio de neumáticos
- Otros

**Datos de entrada:** 
- ID de la Motocicleta: 12345
- Tipo de Mantenimiento: Cambio de aceite
- Fecha: 2024-07-15
- Valor de Mantenimiento: 100.00
- Notas adicionales: Usar aceite sintético

**Indicador de salida:** Confirmación de programación, solicitud de correcciones o notificación de inexistencia.

## 5. Historial de Mantenimientos

**Instrucción:** Consulta el historial de mantenimientos de una motocicleta específica.

**Contexto:** El sistema debe recuperar y mostrar el historial completo de mantenimientos realizados en la motocicleta. Si la motocicleta no existe o no tiene mantenimientos completados, el sistema debe notificar al usuario. El ID de la motocicleta es obligatorio para realizar la consulta, y debe ser un número entero positivo. Los mantenimientos deben mostrarse en orden cronológico y con detalles de fecha y tipo de mantenimiento. Ademas debe incluir el estado del mantenimiento (completado, pendiente, cancelado).

**Datos de entrada:**
- ID de la Motocicleta: 12345

**Indicador de salida:** Historial completo de mantenimientos o notificación de inexistencia o falta de registros.
- 2023-01-10: Cambio de aceite (Completado) Valor: 80.00
- 2023-06-15: Revisión de frenos (Completado) Valor: 50.00

## 6. Consulta

**Instrucción:** Consulta la información de una motocicleta específica en la base de datos.

**Contexto:** El sistema debe recuperar y mostrar toda la información almacenada de la motocicleta, incluidos los datos adicionales. Si la motocicleta no existe, el sistema debe notificar al usuario. El ID de la motocicleta es obligatorio para realizar la consulta, y debe ser un número entero positivo.

**Datos de entrada:**
- ID de la Motocicleta: 12345

**Indicador de salida:** Información completa de la motocicleta o notificación de inexistencia.
- Marca: Yamaha
- Modelo: YZF-R3
- Año: 2021
- Cilindrada: 321 cc
- Kilometraje Actual: 5000 km
- Aceite: Sintético
- Neumáticos: Michelin Pilot Street
- Datos adicionales: Color azul
- Mantenimientos:
  - 2024-07-15: Cambio de aceite (Usar aceite sintético) (Pendiente)

## 7. Cambio de Estado de Mantenimiento

**Instrucción:** Cambia el estado de un mantenimiento programado para una motocicleta específica.

**Contexto:** El sistema debe permitir cambiar el estado de un mantenimiento programado a "completado", "pendiente" o "cancelado", mostrando un listado de mantenimientos programados para seleccionar. Si la motocicleta no existe o no cuenta con mantenimientos programados, el sistema debe notificar al usuario. El ID de la motocicleta es obligatorio para realizar el cambio, y debe ser un número entero positivo. Los mantenimientos deben mostrarse con su fecha, tipo y estado actual. Los estados válidos son: "completado", "pendiente" y "cancelado".

**Datos de entrada:**
- ID de la Motocicleta: 12345
- Mantenimiento a cambiar: 2024-07-15: Cambio de aceite
- Nuevo estado: Completado

**Indicador de salida:** Confirmación de cambio de estado, solicitud de correcciones o notificación de inexistencia o falta de registros.

## 8. Listado de Motocicletas

**Instrucción:** Muestra un listado de todas las motocicletas registradas en la base de datos.

**Contexto:** El sistema debe recuperar y mostrar un listado completo de todas las motocicletas registradas, incluyendo su ID, marca, modelo y año. Si no hay motocicletas registradas, el sistema debe notificar al usuario.

**Datos de entrada:** Ninguno.

**Indicador de salida:** Listado completo de motocicletas o notificación de ausencia de registros.
- ID: 12345, Marca: Yamaha, Modelo: YZF-R3, Año: 2021
- ID: 67890, Marca: Honda, Modelo: CBR500R, Año: 2020

## 9. Consulta personalizada

**Instrucción:** Realiza una consulta personalizada sobre una motocicleta específica.

**Contexto:** El sistema debe permitir al usuario realizar consultas específicas sobre la motocicleta. La respuesta debe ser precisa, usando el historial y datos almacenados, así como también la información especifica del modelo. Si la motocicleta no existe, el sistema debe notificar al usuario. El ID de la motocicleta es obligatorio para realizar la consulta, y debe ser un número entero positivo.

**Datos de entrada:**
- ID de la Motocicleta: 12345
- Consulta: ¿Cuándo fue el último cambio de aceite y qué tipo de aceite se utilizó?

**Indicador de salida:** Respuesta precisa a la consulta o notificación de inexistencia.
- El último cambio de aceite fue el 2023-01-10 y se utilizó aceite sintético.

## 10. Recordatorio de Mantenimiento

**Instrucción:** Envía un recordatorio de mantenimiento para una motocicleta específica.

**Contexto:** El sistema debe enviar un recordatorio al usuario cuando se acerque la fecha de un mantenimiento programado para una motocicleta específica. El recordatorio debe incluir el tipo de mantenimiento, la fecha programada y cualquier nota adicional.

**Datos de entrada:**
- ID de la Motocicleta: 12345
- Fecha actual: 2024-07-10
- Fecha de mantenimiento programado: 2024-07-15

**Indicador de salida:** Recordatorio de mantenimiento.
- Recordatorio: El mantenimiento "Cambio de aceite" para su motocicleta Yamaha YZF-R3 está programado para el 2024-07-15. Nota adicional: Usar aceite sintético.

## 11. Estadísticas de Mantenimiento

**Instrucción:** Proporciona estadísticas de mantenimiento para una motocicleta específica.

**Contexto:** El sistema debe calcular y mostrar estadísticas relevantes sobre los mantenimientos realizados en la motocicleta, como el número total de mantenimientos, el costo total invertido y el mantenimiento más frecuente. Si la motocicleta no existe o no tiene mantenimientos registrados, el sistema debe notificar al usuario. El ID de la motocicleta es obligatorio para realizar la consulta, y debe ser un número entero positivo.

**Datos de entrada:**
- ID de la Motocicleta: 12345

**Indicador de salida:** Estadísticas de mantenimiento o notificación de inexistencia o falta de registros.
- Número total de mantenimientos: 5
- Costo total invertido: 350.00
- Mantenimiento más frecuente: Cambio de aceite (3 veces)

## 12. Consulta personalizada para diagnostico

**Instrucción:** Realiza una consulta personalizada sobre una motocicleta específica y clasifica la respuesta.

**Contexto:** El sistema debe permitir al usuario realizar consultas específicas sobre la motocicleta y clasificar la respuesta en categorías predefinidas. La respuesta debe ser precisa, usando la información suministrada por el usuario, el historial y datos almacenados, así como también la información especifica del modelo. Si la motocicleta no existe, el sistema debe notificar al usuario. El ID de la motocicleta es obligatorio para realizar la consulta, y debe ser un número entero positivo. Las categorías de clasificación son: "Mantenimiento Necesario", "Buen Estado", "Requiere Atención Inmediata".

**Datos de entrada:**
- ID de la Motocicleta: 12345
- Consulta: Mi motocileta esta goteando aceite, ¿qué debo hacer?

**Indicador de salida:** Respuesta precisa a la consulta con clasificación, o notificación de inexistencia.
- Respuesta: Es probable que haya una fuga en el sistema de aceite. Se recomienda llevar la motocicleta a un taller para una inspección completa. Clasificación: Requiere Atención Inmediata.

## 13. Sugerencias de Mantenimiento

**Instrucción:** Proporciona sugerencias de mantenimiento para una motocicleta específica.

**Contexto:** El sistema debe analizar el historial de mantenimientos y el estado actual de la motocicleta para proporcionar sugerencias de mantenimiento preventivo. Si la motocicleta no existe, el sistema debe notificar al usuario. El ID de la motocicleta es obligatorio para realizar la consulta, y debe ser un número entero positivo.

**Datos de entrada:**
- ID de la Motocicleta: 12345
- Kilometraje Actual: 6000 km

**Indicador de salida:** Sugerencias de mantenimiento preventivo o notificación de inexistencia.
- Sugerencias: Se recomienda realizar una revisión general y un ajuste de cadena en los próximos 1000 km.
- Próximo mantenimiento sugerido: Revisión general (Fecha estimada: 2024-08-15)

## 14. Consumo de Combustible

**Instrucción:** Calcula el consumo de combustible de una motocicleta específica.

**Contexto:** El sistema debe calcular el consumo de combustible basado en los datos de kilometraje y galones de combustible utilizados. Si la motocicleta no existe, el sistema debe notificar al usuario. El ID de la motocicleta es obligatorio para realizar la consulta, y debe ser un número entero positivo. Los datos de kilometraje y galones deben ser números decimales positivos

**Datos de entrada:**
- ID de la Motocicleta: 12345
- Kilometraje Recorrido: 300 km
- Galones de Combustible Utilizados: 2.5 galones

**Indicador de salida:** Consumo de combustible calculado o notificación de inexistencia.
- Consumo de Combustible: 120 km/galón

## 15. Registro de Accidentes

**Instrucción:** Registra un accidente para una motocicleta específica en la base de datos.

**Contexto:** El sistema debe almacenar toda la información relevante del accidente, incluidos los daños sufridos. El sistema debe generar las reparaciones necesarias de acuerdo a los daños reportados. Si la motocicleta no existe, el sistema debe notificar al usuario. El ID de la motocicleta es obligatorio para realizar el registro, y debe ser un número entero positivo.

**Datos de entrada:**
- ID de la Motocicleta: 12345
- Fecha del Accidente: 2024-06-20
- Descripción de Daños: Daño en el carenado y rayones en el tanque de combustible

**Indicador de salida:** Confirmación de registro del accidente o notificación de inexistencia.
- Accidente registrado exitosamente para la motocicleta ID 12345.
- Fecha del Accidente: 2024-06-20
- Descripción de Daños: Daño en el carenado y rayones en el tanque de combustible
- Reparaciones sugeridas: Reemplazo del carenado y pintura del tanque de combustible.

## 16. Registro de Tecnico Mecánica

**Instrucción:** Registra la ejecución de la tecnico mecanica para una motocicleta específica en la base de datos.

**Contexto:** El sistema debe almacenar la fecha de ejecución de la tecnico mecanica. Si la motocicleta no existe, el sistema debe notificar al usuario. El ID de la motocicleta es obligatorio para realizar el registro, y debe ser un número entero positivo.

**Datos de entrada:**
- ID de la Motocicleta: 12345
- Fecha de Ejecución de la Técnico Mecánica: 2024-06-25

**Indicador de salida:** Confirmación de registro de la técnico mecánica o notificación de inexistencia.
- Técnico mecánica registrada exitosamente para la motocicleta ID 12345.
- Fecha de Ejecución de la Técnico Mecánica: 2024-06-25

## 17. Notificación anual de tecnico mecánica

**Instrucción:** Envía una notificación anual para realizar la técnico mecánica de una motocicleta específica.

**Contexto:** El sistema debe enviar una notificación al usuario cuando se acerque la fecha anual para realizar la técnico mecánica de una motocicleta específica. La notificación debe incluir la fecha de la última técnico mecánica y la recomendación de realizarla nuevamente antes de la fecha anual.

**Datos de entrada:**
- ID de la Motocicleta: 12345
- Fecha actual: 2024-06-20
- Fecha de la última Técnico Mecánica: 2023-06-25

**Indicador de salida:** Notificación anual de técnico mecánica.
- Notificación: La técnico mecánica para su motocicleta Yamaha YZF-R3 fue realizada el 2023-06-25. Se recomienda realizarla nuevamente antes del 2024-06-25.

## 18. Registro de seguro SOAT

**Instrucción:** Registra el seguro SOAT para una motocicleta específica en la base de datos.

**Contexto:** El sistema debe almacenar la fecha de compra del seguro SOAT, así como la compañía aseguradora. Si la motocicleta no existe, el sistema debe notificar al usuario. El ID de la motocicleta es obligatorio para realizar el registro, y debe ser un número entero positivo.

**Datos de entrada:**
- ID de la Motocicleta: 12345
- Fecha de Compra del Seguro SOAT: 2024-06-15
- Compañía Aseguradora: Seguros Mundial

**Indicador de salida:** Confirmación de registro del seguro SOAT o notificación de inexistencia.
- Seguro SOAT registrado exitosamente para la motocicleta ID 12345.
- Fecha de Compra del Seguro SOAT: 2024-06-15
- Compañía Aseguradora: Seguros Mundial

## 19. Notificación de vencimiento de seguro SOAT

**Instrucción:** Envía una notificación de vencimiento del seguro SOAT para una motocicleta específica.

**Contexto:** El sistema debe enviar una notificación al usuario cuando se acerque la fecha de vencimiento del seguro SOAT de una motocicleta específica. La notificación debe incluir la fecha de vencimiento y la recomendación de renovarlo antes de dicha fecha.

**Datos de entrada:**
- ID de la Motocicleta: 12345
- Fecha actual: 2024-06-10
- Fecha de Vencimiento del Seguro SOAT: 2024-06-15

**Indicador de salida:** Notificación de vencimiento del seguro SOAT.
- Notificación: El seguro SOAT para su motocicleta Yamaha YZF-R3 vence el 2024-06-15. Se recomienda renovarlo antes de dicha fecha.

## 20. Calculadora de depreciación

**Instrucción:** Calcula la depreciación según el valor de compra y el año de una motocicleta específica. Siguiendo la siguiente formula:

- Depreciación Anual = Valor de Compra / (Año Actual - Modelo Año)

**Contexto:** El sistema debe calcular la depreciación anual de la motocicleta basándose en su valor de compra y el año actual. Si la motocicleta no existe, el sistema debe notificar al usuario. El ID de la motocicleta es obligatorio para realizar el cálculo, y debe ser un número entero positivo. El valor de compra debe ser un número decimal positivo y el año debe ser un número entero positivo.

**Datos de entrada:**
- ID de la Motocicleta: 12345
- Valor de Compra: 5500.00
- Modelo Año: 2021
- Año Actual: 2024

**Indicador de salida:** Depreciación anual calculada o notificación de inexistencia.
- Depreciación Anual: 1833.33
- Valor Actual Estimado: 3666.67

## 21. Registro de Accesorios

**Instrucción:** Registra un accesorio para una motocicleta específica en la base de datos.

**Contexto** : El sistema debe almacenar toda la información relevante del accesorio, incluidos el nombre, la descripción y el precio. Si la motocicleta no existe, el sistema debe notificar al usuario. El ID de la motocicleta es obligatorio para realizar el registro, y debe ser un número entero positivo. El precio del accesorio debe ser un número decimal positivo.

**Datos de entrada:**
- ID de la Motocicleta: 12345
- Nombre del Accesorio: Maletero
- Descripción: Maletero de 30 litros para Yamaha YZF-R3
- Precio: 150.00

**Indicador de salida:** Confirmación de registro del accesorio o notificación de inexistencia.
- Accesorio registrado exitosamente para la motocicleta ID 12345.

## 22. Listado de Accesorios

**Instrucción:** Muestra un listado de todos los accesorios registrados para una motocicleta específica.

**Contexto:** El sistema debe recuperar y mostrar un listado completo de todos los accesorios registrados para la motocicleta, incluyendo su ID, nombre, descripción y precio. Si no hay accesorios registrados, el sistema debe notificar al usuario. El ID de la motocicleta es obligatorio para realizar la consulta, y debe ser un número entero positivo.

**Datos de entrada:**
- ID de la Motocicleta: 12345

**Indicador de salida:** Listado completo de accesorios o notificación de ausencia de registros.
- ID: 1, Nombre: Maletero, Descripción: Maletero de 30 litros para Yamaha YZF-R3, Precio: 150.00
- ID: 2, Nombre: Soporte para teléfono, Descripción: Soporte universal para teléfono móvil, Precio: 20.00

## 23. Eliminación de Accesorios

**Instrucción:** Elimina un accesorio específico de una motocicleta en la base de datos.

**Contexto:** El sistema debe eliminar el accesorio de la base de datos. Si el accesorio no existe o la motocicleta no tiene accesorios registrados, el sistema debe notificar al usuario. 
El sistema debe mostrar un listado de accesorios registrados para que el usuario pueda seleccionar el accesorio a eliminar. El sistema debe solicitar confirmación antes de proceder con la eliminación, mostrando un resumen de la información del accesorio. El ID de la motocicleta es necesario para identificar a qué motocicleta pertenece el accesorio. El ID del accesorio se extraerá de la selección del usuario y debe ser un número entero positivo.

**Datos de entrada:**
- ID de la Motocicleta: 12345
- ID del Accesorio: 1

**Indicador de salida:** Confirmación de eliminación, solicitud de confirmación o notificación de inexistencia.
- Accesorio eliminado exitosamente para la motocicleta ID 12345.
- ID: 1, Nombre: Maletero, Descripción: Maletero de 30 litros para Yamaha YZF-R3, Precio: 150.00

## 24. Agendamiento de lavado

**Instrucción:** El sistema debe permitir agendar un servicio de lavado para una motocicleta específica.

**Contexto:** El sistema debe almacenar la fecha del servicio de lavado, así como cualquier nota adicional. Si la motocicleta no existe, el sistema debe notificar al usuario. El ID de la motocicleta es obligatorio para agendar el servicio, y debe ser un número entero positivo. La fecha y hora deben estar en formato AAAA-MM-DD y no pueden ser una fecha pasada. El estado predefinido del servicio de lavado es "pendiente".

**Datos de entrada:**
- ID de la Motocicleta: 12345
- Fecha del Servicio: 2024-07-20
- Nota Adicional: Lavado completo exterior y grafitado de llantas

**Indicador de salida:** Confirmación de agendamiento, solicitud de correcciones o notificación de inexistencia.
- Servicio de lavado agendado exitosamente para la motocicleta ID 12345.

## 25. Notificación de servicio de lavado

**Instrucción:** Envía una notificación al usuario cuando se acerque la fecha del servicio de lavado agendado.

**Contexto:** El sistema debe enviar una notificación al usuario cuando se acerque la fecha del servicio de lavado agendado para una motocicleta específica. La notificación debe incluir la fecha del servicio y cualquier nota adicional.

**Datos de entrada:**
- ID de la Motocicleta: 12345
- Fecha Actual: 2024-07-15
- Fecha del Servicio: 2024-07-20

**Indicador de salida:** Notificación de servicio de lavado.
- Notificación: El servicio de lavado para su motocicleta Yamaha YZF-R3 está agendado para el 2024-07-20. Nota: Lavado completo exterior y grafitado de llantas.

## 25. Actualización automatica de estado para mantenimientos

**Instrucción:** Actualiza automáticamente el estado de los mantenimientos programados según la fecha actual.

**Contexto:** El sistema debe verificar la fecha actual y actualizar el estado de los mantenimientos programados a "No Realizado" de forma automatica si la fecha actual es posterior a la fecha programada. El sistema debe verificar que el estado del mantenimiento sea "Pendiente" antes de realizar la actualización. El ID de la motocicleta es obligatorio para realizar la actualización, y debe ser un número entero positivo.

**Datos de entrada:** 
- ID de la Motocicleta: 12345
- Fecha Actual: 2024-07-15
- Fecha del Servicio: 2024-07-14

**Indicador de salida:** Actualización automatica del estado del mantenimiento a "No Realizado" y notificación al usuario de la actualización.
- El "Cambio de aceite" programado para el 2024-07-14 no fue realizado. El estado ha sido actualizado a "No Realizado".

## 27. Renovación del SOAT

**Instrucción:** Registra la renovación del seguro SOAT para una motocicleta específica en la base de datos.

**Contexto:** El sistema debe actualizar la fecha de compra del seguro SOAT y la compañía aseguradora. Si la motocicleta no existe, el sistema debe notificar al usuario. El ID de la motocicleta es obligatorio para realizar la renovación, y debe ser un número entero positivo. La nueva fecha de vencimiento del SOAT corresponde a un año despues de la fecha actual. 

**Datos de entrada:**
- ID de la Motocicleta: 12345
- Fecha Actual: 2024-12-1
- Compañia Aseguradora: Seguros Mundial

**Indicadore de salida:** Confirmación de renovación del seguro SOAT o notificación de inexistencia.
- Seguro SOAT renovado exitosamente para la motocicleta ID 12345.
- Nueva Fecha de Vencimiento del Seguro SOAT: 2025-12-1












