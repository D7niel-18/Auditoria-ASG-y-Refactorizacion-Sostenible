# Auditoria-ASG-y-Refactorizacion-Sostenible
**Fase 1: Inventario y Dimensión Ambiental (A)**

1. **Medición inicial**. Utiliza herramientas gratuitas como *Website Carbon Calculator* o *Lighthouse* (pestaña de rendimiento en Chrome/Edge) para obtener la huella de carbono estimada por visita.

En mi caso utilice la web llamada Website Carbon para ver el rendimiento que tiene la web que seleccione.

<img width="434" height="391" alt="1" src="https://github.com/user-attachments/assets/ab41153a-8278-405f-ab03-45ef596818a4" />

En este caso la web elegida [autenticodonerkebap.com](https://www.autenticodonerkebap.com/) obtuvo una calificación	D que aproximadamente este sitio web es un 53% más sucio que el resto de páginas.

**2\. Identificación de *Bloatware***. Inspecciona la red (*Network*) en las herramientas de desarrollador del navegador. Identifica los 3 recursos más pesados que se descargan al abrir la web (imágenes sin comprimir, vídeos de fondo, librerías JavaScript pesadas, etc.).

He detectado el uso de imágenes en formato PNG o JPG que no están pasadas a .webp para optimizar la web. 

<img width="271" height="74" alt="2" src="https://github.com/user-attachments/assets/eea3f2eb-b402-44cf-9e20-410e83eb004b" />

También he detectado el uso de distintos scripts que no se utilizan o que dan fallos.

<img width="377" height="103" alt="3" src="https://github.com/user-attachments/assets/fc59d5c1-f88f-4ec0-8436-490db8d8d219" />

También he observado que usan Wix para un sitio tan sencillo haciendo que se ocupe mucho espacio cuando usando html,css y js se ahorran bastante espacio.

<img width="484" height="398" alt="4" src="https://github.com/user-attachments/assets/56c29dd9-32e8-4762-a565-1e62fdaf8db6" />

He usado Wappalyzer para este analisis.

**3\. Análisis**. ¿Crees que la web sufre de "inflación de software"? Justifica tu respuesta.

## **Fase 2: Dimensión Social y Equidad (S)**

**1\. Test de Accesibilidad**. Pasa una herramienta como *WAVE Web Accessibility Evaluation Tool* o el propio *Lighthouse* (pestaña *Accessibility*).

He generado un informe usando Lighthouse y el sitio web pasa la evaluación de métricas web principales.

<img width="434" height="260" alt="5" src="https://github.com/user-attachments/assets/a8d7c70d-2e1e-49f0-8154-c4426383cab3" />

Aunque tiene algo menos de puntuación en la parte de rendimiento ya que hay varias imágenes duplicadas y más grandes de los necesario tambien hay codigo JavaScript duplicado y código antiguo de JavaScript.

 	

<img width="404" height="161" alt="6" src="https://github.com/user-attachments/assets/50c83203-e5f4-4fe3-abdd-005843d47270" />


**2\. Identificación de barreras**. Documenta al menos 2 problemas graves que impidan a personas con diversidad funcional usar la web correctamente (ej. falta de atributos *alt* en imágenes clave, bajo contraste de colores en botones, formularios sin etiquetas).

La página tiene un 98 de puntuación en accesibilidad y el único problema encontrado fue:
<img width="389" height="139" alt="7" src="https://github.com/user-attachments/assets/049dcc8e-7527-4e58-a497-b4f02e7e66c2" />


## **Fase 3: Dimensión de Gobernanza y Ética (G)**

**1\. Transparencia**. ¿Es fácil rechazar las cookies no esenciales o utilizan "patrones oscuros" (Dark Patterns) para forzar al usuario a aceptarlas?

Si, cuando entras a la web te salta una especie de footer diciendo que utiliza cookies puedes ver las opciones de las cookies, rechazarlas o aceptarlas y también ver la política de privacidad.

<img width="492" height="85" alt="8" src="https://github.com/user-attachments/assets/841116ad-f4e5-4106-a0b1-a130d1f17948" />

La propia política de cookies de la web indica que para seguir navegando por nuestro sitio web sin denegar su autorización significa que acepta su uso. Esto es un patrón oscuro clásico expresamente prohibido por el RGPD. El silencio o la continuación de la navegación no son formas válidas de consentimiento ya que puedes seguir navegando por la pagina sin necesidad de aceptar o rechazar las cookies.

**2\. Datos innecesarios**. ¿Pide la web datos personales excesivos en su formulario de contacto o registro?

La web cuenta con un formulario donde solo te piden tu nombre, correo electrónico y el mensaje que quieres enviar. Así que no piden datos personales en exceso.

El formulario de contacto únicamente solicita los datos imprescindibles para responder al usuario, con un checkbox de aceptación de términos y condiciones. La estructura visible indica que se trata de un formulario mínimo sin solicitar datos como teléfono, dirección, fecha de nacimiento, DNI ni ningún otro dato que resultaría excesivo para una simple consulta a un restaurante.

<img width="676" height="441" alt="form" src="https://github.com/user-attachments/assets/576f6638-8353-4ccd-989a-a04b20682435" />


## **Fase 4: Propuesta de Refactorización (Green Coding)**

**¿Qué formatos usarías para sustituir las imágenes actuales (ej. WebP, AVIF)?**

Lo primero que haría es analizar todas las imágenes que tiene el sitio web y las pasaria a .webp ya que webp comprime bastante bien las imagenes (les baja el tamaño) y sigue manteniendo una muy buena calidad

**¿Implementarías Lazy Loading?**

Si, ya que haciendo esto solo cargaremos las imágenes que sean necesarias haciendo que podamos optimizar el sitio web y acelerar la carga inicial.

**¿Qué librerías o scripts externos eliminarías o aplazarías para mejorar la eficiencia del código y reducir el procesamiento en el dispositivo del cliente?**

Trataría de corregir los fallos de los scripts que generar esos fallos y borrar los que no se usan. También no usaría WIX ya que carga muchas cosas innecesarias para una web tan basica asi que la haria usando html,css y javascript para optimizar la web.

**Si optimizamos la web y la carga mucho más rápido, podríamos atraer a muchos más usuarios diarios. ¿Cómo evitarías que este éxito anule el ahorro energético conseguido?**

Esta claro que contra mas personas visiten el sitio web mas carga se le da al servidor haciendo que genere mas calor y por consecuencia mas consumo. En mi caso lo que haria seria encargarme de optimizar muy bien la parte de la web y la parte del servidor escribiendo codigo limpio, borrando scripts que no se usan, quitando elementos que no se usan.
