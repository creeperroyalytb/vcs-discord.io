# vcs-discord.io
Voici comment faire un vcs en discord.io pour votre bot

function virtualBroadcast(serverID, userID, message) {

	if (vcsoutof < virtualChannels.length) {

		bot.sendMessage({

			to: virtualChannels[vcsoutof],

			embed: {

				"color": 1,

				"footer": {

					"icon_url": "https://cdn.discordapp.com/avatars/" + bot.id + "/" + bot.users[bot.id].avatar + ".png?size=4096",

					"text": "VCS " + bot.users[bot.id].username + " - " + bot.servers[serverID].name + " (" + serverID + ")"

				},

				"thumbnail": {

					"url": "https://cdn.discordapp.com/avatars/" + userID + "/" + bot.users[userID].avatar + ".png?size=4096"

				},

				"author": {

					"name": bot.users[userID].username + "#" + bot.users[userID].discriminator + " - " + userID

				},

				"fields": [

					{

						"name": "Message : ",

						"value": message

					}

				]

			}

		});

		vcsoutof = vcsoutof + 1;

	} else if (vcsoutof == virtualChannels.length) {

		bot.sendMessage({

			to: virtualChannels[vcsoutof],

			embed: {

				"color": 1,

				"footer": {

					"icon_url": "https://cdn.discordapp.com/avatars/" + bot.id + "/" + bot.users[bot.id].avatar + ".png?size=4096",

					"text": "VCS " + bot.users[bot.id].username + " - " + bot.servers[serverID].name + " (" + serverID + ")"

				},

				"thumbnail": {

					"url": "https://cdn.discordapp.com/avatars/" + userID + "/" + bot.users[userID].avatar + ".png?size=4096"

				},

				"author": {

					"name": bot.users[userID].username + "#" + bot.users[userID].discriminator + " - " + userID

				},

				"fields": [

					{

						"name": "",

						"value": message

					}

				]

			}

		});

		vcsoutof = vcsoutof + 1;

	} else {

		clearInterval(vcsSend);

		vcsoutof = 0;

	}

}

