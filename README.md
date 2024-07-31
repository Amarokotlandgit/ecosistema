# ecosistema
import discord
from discord.ext import commands

description="es es una programa vinculamos discord con studio code para lanzar imagenes"

intents=discord.Intents.default()
intents.members=True
intents.message_content=True

bot=commands.Bot(command_prefix='/',description=description,intents=intents)


@bot.event
async def on_ready():
    print(f'logeado como {bot.user}(ID: {bot.user.id}')

@bot.event
async def on_message(message):
    if message.author==bot.user:
        return
    if message.content.lower()=='/plastico':
        with open('plastico.jpg', 'rb') as f:
            picture = discord.File(f)
            await message.channel.send(content='Problema: Los plásticos tardan cientos de años en degradarse, y muchos terminan en los océanos, afectando la vida marina.Reducción:reciclaje:Fomenta el reciclaje de plásticos.Alternativas: Utiliza materiales biodegradables.Reutilización: Promueve el uso de productos reutilizables bolsas, botellas, etc.',file=picture)
    
    elif message.content.lower()=='/Fertilizantes_Quimicos':
        with open('fertilizantes quimicos.jpg', 'rb') as f:
            picture = discord.File(f)
            await message.channel.send(content='Problema: Contaminan el suelo y el agua, afectando la biodiversidad y la salud humana.Agricultura orgánica: Utilizar métodos de cultivo orgánico.Manejo integrado de plagas (MIP): Emplear técnicas de control de plagas más sostenibles.',file=picture)
    
    elif message.content.lower()=='/Desechos_Electrónicos':
        with open('desechos electronicos.jpg', 'rb') as f:
            picture = discord.File(f)
            await message.channel.send(content='Problema: Contienen sustancias tóxicas que pueden filtrarse en el suelo y el agua.Reciclaje: Establecer puntos de recogida y reciclaje de electrónicos.Reparación y reutilización: Promover la reparación de dispositivos y su reuso.',file=picture)

bot.run("")
