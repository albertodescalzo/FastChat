## FastChat in deNBI machine
**Prerequisites**: 
    Have a machine in deNBI and being able to log in through ssh. Assume the machine is called denbi_machine.

```
git clone https://github.com/albertodescalzo/FastChat.git
cd FastChat/docker
docker compose up
Ctrl + C  
```
(first time won't work because gradio-server needs to be started once worker-node is finished
---> docker-fastchat-gradio-server-1  | 2024-06-11 08:44:57 | INFO | gradio_web_server | All models: [] 
---> incorrect: you need to see the model in there, e.g. 
---> docker-fastchat-gradio-server-1  | 2024-06-11 08:50:50 | INFO | 
gradio_web_server | All models: ['vicuna-7b-v1.5'])

`docker compose up`


--> In another shell build a tunnel connection: 
`ssh -L 8000:localhost:8000 denbi_machine`

---> Open the gradio webUI in browser locally:
`http://localhost:8000`