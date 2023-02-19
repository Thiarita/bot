paste
Search...

Laura_Sanchez_0206
 
Advertisement

Guest User
Untitled
A GUEST
NOV 18TH, 2022
18,893
22
NEVER
2
0.68 KB | None |  
   
from discord import app_commands, Intents, Client, Interaction
 
 
class Bot(Client):
    def __init__(self, *, intents: Intents):
        super().__init__(intents=intents)
        self.tree = app_commands.CommandTree(self)
 
    async def setup_hook(self) -> None:
        await self.tree.sync(guild=None)
 
 
bot = Bot(intents=Intents.default())
 
@bot.event
async def on_ready():
    print(f"Conectado como: {bot.user}")
 
@bot.tree.command()
async def givemebadge(interaction: Interaction):
    await interaction.response.send_message("Listo!, espera 24 horas para reclamar la insignia\nPuedes reclamarla aquí: https://discord.com/developers/active-developer")
 
 
bot.run("MTA3Njk0ODIwMjgxNDcxMzg5Nw.G36frn.oWOcCDmRWKfesSkcWaKGEgFobKLdYkWvyvXmgY")
