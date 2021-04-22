# Gráfico de Redes com Python e Gephi
### O documento a seguir tem como objetivo expor os passos utilizados para criação de um gráfico como o da imagem
#
![plot](/doc/img/Grafico.PNG)

#
## Tecnologias Utilizadas:

* Python
* Gephi
    * Sigma Exporter
    * Multigravity Force Atlas 2
    * Circle Pack
* Visual Studio Code

#
## Instalando as tecnologias
Para a produção do gráfico, teremos que instalar algumas ferramentas, tecnologias e bibliotecas.
* Python
    - Inicie o download do Python [clicando aqui](https://www.python.org/ftp/python/3.9.4/python-3.9.4-amd64.exe).
    - Na tela inicial do instalador deixe marcada a opção `Add Python 3.X to PATH`.
    ![Add Python 3.X to PATH](/doc/img/PythonPath.PNG)
    - Clique em `Install Now` e aguarde até o fim da instalação.
    - Para verificar se a instalação foi realizada com sucesso abra o terminal da sua máquina:
        - Windows: `Tecla Windows` + `X` e então `A`. Ou busque por "Prompt de Comando" na barra de pesquisa do menu iniciar
        - Linux: `Ctrl` + `Alt` + `T`
    - Digite `python -v`. Caso a instalação tenha sido um sucesso o resultado esperado será `Python 3.X.X (....)` ![resultadoPython](/doc/img/Terminal.PNG)

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
    
    - Pandas
        - Pandas é uma biblioteca de software criada para Python visando manipulação e análise de dados. Para saber mais sobre a biblioteca [clique aqui](https://pandas.pydata.org/).
        - Para instalação do Pandas iremos utilizar, novamento o `pip`.
        - Digite o seguinte código no seu terminal e então pressione `Enter`.
        - > `pip install pandas`

    - OpenpyXL
        - Para a leitura da planilha em excel, teremos que instalar uma dependência para tornar esta leitura possível.
        - Execute o seguinte código no seu terminal.
        - > `pip install openpyxl`

    - XLWT
        - Para a escrita de uma planilha em excel, teremos que instalar uma dependência para tornar esta escrita possível.
        - Execute o seguinte código no seu terminal.
        - > `pip install xlwt`
* Gephi
    - Para fazer o download do Gephi [clique aqui.](https://gephi.org/users/download/)
    - Como a instalação do Gephi é simplificada, seguir selecionando `Next` resultará na instalação total do aplicativo. 
    

* Sigma Exporter
    - Sigma Exporter é um plug-in para Gephi, que permite exportar os gráficos gerados para a plataforma web.
    - Para instalar o plug-in abra o Gephi e na barra de menu superior clique em `Ferramentas` e em seguida em `Plug-ins`.
    ![](/doc/img/gephiferramentas.PNG)
    - Na nova janela aberta, selecione a aba `Plug-ins Disponíveis` e pesquise por `SigmaExporter`.
    - Selecione o plug-in e então clique em `Instalar`.
    ![](/doc/img/sigmaexporter.PNG)
    - Após a instalação reinicie o software.

* ForceAtlas 2
    - Repita os mesmos passos para instalar o `Sigma Exporter`, porém, pesquisando por `ForceAtlas2`

* Circle Pack
    - Repita os mesmos passos para instalar o `Sigma Exporter`, porém, pesquisando por `CirclePack`

* Visual Studio Code
    - Para ajudar na visualização dos cadernos jupyter, utilizaremos o ambiente fornecido pelo Visual Studio Code
    - Faça o download da ferramenta [clicando aqui.](https://code.visualstudio.com/)
    - Assim como o Gephi, a instalação do Visual Studio Code também é bem simplificada, então, seguir pressionando `Next` resultará numa instalação bem sucedida.

#
## Configurações Iniciais do Visual Studio Code

Teremos que instalar algumas extensões para o Visual Studio Code, para isto, abra o seu Visual Studio Code e então clique no ícone de extensões no menu lateral esquerdo.


![extensões](/doc/img/extensoesvs.PNG)

Na nova janela busque por `Jupyter`, e então clique em `Install` no primeiro resultado.
Repita o processo, porém, desta vez pesquisando por `Python`
#
## Planilha com dados e Scripts
Para prosseguirmos com o tutorial, utilizaremos uma planilha de dados concedida pela [Embrapa](https://www.embrapa.br/) para realizar o tratamento e disposição dos dados.
Você pode fazer o download da planilha clicando [aqui.](https://github.com/oajoj/network/raw/master/doc/files/xlsx/mel.xlsx)

Clique [aqui](https://github.com/oajoj/network/raw/master/doc/files/rar/scripts.rar) e baixe a pasta compactada contendo os dois scripts que iremos utilizar para este tutorial.

Extraia a pasta compactada em uma nova pasta vazia e então abra o Visual Studio Code.

Ao abrir o Visual Studio Code clique em `File` e então em `Open Folder`

![Visual File](/doc/img/visualfile.PNG)

Navegue até a pasta que você criou e então clique em `Selecionar Pasta`.

Feito isso, você terá esses dois arquivos na aba `Explorer`.

![Arquivos](/doc/img/arquivos.PNG)

Clique no arquivo `Autores.ipynb` para que o mesmo seja aberto no Visual Studio Code. 
Ao abrir, espere seu carregamento e note a barra superior com alguns botões.
Nela, será possível iniciar o processamento do script e gerar as planilhas resultantes.
![Barra Superior](/doc/img/zoombarra.PNG)
Vamos focar nas ações que iremos utilizar:
- O primero botão (►►)irá rodar o script desde o seu início;
- O quarto botão (⭯) reinicia todas as variáveis do script;
- o quinto botão (□) interrompe o funcionamento do kernel;

## <span style="color:orange">Importante</span>
### <span style="color:orange">Antes de executar o script você deverá colocar o arquivo da planilha no mesmo diretório em que os scripts estão.</span>

Repare como o documento `Planilha_Exemplo.xlsx` está junto dos scripts, ou seja, estão na mesma pasta.

![Planilha](/doc/img/exemploplanilha.PNG)

### Abra o arquivo `autores.ipynb`, siga as instruções do script e então execute-o.
### É esperado que seja gerado uma planilha com o nome `autores.xlsx`.

### Feito isso, com o arquivo `autores.xlsx` gerado, abra o script `RelaçãoAutores.ipynb` e siga suas instruções e então execute-o.
### É esperado que seja gerado uma planilha com o nome `resultado_final.xls`


> Uma ideia para atualização deste script seria a sua unificação, visto que é necessário rodar dois arquivos diferentes para obter o resultado esperado.


#
## Utilizando o Gephi

Abra o Gephi e em sua tela de Boas Vindas cliquem em `Novo Projeto`.

No menu superior clique em `Laboratório de Dados`.

![Laboratório de Dados](/doc/img/lab.PNG)

Nesta nova janela, clique em `Importar Planilha`

![Import](/doc/img/import.PNG)

Selecione o arquivo `resultado_final.xlsx` e confirme clicando em `abrir`

Altere, no campo `Import as`, para `Edge Table`. Apenas as colunas `Source`, `Target` e `Weight` devem ser exibidas. Clique em `Próximo`

![Arestas](/doc/img/edge.PNG)

Clique em `PRÓXIMO` e então em `FINALIZAR`

Na tela final, mude o tipo de grafo para `NÃO-DIRIGIDO` e selecione a opção `APPEND TO EXISTING WORKSPACE` e pressione `OK`

![Importação](/doc/img/impor.PNG)

Agora, ainda no `Laboratório de dados`, na aba `Tabela de dados` clique em `Nós`

![Nós](/doc/img/nos.PNG)

No menu inferior, clique em `Copiar dados para outra coluna` e selecione `Id`

![Id](/doc/img/Id.PNG)

Selecione `Label` e clique em `Ok`


![Label](/doc/img/labela.PNG)

#
## Melhorando a visualização

No menu superior, clique em `Visão Geral` e então você verá o resultado das ligações dos nós que importamos anteriormente, porém é impossível entender qualquer coisa deste gráfico. Por isso, iremos melhorar sua visualização.

## Cor
No menu lateral superior esquerdo na aba `Aparência` selecione o item `Nós` e seleciona o símbolo de uma Paleta de Pintura


![Cor](/doc/img/cor.PNG)

Agora, clique e segure no quadrado cinza e escolha a cor de sua preferência e clique em `Aplicar`

## Rótulos
Para exibir os nomes dos autores, no menu superior esquerdo, na aba `Nós` clique no ícone `TT` e defina o tamanho
## Modularidade
No menu lateral dirieto na aba `Estatísticas` procure por `Modularidade` e clique em `Executar`

![Modularidade](/doc/img/mod.PNG)

Desmarque a opção `Utilizar pesos de aresta` e então clique em `ok`.

Feche a nova janela que surgiu.

## Grau ponderado médio

No menu lateral direito na aba `Estatísticas` procure por `Grau ponderado médio` e clique em `Executar`

![Grau](/doc/img/grau.PNG)

Feche a nova janela que surgiu.

## Distribuição

No menu lateral inferior direito, clique em `--Escolha uma distribuição` e selecione `Circle Pack Layout`

![Círculo](/doc/img/circle.PNG)

No menu `Hierarchy1` selecione `Modularity Class`

No menu `Hierarchy2` selecione `Grau Ponderado`

![Atributos](/doc/img/att.PNG)

Clique em `executar`

## Distribuição de Rótulos
No menu lateral inferior direito, clique em `--Escolha uma distribuição` e selecione `Ajustar rótulos`


Desta forma já teremos uma visualização bem melhor.

Salve o seu projeto e então, no menu superior, clique em `Visualização` e logo clique em `Atualizar`

![Atualizar](/doc/img/atualizar.PNG)


#
## Rótulos e Arestas

Para exibir os rótulos, no menu lateral esquerdo selecione `Mostrar Rótulos` e altere o tamanho para o de sua preferência.
Limite o tamanho de caracteres selecionando `Limitar rótulos` e inserindo o valor máximo de caracteres no item abaixo `Número máximo de caracteres`

Atualize para verificar as alterações


Ainda no menu lateral esquerdo, no menu de Arestas, seleciona `Reescalonar Peso` e mude os valores de acordo com sua preferência.

Feito isso é hora de gerar o gráfico para a web.

#
## Exportando o Gráfico

Clique em `Arquivo` e `Exportar` e seleciona `Sigma.js Template`

A seguinte janela abrirá

![Exportar](/doc/img/exporter.PNG)

Explicação dos campos:
- O primeiro campo, que possui o botão `Browser`, identifica onde você quer salvar o gráfico (lembre-se de criar uma pasta vazia para salvar)

- Legend
    - Node: Descrição do que os nós no gráfico representa (Ex.: Pessoas)
    - Edge: Descrição do que as ligações entre nós representam (Ex.: Relação de parentesco)
    - Color: Descrição do que as cores representam no gráfico (Ex.: Pessoas)

- Branding
    - Logo(url): Endereço do arquivo que representa seu logotipo (Ex.: C:\Users\usuario\fotos\logotipo.PNG)
    - Link: Link para sua instituição (Ex.: www.instituicao.com.br)
    - Author: Nome do autor que gerou o gráfico (Ex.: Fulano de tal)
    - Title: Título do gráfico (Ex.: Relação de Parentesco)

- Features
    - [ ] Include search?: Você deseja habilitar a função de pesquisa dentro do gráfico?
    - O restante pode ficar do jeito que está...

- Short Description: Pequena descrição do projeto
- Long Description: Longa descrição do projeto

Ao final, clique em `Ok`

#
## Exibição no navegador

Navegue até a pasta onde você escolheu salvar o gráfico. Você encontrará uma pasta chamada `network`

![Rede](/doc/img/network.PNG)

Abra a pasta e todo o conteúdo do gráfico estará lá.

Clique na barra de pesquisa superior e copie o caminho dos arquivos

![Path](/doc/img/caminho.PNG)

Abra o terminal do seu computador e insira `cd` e em seguida cole o caminho do seus arquivos

```
 cd C:\Users\joao-\Desktop\Network\teste\network
```

![CMD](/doc/img/cmd.PNG)

Feito isso copie e cole o seguinte código

```
python -m http.server
```

![Python](/doc/img/py.PNG)

Agora no seu navegador acesse http://localhost:8000/

Pronto, agora você já pode interagir com seu gráfico.

Caso você deseje alterar algum detalhe do gráfico, tal como, cor, tamanho das arestas, tamanho dos nós, faça essas alterações no Gephi e então faça uma nova exportação.

#



