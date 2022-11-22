Fpay
Contributors: fpay, falabella
Tags: Fpay, woocommerce, payments, payment, Falabella
Requires at least: 4.7
Tested up to: 6.0.2
Stable tag: 2.4.2
Requires PHP: 7.4
License: GPLv2 or later
License URI: https://www.gnu.org/licenses/gpl-2.0.html

== Description ==

Plugin oficial de Fpay.

== Frequently Asked Questions ==

= Recibo un mensaje del tipo FpayWoocommerceError-0## que significa? =

Son códigos que usan para tener una traza de un posible error con el plugin. Estos serán de utilidad al momento de brindarle soporte.

= Recibo un mensaje error "FpayWoocommerceError-001" que significa? =

Este es un problema de relacionado a la autenticación con Fpay. Debe validar y/o volver a configurar las credenciales obtenidas desde el portal Fpay de comercios en la sección Configuración apartado de Credenciales.

== Changelog ==
= 2.5.3 =
* Se mueve la logica que captura alguna excepción del cliente guzzle y se crea una nueva excepción FpayHttpClientException para no tener ligado el paquete a la logica del plugin.
= 2.5.2 =
* Se soluciona el problema de incompatibilidad con otras versiones de la misma dependencia con otros plugins.
* Se agrega el paquete brianhenryie/strauss para sobreescribir el namespace de las dependencias que podrian generar conflictos.

= 2.5.1 =
* Se soluciona un problema por la diferencia de datos que responde la Api de Fpay en Perú.
* Se agrega el metodo sanitize requerido por Wordpress.

= 2.5.0 =
* Se agrega la validación cuando una moneda, pais no son soportados. El plugin no se podrá activar si la tienda NO tiene un pais, moneda soportado por Fpay.
* Se agrega el código de error "FpayWoocommerceError-017" cuando un usuario de la tienda intenta pagar con Fpay y la tienda modifico las configuraciones de moneda y pais soportadas por Fpay.
* Se crea la clase HttpClient la cual es un envoltorio a la clase Client de Guzzle para tener un mejor manejo de los headers y otras configuraciones necesarias para el cliente http del plugin.
* Se construye la clase CountryManager dedica a manejar la lógica relacionada a la configuración de países y monedas que usa el plugin de Fpay.

= 2.4.3 =
* Se solventa un problema que no redirigia correctamente cuando el webhook habia sido llamado previamente.
= 2.4.2 =
* Se agrega el método "sanitize" de Wordpress para las llamadas que vienen de los endpoints en el plugin.
* Se traslada la lógica de entrada de los webhooks a una nueva clase llamada WebhookController.
* Se agrega la clase SessionManager para delegarle la responsabilidad de los datos de sesión usados en el plugin.
* Se incrementa el coverage de las pruebas al 77.17 porcientos.

= 2.4.1 =
* Se soluciona un problema cuando el webhook notificaba al comercio y luego el cliente intentaba volver al comercio no mostraba la ventana de checkout.

= 2.4.0 =
* Se implementa la funcionalidad de N-duplicidad de plugins, esto permitirá tener N-plugins basado en las configuraciones de los archivos .env.

= 2.3.0 =
* Se agregó la funcionalidad para recibir llamadas de pago, cancelado y devoluciones via webhook.

= 2.2.4 =
* Se agregó el medio de pago al resumen del pedido.

= 2.2.3 =
* Para que no haya errores si se usa la url de cancelar cuando la intención ya ha sido pagada. Se optimiza los webhooks de pago exitoso y otros estados, para en cualquier de los dos webhooks se valide el estado de la intención y se reaccione según este.
* Se agrega al mensaje de "Fpay requiere que configure sus credenciales" el mensaje "Clic aquí para configurar.", con un enlace que lleva a la sección de configuraciones del plugin.
* Se separan en diferentes archivos la configuración del service container.
* Se mueve el mensaje 'Ocurrió un error al procesar la transacción con Fpay - ', a dos contantes para tener un mejor control si se desea cambiar.
* Se agrega la validación de la constante 'ABSPATH' a todos los archivos del plugin que implementan por recomendación de la documentación de desarrollo de Woocommerce.

= 2.2.2 =
* Se soluciona problema al mostrar el mensaje de que debe configurarse credenciales correctamente, cuando el plugin no había sido instalado nunca y saltaba un error.
* Se soluciona el problema que al enviar multiples clics al momento de volver al comercio luego de pagar, cancelar o fallar la intención de pago agregaba multiples notas a la orden de manera repetida.
* Se actualiza el readme.txt para la publicación del plugin en la tienda de Wordpress.
* Se actualiza la url de producción para los pagos.
* Se agrega la copia automática del archivo .env para la suit de pruebas desde el archivo bootstrap.

= 2.2.1 =
* Se configura Pest Php como framework de pruebas unitarias.
* Se alcanza un 73.69% de coverage del código.
* Se agrega una nueva excepción para el momento de que falle al consultar una intención de pago.
* Se agrega un mensaje para el administrador que si no ha configurado las credenciales de Fpay debe hacerlo.

= 2.1.1 =
* Se corrige el problema que no agregaba el nombre de Fpay en los detalles de la orden.
* Se alinea el logo de Fpay a la derecha.

= 2.1.0 =
* Se añade la funcionalidad de recibir devoluciones via webhook.

= 2.0.1 =
* Control de errores para shipping address city vacío.

= 2.0.0 =
* Nueva interfaz de administración y redireccionamiento al nuevo Checkout Fpay.

= 0.1.0 =
* Inicio del proyecto.

== Screenshots ==

1. Método de pago Fpay al finalizar la compra.
2. Activar "Fpay" en la pestaña de metodos de pagos en WooCommerce.
3. Clic en "Portal Comercios Fpay" para enlazar su sitio con su cuenta de comercio en Fpay.
4. Página principal de configuración del plugin de Fpay.
