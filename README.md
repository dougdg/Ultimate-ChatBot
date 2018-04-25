# Exemplo de Chatbot com Watson Conversation em Node.js

Este aplicação é um demo de cliente de Chatbot em Node.js que utiliza Watson Assistant. Basta criar um Watson Assistant, colocar as credenciais neste app e fazer o deploy no Bluemix. (Exemplo de criação de Watson Conversation no arquivo: https://github.com/sergiogama/Ultimate-ChatBot/blob/master/TUTORIAL%20ChatBot.pdf).

[![Deploy to Bluemix](https://bluemix.net/deploy/button.png)](https://bluemix.net/deploy?repository=https://github.com/sergiogama/Ultimate-ChatBot)

É possível utilizar Node-red como orquestrador ou qualquer outra plataforma como um orquestrador. Para usar o Node-red é necessário expor uma API tipo POST e retornar o JSON do Watson diretamente. 
Obs:. Este aplicação permite e mostra trabalhar com mais de um retorno do Watson Assistant.
Abaixo esta exexmplo de flow do Node-red:

[{"id":"f00c4075.ce4e4","type":"http in","z":"8ac0be49.7b6a3","name":"","url":"/api/conversation","method":"post","upload":false,"swaggerDoc":"","x":116,"y":71,"wires":[["d5767344.1b9f8"]]},{"id":"3636b79a.cd5878","type":"http response","z":"8ac0be49.7b6a3","name":"","statusCode":"","headers":{},"x":665.2801513671875,"y":70.77455139160156,"wires":[]},{"id":"ce77e800.614a48","type":"watson-conversation-v1","z":"8ac0be49.7b6a3","name":"","workspaceid":"1ce9bef8-2d1e-4209-94ca-54d55e6330b0","multiuser":false,"context":true,"empty-payload":false,"default-endpoint":true,"service-endpoint":"https://gateway.watsonplatform.net/conversation/api","timeout":"","optout-learning":false,"x":509.5,"y":71,"wires":[["3636b79a.cd5878"]]},{"id":"d5767344.1b9f8","type":"change","z":"8ac0be49.7b6a3","name":"","rules":[{"t":"set","p":"payload","pt":"msg","to":"payload.params.input.text","tot":"msg"}],"action":"","property":"","from":"","to":"","reg":false,"x":324.5,"y":71,"wires":[["ce77e800.614a48"]]}]

![alt text](https://raw.github.com/sergiogama/Ultimate-ChatBot/blob/master/Screen%20Shot%202018-04-25%20at%2016.50.50.png)

(https://github.com/sergiogama/Ultimate-ChatBot/blob/master/Screen%20Shot%202018-04-25%20at%2016.50.50.png)

OU

## Para executar o app localmente

1. [Instalar Node.js][]
+ cd no diret'roio raiz do projeto
+ Execute `npm install` para instalar as dependências do app
+ Altere o aquivo vcap-local.json e coloque as credenciais e workspace_id do assistant.
+ Execute `npm start` para o iniciar o app
+ Acesse a aplicação no browser no link <http://localhost:6001>

[Instale Node.js]: https://nodejs.org/en/download/
"# Conversation-demo" 
