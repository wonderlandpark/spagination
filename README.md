# pagination-is-noob
Pagination For Discord.js


## Example
```js
const Discord = require('discord.js')
const Pagenation = require('./index')
const Client = new Discord.Client()

Client.on('message', async (m) => {
  if (m.content === 'test') {
    const pagination = new Pagenation.Pagination({ pageText: 'Page %CURRENT% / %ALL%' })
    pagination.addEmbed(new Discord.MessageEmbed().setColor('#FFBABA').setTitle('Page 1'))
    pagination.addEmbed(new Discord.MessageEmbed().setColor('#FFBABA').setTitle('Page 2'))
    pagination.addEmbed(new Discord.MessageEmbed().setColor('#FFBABA').setTitle('Page 3'))
    pagination.addUser(m.author.id)
    await pagination.send(m.channel)
  }
})

Client.login('')
```