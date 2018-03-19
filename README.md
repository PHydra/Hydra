Change Log
==========
## 0.2.5 - (2018.03.14)
### Corrigido
- erro ao clicar na tabela geopressões
- Atualização da função poros_pressure_correction na classe HyTables_Geopressures
- Generelização da função update_graph na classe HyTable_PlotData

## 0.2.4 - (2018.03.02)
  - Salvar e carregar arquivos .cae com as informações do poço para a interface
  - Nova equação para a degradação termica caso o tubo não esteja no cardapio de tubos
  - A duração da troca de fluido e repasse na tabela eventos ficam ocultas (setando com '-')
  - O peso de lama do repasse foi alterado para '-'
  - Repasse considera o ultimo peso de lama anterior

### Corrigido
  - Correção da poropressão: Ao criar um ponto imediatamente acima da camada de sal, a interface deve criá-lo para evitar interpolação errada da pressão de poros
  - Bug: atualização da duração na tabela eventos
  - Bug: erro do windows ao fechar o plugin

## 0.2.3 - (2018.02.02)
  - Resumo das análises. Dados de geometria, geologia, tubos e eventos
  - Degradação térmica é buscada no Kernel e corrigida com a temperatura geotérmica da rocha.
  - Plugin funcionando no Abaqus 6.14

### Corrigido
  - Repasse: Kernel define como step instantâneo. as edições do inp no CAE são feitas no mesmo módulo, evitando a ocorrencia de conflitos nos sieBlocks
  - Definição dos eventos por duração
  - Lista automática que atualiza a duração dos eventos específicos, bem como a duração total de perfuração e do revestimento
  - Vida útil do último revestimento sempre igual a vida produtiva menos os eventos anteriores


## 0.2.2 - (2018.01.23)
### Nota
  - A versão 0.2.2 já foi gerada, porém um problema no servidor seguido da falha do HD na máquina gerada (Daniel) gerou a perda do change log.

## 0.2.1 - (2018.01.18)
### Corrigido
  - Carregamento sumindo após a criação do evento na hora de salvar o dado.

## 0.2.1a - (2018.01.17)
### Corrigido
  - OD do Repasse era convertido de pol. para metro duas vezes.
  -

## 0.2.0 - (2018.01.16)
### Adicionado
  - Repasse, Perda de circulação
  - corrigido leitura do OD repasse em polegadas

## 0.1.16 - (2018.01.16)
### Corrigido
  - Adicionado o import session em kernel readResults module
  - OD repasse trocado para polegadas

## 0.1.15 - (2018.01.15)
### Corrigido
  - Adicionado os eventos de Mud drop e de Repasse (kernel e GUI)
  - Corrigido o "focus" das tabelas

## 0.1.14 - (2018.01.05)
### Corrigido
  - Etapas e Eventos:
    - Carregamento sumindo após criação da análise.
    - HyTables de todos os itens - criação de novas funções, update_row, update_col e update_cell

## 0.1.13 - (2017.12.14)
### Corrigido
  - Análise:
    - Correção da correção do contato. Segundo o Kernel: leitura da face errada da superficie

## 0.1.12 - (2017.12.14)
### Corrigido
  - Análise:
    - Configuração (default) tela de análise - Avançado.
    - Histórico de pressão interna e temperatura durante a simulação
    - Alteração a superfície do INTERACTION para o *self contact

## 0.1.11 - (2017.11.21)
### Corrigido
  - No Item Análise foi modificado como valores defaut os seguintes itens:
    - Revestimento - Conforme definido.
    - Cimento - Elástico
    - Rocha - Conforme definido
    - Térmico - Constante
    - Avançado - Contato sal/revestimento

## 0.1.10 - (2017.11.17)
### Corrigido
  - Foram encontrados e solucionados problemas tanto na interface como no kernel. O problema na interface foi no item step e eventos no momento de pegar os dados do poço revestido da interface para enviar para o kernel.

    O problema do Kernel foram:

    Ao capturar os dados de temperatura da rocha, a temperatura do topo não era atualizada. Quando as camadas de rocha eram divididas no Kernel (em profs. de TOC, Sapata, e etc.) esses valores eram extrapolados erradamente.
    Fases que apresentavam varias seções de tubos diferentes eram tratadas como anulares diferentes. Assim, os eventos daquela fase eras selecionados erradamente. Corrigido através do link entre os revestimentos e a fase nos quais eles se encontravam.

