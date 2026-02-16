# Especificación de Requisitos de Software
## Proyecto: E-commerce Academia de Danza Árabe

### 1. Introducción
Este documento detalla los requisitos técnicos y funcionales para el desarrollo de una plataforma web integral para la Academia de Danza. El sistema tiene el doble propósito de profesionalizar la venta de artículos especializados (velos, crótalos, faldas, etc.) y servir como punto de contacto digital y branding para la institución.

### 2. Alcance del Sistema
El software abarcará desde la presentación pública de la academia (Landing Page, Galería) hasta el ciclo completo de comercio electrónico (Catálogo, Carrito, Pagos, Órdenes), incluyendo un panel administrativo para la gestión de inventario ,pedidos y alumnos inscritos.

---

### 3. Requisitos Funcionales (RF)
A continuación, se enlistan las funciones específicas que el sistema debe proveer a partir las características a implementar:

#### Landing page para visualizar a la academia.

* **RF-01 Visualización de Identidad Institucional:** El sistema deberá permitir la visualización de la propuesta de valor de la academia en la página principal, integrando elementos multimedia y contenido textual descriptivo.

* **RF-02 Visualización de proximos eventos:** El sistema deberá permitir la visualización de proximos eventos de la academia.

* **RF-03 Visualización de Mision y Visión:** El sistema deberá permitir la visualización de la misión y visión de la academia acompañado de elementos multimendia.

* **RF-04 Localización y Contacto:** El sistema deberá mostrar la ubicación física (mapa), horarios de atención y canales de contacto directo para facilitar la conversación de visitantes a alumnos.

#### Sección de galeria

* **RF-05 Gestión de galeria :** El sistema deberá contar con una sección de galeria donde el administrador podrá subir,editar o eliminar contenido multimedia con texto descriptivo.

* **RF-06 Visualización Pública de Galería:** El sistema deberá presentar a los usuarios visitantes las imágenes y descripciones gestionadas por el administrador de forma organizada y estética.

#### Sección de tienda

##### Carrito de compra

* **RF-07 Gestión de Selección de Productos:** El sistema deberá permitir al usuario agregar, modificar cantidades y eliminar artículos del carrito de compras en cualquier momento antes de finalizar la transacción.

* **RF-08 Persistencia del Carrito de Compras:** El sistema deberá garantizar que los artículos seleccionados permanezcan almacenados en la sesión del usuario (mediante LocalStorage o base de datos), permitiendo que la información se mantenga disponible incluso si el usuario refresca la página o cierra la sesión del navegador.

* **RF-09 Sincronización de Inventario en Carrito:** El sistema deberá validar en tiempo real que la cantidad de artículos en el carrito no exceda el stock disponible reportado en la base de datos.

##### Catálogo dinámico con variantes de producto

* **RF-10 Catálogo de Productos Dinámico:** El sistema deberá presentar una lista organizada de artículos de danza, permitiendo el filtrado por categorías (ej. faldas, velos, accesorios) y la actualización automática de precios y existencias.

* **RF-11 Gestión de Variantes de Producto:** El sistema deberá permitir que un solo producto cuente con múltiples variantes basadas en atributos de talla y color. Cada variante será tratada como una unidad de inventario independiente (SKU).

* **RF-12 Visualización de Disponibilidad por Variante:** Al seleccionar una variante específica (ej. Velo - Color: Oro / Talla: M), el sistema deberá mostrar la disponibilidad real y ajustar el precio de manera dinámica si existe una diferencia entre variantes.

##### Pasarela de pagos segura con generación de facturas.

* **RF-13 Integración de Pasarela de Pagos Segura:** El sistema deberá integrarse con una API de pagos externa (Stripe/Mercado Pago) para procesar transacciones mediante tarjetas de crédito, débito y métodos alternos, garantizando el cumplimiento de estándares de seguridad (PCI DSS) al no almacenar datos sensibles de tarjetas en servidores propios.

* **RF-14 Gestión de Estados de Pago:** El sistema deberá actualizar automáticamente el estado del pedido (Pendiente, Pagado, Cancelado) basándose en la respuesta recibida por la pasarela de pagos en tiempo real.

* **RF-15 Módulo de Facturación Automática:** El sistema deberá permitir al usuario ingresar sus datos fiscales tras la confirmación del pago y generar un comprobante de compra (factura) en formato descargable (PDF), cumpliendo con los requisitos de información del negocio.

#### Sección del Administrador.

##### Panel de administración para control de la academia.

* **RF-16 Gestión de artículos:** El sistema debe permitirle al administrador poder dar de alta articulos para la tienda, asi como realizar actualizaciones o poder eliminarlos del inventario.
* **RF-17 Gestión de pedidos:** El sistema deberá proporcionar al administrador una vista detallada de los pedidos realizados, permitiendo visualizar el estado de los pagos y la información del cliente para la gestión de entregas.

* **RF-18 Gestión de alumnas:** El sistema deberá proporcionar al administrador una vista de las alumnas inscritas en la academia.


##### Notificaciones automáticas por correo electrónico.


* **RF-19 Sistema de Notificaciones Transaccionales:**: El sistema deberá enviar correos electrónicos automáticos a los usuarios en respuesta a eventos clave del ciclo de vida de la compra, tales como:

    * Confirmación de creación de cuenta.

    * Confirmación de recepción de pago.

    * Envío de comprobante de compra (factura).

* **RF-20 Alertas Administrativas:** El sistema deberá notificar al administrador mediante correo electrónico cuando se genere una nueva orden de compra o cuando el stock de una variante de producto llegue a un nivel crítico (definido en las reglas de negocio).


###### Sección de Login

###### Requerimientos Nuevos

##### Registro y manejo de usuarios

* **RF-21 Usuarios para alumnas:** El sistema deberá permitirle a las alumnas de la academia crear su perfil en el sistema, con el cual podran consultar el estatus de sus compras.

* **RF-22 Compras generales:** El sistema deberá de tener la opción de comprar sin ser alumna.

### Requerimientos no funcionales

* **RNF-01 Seguridad** El sistema debe implementar protocolos SSL/TLS (HTTPS) para cifrar la comunicación entre el cliente y el servidor, especialmente en el módulo de checkout.

* **RNF-02 Disponibilidad:** La plataforma debe garantizar un Uptime del 99.5%, asegurando que el catálogo esté disponible para consulta en todo momento.

* **RNF-03 Rendimiento:** El tiempo de carga inicial de la Landing Page y la Galería no debe exceder los 3 segundos en conexiones de banda ancha estándar para evitar el abandono del usuario.

### Reglas de Negocio

* **RN-01:** Debe de haber descuentos para usuarios que sean alumnas.
* **RN-02:** Los usuarios que no sean alumnas no necesitaran crear una cuenta para comprar, su orden sera gestionada con un ID.
* **RN-03:** El sistema NO deberá gestionar en su base de datos las transacciones de tarjetas.
