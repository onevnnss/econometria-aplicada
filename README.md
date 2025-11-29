### Motivação

* A relação entre política monetária e atividade econômica é um dos temas centrais em macroeconomia. Embora o mecanismo de transmissão dos juros seja amplamente estudado, existe crescente evidência de que esse efeito não é uniforme ao longo do ciclo econômico. Em momentos de recessão, por exemplo, aumentos da taxa de juros tendem a produzir impactos distintos em relação a períodos de expansão, sugerindo a presença de assimetrias na resposta da atividade.

* A economia brasileira passou por três regimes bastante distintos na última década: um período pré-pandemia relativamente estável; a pandemia de COVID-19, marcada por forte quebra estrutural; e a fase pós-pandemia, caracterizada pela reacomodação da política monetária e recuperação gradual da atividade. Esses choques tornam o Brasil um laboratório ideal para investigar se o impacto da Selic varia não apenas entre períodos diferentes, mas também ao longo da distribuição da atividade econômica.

* Diante desse contexto, surge a motivação deste trabalho: examinar se o efeito da Selic sobre o nível de atividade (medido pelo IBC-Br) é assimétrico e regime-dependente. A análise tradicional via regressão linear captura apenas efeitos médios; para investigar heterogeneidade e assimetria, é necessário utilizar abordagens que considerem toda a distribuição condicional — como a regressão quantílica.

------------------------

#### Pergunta norteadora e hipóteses
> A pergunta central deste trabalho é:

“Os efeitos da taxa Selic sobre o nível de atividade econômica brasileira (IBC-Br) são assimétricos ao longo da distribuição condicional e variam entre os regimes pré-pandemia, pandemia e pós-pandemia?”

> A partir dessa pergunta, estabelecemos as seguintes hipóteses:

• H1: O impacto da Selic sobre o IBC-Br não é constante ao longo da distribuição condicional — sendo maior em quantis superiores (maior atividade) ou inferiores (baixa atividade).  
• H2: O impacto da Selic varia entre os regimes econômico-sanitários — particularmente durante a pandemia, quando choques exógenos dominam a dinâmica da atividade e enfraquecem o mecanismo tradicional de transmissão monetária.  
• H3: A OLS captura apenas o impacto médio, enquanto a regressão quantílica revelará heterogeneidade e assimetrias não observáveis pela média.

------------------------

#### Descrição de Dados
Utilizamos dados mensais do Banco Central do Brasil (BCB/SGS) no período de janeiro de 2015 a dezembro de 2024. As séries selecionadas foram:

• IBC-Br (código 24363), utilizado como proxy mensal da atividade econômica;  
• Taxa Selic (código 1178), agregada por média mensal;  
• IPCA (código 433), utilizado como controle de inflação corrente.

A escolha do IBC-Br se justifica por sua alta correlação com o PIB e sua disponibilidade mensal, permitindo maior granularidade temporal. A Selic é o principal instrumento de política monetária no Brasil, sendo a variável focal do estudo. O IPCA é incluído como variável de controle para capturar condições de preços no curto prazo.

Realizamos tratamento padronizado:  
* (i) conversão de datas;  
* (ii) transformação de valores para formato numérico;  
* (iii) alinhamento temporal das três séries por merge;  
* (iv) criação de três subconjuntos que representam os regimes: pré-pandemia (jan/2015–fev/2020), pandemia (mar/2020–dez/2021) e pós-pandemia (jan/2022–dez/2024).

------------------------

#### Modelo OLS Múltiplo

Estimamos regressões lineares múltiplas do tipo:

> IBCBr_t = β0 + β1·Selic_t + β2·IPCA_t + ε_t

para cada um dos três períodos. A OLS fornece apenas o impacto médio da Selic sobre a atividade. Os resultados mostram:

• Pré-pandemia: coeficientes pequenos e não significativos, sugerindo baixa tração monetária em um regime estável;  
• Pandemia: a Selic perde significância, enquanto o IPCA se torna dominante — resultado coerente com a quebra estrutural;  
• Pós-pandemia: surge coeficiente negativo da Selic, indicando retorno parcial da eficácia da política monetária.

Apesar de úteis, os modelos OLS apresentam baixo poder explicativo e resíduos que revelam heterogeneidade e não-linearidades, especialmente nas caudas da distribuição. Esses diagnósticos motivam o uso da regressão quantílica como ferramenta mais apropriada para capturar assimetrias.

------------------------

#### Regressão quantílica
A OLS estima apenas o efeito médio da Selic sobre o IBC-Br. Entretanto, se os efeitos forem assimétricos — maiores quando a economia está aquecida ou deprimida — então a média oculta parte importante da relação.

A regressão quantílica permite estimar o efeito da Selic em diferentes pontos da distribuição condicional do IBC-Br, como os quantis 0.10, 0.25, 0.50, 0.75 e 0.90. Dessa forma, é possível identificar se a política monetária impacta mais fortemente momentos de baixa atividade ou de expansão.

O modelo econométrico estimado é:

Qτ(IBCBrₜ | Selicₜ, IPCAₜ)
= β₀,τ
+ β₁,τ · Selicₜ
+ β₂,τ · IPCAₜ
+ εₜ,τ

O modelo é estimado separadamente para: pré-pandemia, pandemia e pós-pandemia.

Os resultados mostram clara heterogeneidade ao longo dos quantis. Durante a pandemia, o impacto da Selic é praticamente nulo em todos os quantis, enquanto o IPCA domina. No pós-pandemia, o coeficiente da Selic torna-se fortemente negativo nos quantis superiores — indicando que juros altos reduzem mais a atividade quando ela já está em níveis elevados.

Esses achados revelam um comportamento assimétrico da política monetária: em períodos de maior dinamismo, o aperto monetário é mais efetivo; em períodos deprimidos, o impacto é menor. Esse padrão não aparece nas regressões OLS.

------------------------

### Conclusão

O trabalho mostrou que o impacto da Selic sobre o nível de atividade econômica brasileira não é uniforme ao longo do tempo nem ao longo da distribuição condicional do IBC-Br. A regressão OLS indicou efeitos médios fracos ou instáveis, especialmente durante a pandemia. Os diagnósticos revelaram heterogeneidade substancial, motivando a aplicação da regressão quantílica.

A regressão quantílica confirmou efeitos assimétricos da política monetária: no pós-pandemia, o impacto negativo da Selic é mais pronunciado nos quantis superiores, sugerindo que períodos de maior atividade respondem mais ao aperto monetário. Durante a pandemia, os coeficientes foram pouco significativos, refletindo a predominância de choques exógenos sobre o mecanismo de transmissão.

Esses resultados destacam a importância de métodos que capturam heterogeneidade e assimetria em análises de política monetária. Além disso, reforçam que a interpretação média fornecida pela OLS pode ser insuficiente para compreender a complexidade da dinâmica econômica brasileira em contextos de choque e recuperação.

