# descobertaRemedios
 Projeto desenvolvido a partir da Imersão de Dados 3 da Alura.

### Problema:
Pensar em técnicas de Aprendizagem de máquina que podem ajudar na descoberta de novas drogas farmacêuticas baseado no desafio do [Laboratory innovation science at Havard](https://lish.harvard.edu/) disponibilizado no [kaggle](https://www.kaggle.com/c/lish-moa).  a descoberta de novas drogas. 

### **Dados**:

No caso dos dois conjuntos de dados que estamos trabalhando, cada linha representa uma cultura celular. Mas o que é cultura celular? Basicamente, é um grupo de células armazenadas em algum recipiente/ambiente em laboratório para que sejam feitos experimentos. Assim, nós temos dois grande grupos:

1) Aqueles que de fato receberam alguma substância quimíca e

2) grupo de controle, isto é, grupos que não receberam nenhum substância para que se tenha uma comparação do comportamento natural dos genes e da morte celular desse grupo com o primeiro.

Foram retirados das células valores de expressões genéticas, morte de celulas (por tipo, tais como saudável, cancerígenas etc) e mecanismos de ativação ativados ou não. Mecanismo de ativação nos indicam duas coisas:

a) o efeito do composto (bloqueia, inibe, ativa etc);

b) proteína em que o efeito se dá.

Essas medidas foram tiradas com dois tipos de doses diferentes do composto (D1 e D2) em três períodos diferentes após a aplicação do composto ou armazenamento do grupo de células de controle: 24, 48 e 72 horas. Assim, temos informações do efeito do composto por quantidade da dose e tempo após a sua aplicação.

## Arquivos de Dados

_dados_experimentos.zip_:

    Variáveis:
    
    1) Id -> identificador de cada grupo de célula utilizado nos experimentos
    
    2) Tratamento -> Com droga ou com controle. 
      Esta coluna nos diz se a cultura celular havia sido submetida à alguma droga ou estava somente em um ambiente de controle no momento em que foram tiradas as medidas de algumas de suas características. 
      *Ambiente de controle: 
          no contexto científico, diz respeito a isolar os indivíduos nos quais se está realizando um experimento, mas simulando seu ambiente natural de vida, para que haja confiança de que os efeitos observados sejam causados pela droga aplicada e não de outro fator externo.
      
    3) Tempo -> Se tratamento com controle, tempo em que o grupo de células fora isolado no laboratório; se tratamento com droga, tempo desde que a droga foi aplicada até a "anotação" das atuais características das células.
      
    4) Dose -> D1 ou D2. Provavelmente diz respeito à quantidade da droga aplicada.
      
    5) Droga-> Nome da droga ou composto químico aplicada(o). A maioria são compostos, porém pode haver drogas que estão sendo submetidas a testes novamente. Os nomes foram anonimizados para evitar o viés da análise dos cientistas a partir do conhecimento prévio da substância.
      
    6) G's -> trechos do DNA. Nos traz a informação da reação do gene ao comparar suas medidas com controle e com droga. 
      Neste caso, como existe um processo de proteína gerada por esse elementos, estaríamos interessados em drogas que aumente ou diminui tais medidas do Gene dependendo do problema ao qual o remédio visa resolver.
      
    7) C's -> Tipo celular. Exemplos: células de câncer, células saudáveis etc. Aplicar a substância em vários tipos de célula tem o objetivo de observar os efeitos dos compostos em células com vários tipos de características e garantir que os efeitos se dão pelo composto e não pelo tipo da célula (seres humanos com algum tipo de doença ou não, por exemplo). Os seus valores são o que é chamado de viabilidade celular, isto é, a contagem das células. Neste caso utilizamos pra comparar a quantidade de células sem composto e com aplicação de composto (quantas sobreviveram ou não) dada as características de tempo e dose recebida.
    
_dados_resultados.csv_:

    Variáveis:
        
        1) Id -> identificador de cada grupo de células utilizado nos experimentos
        
        2) Seguido por 210 colunas indicando um mecanismo de ativação e a(o) proteína ou patógeno que esse mecanismo fora ativado. Essas colunas possuem valores de 1 pra indicar se aquele mecanismo de ativação fora ativado ou 0 do contrário no grupo de células indicado pela coluna id. 

[Notebook Análise Exploratória Inicial](https://github.com/Fabiano23/descobertaRemedios/blob/main/Notebooks/AnaliseExploratoria.ipynb)

[Notebook Análise de Modelo e Próximos passos](https://github.com/Fabiano23/descobertaRemedios/blob/main/Notebooks/AnaliseModelo.ipynb)
