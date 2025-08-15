# Online Fruit Store Automation

Automatización para la actualización del catálogo de una tienda online de frutas.  
El sistema procesa imágenes y descripciones enviadas por los proveedores y las sube a un servidor Django, generando un reporte PDF que se envía por correo electrónico.

---

## 📜 Flujo del Proyecto

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

----
## Requerimientos 
Python 3.6+

# Librerías:

pip install pillow requests reportlab


## Entorno necesario:

Servidor Django con endpoints /upload/ y /fruits/.

Base de datos conectada

Servidor SMTP local (localhost).
