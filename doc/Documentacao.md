# Gráfico de Redes com Python e Gephi
### O documento a seguir tem como objetivo expor os passos utilizados para criação de um gráfico como o da imagem
#
![plot](Grafico.png)

#
## Tecnologias Utilizadas:

* [Python](https://www.python.org/ftp/python/3.9.4/python-3.9.4-amd64.exe)
* [Gephi](https://github.com/gephi/gephi/releases/download/v0.9.2/gephi-0.9.2-windows.exe)
* [Sigma Exporter](https://github.com/oxfordinternetinstitute/gephi-plugins/tree/sigmaexporter-plugin/modules/sigmaExporter)
* >Sigma Exporter é um Plug-In para a ferramente Gephi, sua instalação será explicada posteriormente
* [Visual Studio Code](https://code.visualstudio.com/)

#
## Instalando as tecnologias
Para a produção do gráfico, teremos que instalar algumas ferramentas, tecnologias e bibliotecas.
* Python
    - Inicie o download do Python [clicando aqui](https://www.python.org/ftp/python/3.9.4/python-3.9.4-amd64.exe).
    - Na tela inicial do instalador deixe marcada a opção `Add Python 3.X to PATH`.
    ![Add Python 3.X to PATH](PythonPath.png)
    - Clique em `Install Now` e aguarde até o fim da instalação.
    - Para verificar se a instalação foi realizada com sucesso abra o terminal da sua máquina:
        - Windows: `Tecla Windows` + `X` e então `A`. Ou busque por "Prompt de Comando" na barra de pesquisa do menu iniciar
        - Linux: `Ctrl` + `Alt` + `T`
    - Digite `python -v`. Caso a instalação tenha sido um sucesso o resultado esperado será `Python 3.X.X (....)` ![resultadoPython](Terminal.png)

* Bibliotecas Python

    Com o Python instalado, agora iremos instalar as bibliotecas para facilitar o tratamento dos dados da planilha. Para instalação das bibliotecas utilizaremos o `pip`. Para nossa felicidade, o gerenciador de pacotes já está instalado, uma vez que a instalação do Python tenha sido um sucesso.

    - Jupyter Notebook
        - O Jupyter Notebook é uma aplicação de código aberto que possibilita a criação de documentos com códigos, equações, visualizações e textos. Isto torna o processo de tratamento de dados mais simplificado e intuitivo. Para saber mais sobre o Projeto Jupyter [clique aqui](https://jupyter.org/).
        - Para instalação do Jupyter Notebook retorne ao terminal da sua máquina e, então, utilizaremos o gerenciador de pacotes `pip`. 
        - Insira o seguinte código no seu terminal e então pressione `Enter`.
        - > `pip install notebook`
        - Aguarde até que o processo de download e instalação seja finalizado.
        - Utilizaremos o Jupyter com o Visual Studio Code, porém é possível utilizá-lo via Web. Para isto, basta inserir no terminal:
        - > `jupyter notebook`
    


#
## Planilha com dados
Para prosseguirmos com o tutorial, utilizaremos uma planilha de dados concedida pela [Embrapa](https://www.embrapa.br/) para realizar o tratamento e disposição dos dados.
Você pode fazer o download da planilha clicando [aqui.](link)
