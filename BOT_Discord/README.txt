1- Crea una carpeta para el ejercicio del bot

2- Inicia el NodeJs

3- Ejecuta el comando "npm init --yes" (el package.JSON debe estar dentro de la carpeta Bot)

4- "npm install discord.js" (para instalar las dependencias de discord)

5- Dentro de la carpeta discord que creaste , crea un archivo que termine en .js

6- "npm install axios" (Librerias)

7- Ejecuta el comando "npm install dotenv" (creacion de varibales de amnbiente)

8- En el Javascript:

 -- Estos son los privilegios del bot --
require('dotenv').config();
const {Client, GatewayIntenBits} = require ('discord.js')
const axios = require('axios')
const cliente = new Client ({intents:[
	GatewayIntentBits.Guilds,
	GatewayIntentBits.GuildMessages,
	GatewayIntentBits.MessagesContent
]});

client.on('ready'), ()=>{
	console.log('El bot esta listo');
})


--esto es para enviar mensajes al bot para que los muestre en el chat--
client.on('messageCreate', async(message)=>{
	if(message.content === 'hola'){
		message.reply({
			content:'Bienvenido a nuestro canal'
		})

	}else if(message.content === 'quote'){
		let resp = await axios.get('https://api.quotable.io/ramdon'); //esta api genera frases!!
		const quote = resp.data.content;
		message.reply({
			content:quote,
	 

})

client.login(process.env.DISCORD_BOT_ID); //metodopropiodediscord



9- Crear un archivo nuevo dentro de la carpeta de discord  que se llame ".env"

10- Ve al archivo .env: DISCORD_BOT_ID= Copia y pega el token del BOT

11- Por ultimo coloca el comando "ini npm run start" para inicializar el bot

