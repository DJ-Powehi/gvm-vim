# Nova Rede Golem - Light Bounty #1
## Compile VIM On Single Golem Node
*Sua missão é construir um VIM binário dentro de uma imagem rodando no topo da Rede Golem e depois rodar na sua máquina nativa.*

## É necessário:
- Python3 + Pip
- Docker + Compose + Machine + Virtualbox (no caso do MacOS)
- yagna - requestor
- gvmkit-build
- yapapi

## Passos Obrigatórios
- você precisa construir uma imagem docker que seja convertido com o VIM.
- você precisa converter essa imagem em uma Golem VM imagem.
- você precisa rodar a imagem na rede devnet-alpha.2 usando alto nível de Python API.
- você conseguiu rodar completamente o código binário na sua máquina nativa.

## Instruções
- instale o que é preciso
- crie um virtualenv
- ative o virtualenv
- instale gvmkit-build e yapapi via pip
- construa e marque a página do Docker.  build and tag the Dockerfile
- construa e puche a imagem marcada gvmkit-build. usando and push the tagged image using gvmkit-build
- copie e genre copy the generated hash link and paste it into IMAGE_HASH inside vim-gvm.py
- executar o serviço yagna em um terminal independente
- em outro terminal, inicialize o pagamento yagna e aguarde faucet e tx
- uma vez que a conta é registrada, crie um solicitante
- observe a chave de saída e exporte-a como a variável de ambiente YAGNA_APPKEY
- execute vim-gvm.py
- aguarde alguns minutos para o VIM compilar em sua máquina
- transforma o arquivo baixado em um executável via chmod
- abra o VIM :)

## Comandos Usados
- pip install -U gvmkit-build yapapi
- docker build -t vim:v1 .
- gvmkit-build vim:v1
- gvmkit-build vim:v1 --push
- yagna service run
- yagna payment init -r
- yagna app-key create requestor
- export YAGNA_APPKEY={requestor_output}
- python3 vim-gvm.py
- chmod +x vim
- open vim || ./vim

## Agradecimentos
- @canokaue pela ajuda