# Hateful memes by Facebook AI 💻
Los datos se pueden descargar [aquí](https://drive.google.com/drive/folders/1ff0l1GXazCml-kIqkL2RnvdaRCxpYYcE?usp=sharing).

La carpeta `img` contiene todas las imágenes. Nos interesará usar el archivo json `train.jsonl` para entrenar a nuestro modelo. Recuerde que los archivos json se convierten
fácilmente a diccionarios en Python. Cada línea del archivo tiene el siguiente formato: `{"id":1,"img":"img\/1.png","label":0,"text":"its their character not their color that matters"}`, donde:
- el `id` y _path_ de cada imagen coinciden,
- una label de 0 significa que el meme no es ofensivo, mientras que 1 significa que sí,
- y `text` contiene el texto que aparece en el meme.

¡Mucha suerte!
