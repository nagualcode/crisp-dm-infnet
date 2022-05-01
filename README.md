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