## 0.1.9 - (2017.10.19)
### Corrigido
  - Correção da função geopressures_property no cálculo da tensão na rocha quando a sua base é igual a um dado de profundidade de geopressões.

## 0.1.8 - (2017.10.18)
### Corrigido
  - Correção da função abqSimulation, criação de uma margem de erro na fronteira de +- 0.0001.

## 0.1.7 - (2017.10.17)
### Corrigido
  - Salvar dados ao criar e submeter a análise
  - Correção da função import_data

## 0.1.6 - (2017.10.16)
### Corrigido
  - Salvar dados ao criar e submeter a análise


## 0.1.5 - (2017.10.02)
### Corrigido
  - Salvar e carregar novas linhas nas tabelas do item [**Dados Materiais**]
  - Importando corretamente os dados do arquivo StandartProperties
  - Removendo a extensão do arquivo StandartProperties.txt

## 0.1.4 - (2017.09.20)
### Adicionado
  - Caso a profundidade selecionada esteja em uma interface (TOC, Sapata ou interface de camada), é adicionado 1e-5 na profundidade para seleção sempre da geometria mais profunda
  - Caso a rocha seja um Sal, o GUI modifica a pressão de poros para zero.
### Modificado
  - rathole alterado para zero, pois não afeta o estado plano.
### Corrigido
  - corrigido o bloqueio da tabela específica de tubos
  - Na amplitude em eventos de mudança de lama/temperatura, adicionado uma linha para manter o valor constante até o final do step (havia erro de extrapolação)

## 0.1.3 - (2017.09.13)
### Adicionado
  - Preenchimento automático da tabela *Operações*  na hora de submenter o modelo [**Análises**]
  - Adicionado a opção default do cimento na tabela *Propriedades comuns dos cimentos* [**Cimentos**]
  - Bloqueada a coluna ov(%) e trocada a fração para porcentagem das colunas DeltaMax_OD/OD e DeltaMin_OD/OD na tabela *Propriedades da seção Transversal* [**Seção Transversal**]
  - Atualizado a criação dos modelos temporários utilizando o nome Model-1 padrão do ABAQUS [**Kernel**]
  - Adicionada a camada de estratos quando o topo da primeira camada é diferente da lâmina da água definida [**Kernel**]
  - Atualizado o carregamento inicial da geometria temporária [**Kernel**]
### Corrigido
  - Vizualização correta do gráfico *Vizualização Grafica* [**Perfil Térmico**]
  - Leitura correta do perfil térmico para o kernel [**Perfil Térmico**]
  - Correção dos valores do escoamento dos tubos na tabela **Propriedades dos graus** [**Tubos e Sapatas**]
  - Geração do modelo do ABAQUS somente ao clicar no botão OK no *Gerenciador de Análises* [**Análises**]
  - Correção da leitura das tensões do GUI para o kernel da tabela *Geopressões* [**Geopressões**]
  - Correção do problema da comunicação GUI-Kernel para o creep do material [**Análises**]

## 0.1.2 - (2017.08.09)
### Corrigido
  - Atualização do peso de lama na tabela *Eventos* [**Etapas e Eventos**]
  - Ordem de preenchimento da tabela *Dados Gerais* irrelevante [**Tubos e Sapatas**]
  - Carregamento da tabela cimentos (faltando checkbox) [**Cimentos**]
  - Carregar tabela *Dados Específicos* com mais de duas linhas [**Tubos e Sapatas**]

## 0.1.1 - (2017.08.01)
### Corrigido
  - Correção da atualização do peso de lama na tabela Eventos
  - Correção da vizualização do módulo Hydra Plug-in somente com
    as abas 'Model' e 'Results'


## 0.1.0 - (2017.07.21)
### Adicionado
  - Mensagem de erro ao criar uma operação sem escolher uma fase
  - Gerenciador de análise criado
  - Análise Plano-Deformação
  - Visualização gráfica do esquema de poço e coluna litológica
  - Gráficos de temperatura e geopressões
  - Operações disponíveis: Troca de fluido
  - Opção de salvar e carregar um projeto
  - Cria, submete, edita, copia e deleta a análise

## 0.1.0a - (2017-02-22)
### Modificado
  - Novo layout (ícones, botões, visualização, gráficos e disposição)
  - Novo gerenciamento do perfil térmico
  - Aperfeiçoamento da comunicação entre as tabelas
  - Finalizada a seção **Etapas e Eventos**
  - Seção **Análise** e comunicação com o kernel pendentes

### Adicionado
  - Escolha do cimento na seção **Dados Materiais > Cimentos**

