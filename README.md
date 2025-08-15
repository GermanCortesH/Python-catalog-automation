# Online Fruit Store Automation

Automatización para la actualización del catálogo de una tienda online de frutas.  
El sistema procesa imágenes y descripciones enviadas por los proveedores y las sube a un servidor Django, generando un reporte PDF que se envía por correo electrónico.

---

## 📝 Introducción

Este proyecto tiene como objetivo automatizar el proceso de actualización del catálogo de frutas de una tienda online.  
Los proveedores envían datos en archivos de imagen (.tiff) y descripciones (.txt). El sistema convierte las imágenes, procesa las descripciones, sube la información al servidor y genera un reporte en PDF que se envía automáticamente al proveedor.  

Este flujo asegura eficiencia y reduce errores en la actualización manual del catálogo, mejorando la experiencia de los usuarios y la gestión interna.

---

## 🎯 Escenario

Imagina que trabajas para una tienda de frutas online y recibes constantemente nuevos productos de tus proveedores. Cada producto viene con:

- Una imagen en formato `.tiff`
- Una descripción en formato `.txt`

La tarea consiste en:

1. Convertir las imágenes a `.jpeg` y ajustar su tamaño.
2. Procesar las descripciones y generar archivos JSON con la información de cada fruta.
3. Subir las imágenes y los datos al servidor Django.
4. Generar un reporte PDF con la información de los productos y su peso total.
5. Enviar un correo electrónico al proveedor con el PDF adjunto.

El objetivo es automatizar este flujo para que sea repetible, confiable y eficiente.

---

## ⚙️ Desarrollo

### Flujo del Proyecto

```plaintext
Proveedor → [Imágenes .tiff + Descripciones .txt]  
         ↓  
  changeImage.py → Convierte a .jpeg (600x400)  
         ↓  
  supplier_image_upload.py → Sube imágenes al servidor  
         ↓  
  run.py → Procesa descripciones y sube JSON con datos de frutas  
         ↓  
  report_email.py + reports.py → Genera reporte PDF con peso total  
         ↓  
  emails.py → Envía email al proveedor con PDF adjunto
