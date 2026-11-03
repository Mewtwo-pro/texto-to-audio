
### Paso 1: Descargar el binario de Piper

Actualmente, la forma más sencilla y directa en distribuciones de Linux (como Linux Mint) es descargar el binario compilado listo para usar desde su repositorio oficial de GitHub.
    
```
wget https://github.com/rhasspy/piper/releases/download/2023.11.14-2/piper_linux_x86_64.tar.gz
```

Descomprime el archivo descargado
```
tar -xvf piper_linux_x86_64.tar.gz
```
### Paso 2: Descargar un modelo de voz en español

Piper funciona descargando archivos de modelos específicos (que constan de un archivo `.onnx` para la red neuronal y un archivo `.onnx.json` con la configuración).
Puedes descargar una voz en español de alta calidad (por ejemplo, la voz española `es_ES-carlfm-medium` o voces en español latinoamericano como `es_MX-ald-medium`) directamente desde sus repositorios de Hugging Face.
Por ejemplo, descarga los dos archivos necesarios para una voz en español de España fluida:

```
wget https://huggingface.co/rhasspy/piper-voices/resolve/v1.0.0/es/es_ES/carlfm/medium/es_ES-carlfm-medium.onnx
wget https://huggingface.co/rhasspy/piper-voices/resolve/v1.0.0/es/es_ES/carlfm/medium/es_ES-carlfm-medium.onnx.json

```
### Paso 3: Usar Piper para generar audio o hablar

una vez que tienes el binario de Piper y los archivos del modelo en una misma carpeta, puedes convertir texto a audio de las siguientes maneras:

```
echo "Hola Manuel, esta es una prueba utilizando la voz en español latinoamericano de México." | ./piper/piper --model es_MX-ald-medium.onnx --output_file prueba_mexico.wav
```
Puedes reproducir el audio generado directamente desde la terminal
```
ffplay prueba_mexico.wav
```
