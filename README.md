# Custom-prefix-command
first make a file called CP.json
then go in the json file and paste in: {"CP":"*"}
after that go back to the index.js or what ever your main file is and paste

client.on('message', message =>{
    if(!message.content.startsWith(CP.CP) || message.author.bot) return;


    const args = message.content.slice(CP.CP.length).split(/ +/);
    const command = args.shift().toLowerCase();


    if(command == 'setprefix'){
        let newCP = args[0]
        CP.CP = newCP;
        message.channel.send(`The prefix has been set to:${newCP}`)

        fs.writeFile("./CP.json", JSON.stringify(CP), (err) => {
            if (err) console.log(err)
        });
    }

});

and thats
to set the prefix just do !setprefix <prefix>
  for example: !setprefix ?
