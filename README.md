# Thermal Solar Plant Dataset

Realtime thermal solar plant dataset for machine learning.

I would like to provide reale time dataset of a thermal solar plant logged in 
the time of 2016-12-28 till 2018-10-10.

> Feel free to use data for research and development and let me know what you have learned and developed.



## Data Structure

Data is logged every minute but has some corrupted elements and data gaps.

The data is stored in individual CSV files. There is one log file per day. 
The log files are grouped in monthly folders.

The headers of the CSV files are in German and will be translated into 
English in the following. The temperature values are stored in Celcius.
Please consider that not all values are really provided with measured data.

### Dataset Header

Content of CSV files is structured in following columns:

| Column                         | Description                      |
|--------------------------------|----------------------------------|
| Datum & Uhrzeit                | date & time                      |
| Temperatur Sensor 1 [ °C]      | temperature of sensor 1 in °C    |
| Temperatur Sensor 2 [ °C]      | temperature of sensor 2 in °C    |
| Temperatur Sensor 3 [ °C]      | temperature of sensor 3 in °C    |
| Temperatur Sensor 4 [ °C]      | temperature of sensor 4 in °C    |
| Temperatur Sensor 5 [ °C]      | temperature of sensor 5 in °C    |
| Temperatur Sensor 6 [ °C]      | temperature of sensor 6 in °C    |
| Druck Sensor 7 [ Bar]          | pressure of sensor 7 [Bar]       |
| Temperatur Sensor 8 [ °C]      | temperature of sensor 8 in °C    |
| Durchfluss Sensor 9 [ l/h]     | Flow rate sensor 9 [ l/h]        |
| Durchfluss V40 [ l/h]          | Flow rate V40 [ l/h]             |
| Einheit                        | Unit                             |
| PWM 1 [ %]                     | ?                                |
| PWM 2 [ %]                     | ?                                |
| Drehzahl Relais 1 [ %]         | rotational speed relais 1 in %   |
| Drehzahl Relais 2 [ %]         | rotational speed relais 2 in %   |
| Drehzahl Relais 3 [ %]         | rotational speed relais 3 in %   |
| Drehzahl Relais 4 [ %]         | rotational speed relais 4 in %   |
| Betriebssekunden Relais 1 [ s] | operating seconds relais 1 [ s]  |
| Betriebssekunden Relais 2 [ s] | operating seconds relais 2 [ s]  |
| Betriebssekunden Relais 3 [ s] | operating seconds relais 3 [ s]  |
| Betriebssekunden Relais 4 [ s] | operating seconds relais 4 [ s]  |
| Fehlermaske                    | error mask                       |
| Statusmaske                    | status mask                      |
| Wärme [ Wh]                    | heat energy                      |
| Version                        | version                          |
| Systemzeit                     | system time                      |
| Systemdatum                    | system date                      |

# License

[LICENSE](LICENSE)

---

# Further Datasets

* Awesome Public Datasets: [https://github.com/awesomedata/apd-core], [https://github.com/awesomedata/awesome-public-datasets] 
* 25 Datasets for Deep Learning in IoT: [https://hub.packtpub.com/25-datasets-deep-learning-iot]
* MACHINE LEARNING DATASETS: [https://www.kaggle.com/pitasr/datasets]
* Great IoT, Sensor and other Data Sets Repositories: [https://www.datasciencecentral.com/profiles/blogs/great-sensor-datasets-to-prepare-your-next-career-move-in-iot-int]





# Modelo CRISP-DM

Este repositório contém um repositório Python-cutter para uso com o fluxo de trabalho CRISP-DM.
CRISP-DM é um fluxo de trabalho de ciência de dados, o que significa que descreve um processo específico para
execução de projetos de ciência de dados. Tais processos estão se tornando mais necessários quanto mais
experimentos de ciência de dados que você executa, pois são confusos e altamente iterativos por natureza, e
os fluxos de trabalho tradicionais de engenharia de software nem sempre são muito práticos de aplicar.

Enquanto [a teoria do fluxo de trabalho](https://www.the-modeling-agency.com/crisp-dm.pdf)
é descrito em detalhes maravilhosos, fiquei frustrado com a falta de exemplos práticos
conectados. O melhor que encontrei foi de um projeto de
[RyusukeKimura](https://github.com/RyusukeKimura/crisp-dm), mas isso está em japonês, então
muito difícil de seguir (linguagem técnica) para falantes não nativos. Devido a este raciocínio resolvi
configurar um projeto modelo que qualquer pessoa possa seguir, inspirado no layout do código proposto em
[este artigo](https://neptune.ai/blog/best-practices-for-data-science-project-workflows-and-file-organizations)
de netuno.ai.

## Este repositório

Este repositório contém as seguintes pastas para você usar.

```texto
crisp-dm-template
---dados | conjuntos de dados para seu experimento
    ---cru | conjuntos de dados como você os recebeu originalmente
    ---processado | conjuntos de dados no final do estágio de preparação de dados
---docs | notebooks em fases para escrever seu relatório CRISP-DM em
---fonte | contém funções Python que são usadas para produzir seu relatório
```

Usar o modelo é simples.

1. Fork ou clone o repositório para criar um novo experimento
2. Configure um novo ambiente virtual e instale os pacotes com `poetry install`, cortesia de
o gerenciador de pacotes [poetry](https://python-poetry.org/).
3. Siga os passos em `docs`, com auxílio do material fonte do CRISP-DM, opcionalmente
escrevendo código em `source` para ajudar a escrever seu relatório.

## Notas

### Que tipo de funções deve conter `source`?

É melhor deixar isso para interpretação pessoal, mas uma boa regra genérica é mover o código para um novo
função em `source` se:
- Você reutiliza um pedaço de código mais de uma vez
- Um pedaço de código é consideravelmente longo e prejudica a experiência de leitura em documentos
- Um pedaço de código requer documentação/contexto extra para ser entendido corretamente

### E se eu precisar de um arquivo/pasta extra?

Uma consideração importante para este repositório é que ele deve ser flexível, é um
modelo no final. Como tal, se seu experimento específico exigir, digamos, um arquivo extra em `source`
para se manter organizado, então não tenha medo de fazê-lo.

**No entanto**, é importante que essas alterações sejam feitas com consideração, para
consistência. Ninguém quer que seus experimentos tenham uma estrutura diferente para cada
experimento, pois isso torna substancialmente mais difícil encontrar as informações corretas.

### Por que específico do Python?

Python é de longe a linguagem mais popular para fins de ciência de dados, o que inúmeras fontes online podem confirmar. Devido à popularidade e preferências pessoais, foi tomada a decisão de adaptar esse modelo principalmente ao Python, no entanto, só porque esse é o foco, isso não significa que você não possa usar o modelo em outro idioma. Caso você queira mudar as linguagens de programação, siga estas etapas:

1. Remova os arquivos relacionados à poesia (poetry.lock e pyproject.toml).
2. Remova os arquivos python em `source`, e mude o tipo de arquivo para a escolha de idioma desejada.
3. Adicione as etapas necessárias para reproduzir o ambiente do projeto no idioma de sua escolha.
4. Certifique-se de incluir todos os pacotes necessários para executar os Jupyter Notebooks.

Caso seu idioma de alguma forma não suporte Jupyter Notebooks ([o que é muito difícil)](https://github.com/jupyter/jupyter/wiki/Jupyter-kernels), então você terá que fazer mais trabalho manual. Os cadernos são preenchidos com texto de remarcação, que você terá que extrair das células dos cadernos (texto dentro dos blocos `#%% md`) para outro formato de arquivo adequado.