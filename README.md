from zipfile import ZipFile
import shutil
import os

# Reconfigurar rutas tras el reinicio del entorno
folder_path = "/mnt/data/juanes_web_final"
html_source = "/mnt/data/juanes_fut_combined.html"
html_dest = f"{folder_path}/index.html"

# Crear carpeta de salida
os.makedirs(folder_path, exist_ok=True)

# Copiar el HTML y renombrarlo como index.html
shutil.copyfile(html_source, html_dest)

# Crear ZIP con los archivos necesarios
zip_path = "/mnt/data/juanes_web_final.zip"
with ZipFile(zip_path, 'w') as zipf:
    zipf.write(html_dest, arcname="index.html")

zip_path

