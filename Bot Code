import discord
from discord.ext import commands
import requests

headers = {'Accept': 'application/json'}


TOKEN = ''

client = commands.Bot(command_prefix='?')

def uuid(name):
    data = requests.get(
        f"https://api.mojang.com/users/profiles/minecraft/%7Bname%7D", headers=headers)
    uuid = data.json()
    return uuid



@client.event
async def onready():
    print(f'{client.user} has connected to Discord!')


@client.command()
async def say(ctx, msg):
    await ctx.send(msg)

@client.command()
async def sayas(ctx, user, *agrs):
    await ctx.send(f"{user} said '{' '.join(agrs)}'")

@client.command()
async def spam(ctx, num, *agrs):
    for i in range(0,int(num)):
        await ctx.send(' '.join(agrs))

@client.command()
async def spaminline(ctx, num, *agrs):
    msg = []
    for  in range(0, int(num)):
        agr = ' '.join(agrs)
        msg.append(agr)
    await ctx.send(' '.join(msg))
    msg = []

@client.command()
async def mcskin(ctx, name):
    skins = dict(uuid(name))
    skin = skins.get('id')
    await ctx.send(f'https://crafatar.com/skins/%7Bskin%7D%27)

@client.command()
async def skin(ctx, name):
    ied = uuid(name)
    ied = ied.get('id')
    await ctx.send(f'https://crafatar.com/renders/body/%7Bied%7D%27)
    import asyncio


def setup(bot):
    bot.add_cog(Music(bot))

client.run(TOKEN)
