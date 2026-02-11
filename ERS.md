# Especificación de Requisitos de Software (ERS)
## Proyecto: E-commerce Academia de Danza Árabe

### 1. Introducción
Este documento detalla los requisitos para el desarrollo de una plataforma web integral. El sistema busca profesionalizar la venta de artículos de danza (velos, crótalos, faldas, etc.) y optimizar la gestión de inventario de la academia, además de contar con un landing page para familiarizarse con la academia.

### 2. Alcance del Sistema
El software permitirá a los usuarios navegar por un catálogo, gestionar un carrito de compras y realizar pagos seguros. Para el administrador, proporcionará herramientas de gestión de stock, variantes de producto y control de pedidos.

### 3. Requisitos Funcionales (RF)
Los requisitos funcionales definen las acciones que el sistema debe ser capaz de realizar:

* **RF-01 Gestión de Productos:** El sistema permitirá crear, leer, actualizar y eliminar (CRUD) artículos de danza árabe.
* **RF-02 Sistema de Variantes:** El sistema permitirá asignar múltiples variantes a un solo producto (ej. Velo de seda en colores: Rojo, Azul, Esmeralda), cada una con su stock independiente.
* **RF-03 Carrito de Compras:** Los clientes podrán agregar productos, modificar cantidades y persistir su selección durante la sesión.
* **RF-04 Pasarela de Pagos:** Integración segura para procesar transacciones mediante tarjetas de crédito/débito.
* **RF-05 Gestión de Pedidos:** El sistema generará una orden de compra tras un pago exitoso, notificando al administrador y al cliente.
* **RF-06 Autenticación de Usuarios:** Registro e inicio de sesión seguro para clientes (historial de compras) y administradores (panel de control).

### 4. Requisitos No Funcionales (RNF)
Definen las propiedades y restricciones del sistema:

* **RNF-01 Disponibilidad:** El sistema deberá estar desplegado en la nube con un tiempo de actividad del 99.9%.
* **RNF-02 Rendimiento:** El tiempo de carga de la página de inicio debe ser inferior a 2 segundos (optimización de imágenes y SSR).
* **RNF-03 Seguridad:** Uso de protocolos HTTPS y encriptación de datos sensibles. No se almacenarán datos de tarjetas en servidores propios.
* **RNF-04 Diseño Responsivo:** La interfaz debe ser "Mobile First", adaptándose a cualquier tamaño de pantalla.

### 5. Reglas de Negocio
* **RN-01:** No se permitirá la compra de artículos cuyo stock sea igual a cero.
* **RN-02:** Los precios de los productos deben mostrarse en Pesos Mexicanos (MXN).
* **RN-03:** Una orden solo se marca como "Pagada" tras la confirmación exitosa de la pasarela de pagos.
