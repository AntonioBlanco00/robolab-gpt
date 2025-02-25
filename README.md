# robolab-gpt

Esta es una versión sencilla, hay documentación y videos que enseñan a como añadir funciones que el chat conversacional puede llamar y usar dado el caso. Esta es como usar el chatGPT normal pero en componente: prompt inicial, e intercambio de mensajes y respuestas entre usuario y LLM.

## Configuración de `robolab_gpt`

Para que `robolab_gpt` funcione correctamente, es necesario crear un archivo `.env` y agregar tu clave de OpenAI.

### Pasos para crear el archivo `.env`
1. Ejecuta el siguiente comando para crear el archivo `.env`:
   ```sh
   touch .env
   ```
2. Abre el archivo `.env` con tu editor de texto preferido y agrega la siguiente línea:
   ```env
   OPENAI_API_KEY="tu_clave_aqui"
   ```
3. Guarda los cambios y cierra el archivo.

Ahora `ebo_gpt` estará configurado correctamente para utilizar la API de OpenAI.

## Explicación de las funciones

En primer lugar, en el repo hay un `assistants.txt` donde cada fila es un asistente distinto, los cuales se crean en el playground de openai. A la izquierda está el nombre dado al asistente el cual se usa como parámetro en la función, y la derecha hay que poner el ID que es lo que usará el componente para iniciar la conversación. Sabiendo esto:

1. GPT_setGameInfo(assistantName, userInfo)

Dónde assistantName es el nombre dado al asistente como acabamos de ver.

Y dónde userInfo es simplemente ya el primer mensaje que se le manda al chat, tiene este nombre porque en EBO se usaba el primer mensaje para pasar la información del usuario.

Al llamar a esta función fijas tanto el asistente a usar como el mensaje inicial.

2. GPT_startChat()

Crea la conversación, manda ese primer mensaje, y printa por pantalla la respuesta.

3. GPT_continueChat(message)

Manda el mensaje y sigue con la conversación. 

Existe un código de terminación para terminar el chat, almacenar la conversación y borrar el hilo. Si usas esta función con: message = "03827857295769204" (o el valor o palabra que definas en esta misma función), el chat se terminará y almacenará de forma limpia.
