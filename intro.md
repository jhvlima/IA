# Inteligência Artificial

## IA Simbólica

A IA Simbólica baseia-se na premissa de que a inteligência pode ser replicada através da manipulação de **símbolos e regras lógicas**. É uma abordagem "top-down" (de cima para baixo), onde o conhecimento é explicitamente programado por humanos.

* **Como funciona:** Utiliza estruturas como "se-então" (if-then) para formar sistemas especialistas.
* **Pontos fortes:** Alta interpretabilidade (é fácil entender por que uma decisão foi tomada) e excelente para tarefas de raciocínio lógico estruturado.
* **Limitações:** Dificuldade em escalar, não aprende sozinha

## IA Conexionista

Inspirada na biologia, especificamente no funcionamento do cérebro humano, esta abordagem foca em **redes neurais artificiais**. Ao contrário da simbólica, ela é "bottom-up": o sistema aprende padrões a partir de grandes volumes de dados.

* **Como funciona:** Pesos entre conexões (neurônios) são ajustados durante o treinamento para minimizar erros. É a base do **Deep Learning**.
* **Pontos fortes:** Excelente para reconhecimento de padrões, e tem alta performace com muitos dados.
* **Limitações:** Frequentemente descrita como uma "caixa-preta", pois é difícil explicar exatamente como a rede chegou a um resultado específico, e precisa de muitos dados para treinamento eficaz.

## IA Evolutiva

Esta vertente utiliza algoritmos inspirados na **teoria da evolução de Charles Darwin** (seleção natural) para resolver problemas de otimização e busca.

* **Como funciona:** Gera-se uma "população" de soluções candidatas que passam por processos de mutação, cruzamento (crossover) e seleção. As "mais aptas" sobrevivem e geram a próxima geração.
* **Pontos fortes:** Muito eficaz para encontrar soluções em espaços de busca vastos e complexos onde não se conhece a solução ideal.
* **Limitações:** Pode ser computacionalmente cara e lenta, pois exige muitas gerações para convergir para uma solução.

## IA Baseada em Probabilidade

Foca na gestão da **incerteza e do risco**. Em vez de respostas binárias (sim/não), esta abordagem calcula a probabilidade de diferentes resultados com base em evidências estatísticas.

* **Como funciona:** Utiliza modelos como Redes Bayesianas e Processos de Decisão de Markov para inferir estados ocultos e prever eventos futuros.
* **Pontos fortes:** Essencial para sistemas de recomendação, diagnósticos médicos e robótica, onde o ambiente é imprevisível.
* **Limitações:** Requer uma base estatística sólida e pode se tornar complexa demais para problemas com variáveis excessivas.

## IA Híbrida (Neuro-Simbólica)

Busca o "melhor dos dois mundos", combinando a capacidade de aprendizado das **Redes Neurais** com o raciocínio lógico da **IA Simbólica**.

* **Objetivo:** Criar sistemas que possam aprender com a experiência (conexionismo), mas que também consigam explicar suas decisões e seguir regras abstratas (simbolismo).
* **Aplicação:** É vista como o caminho para a Inteligência Artificial Geral (AGI), permitindo que máquinas entendam conceitos e não apenas memorizem padrões estatísticos.

## Agentes Inteligentes

Um agente inteligente é uma entidade autônoma que **percebe seu ambiente através de sensores e age sobre ele através de atuadores** para atingir objetivos específicos.

* **Características:** Autonomia, reatividade (responde a mudanças), proatividade (toma a iniciativa) e sociabilidade (interage com outros agentes ou humanos).
* **Exemplos:** Desde um simples termostato (agente reativo simples) até carros autônomos e assistentes virtuais complexos.

---

### Agente de Reflexo Simples

É o tipo mais básico de agente. Ele toma decisões baseadas **apenas na percepção atual**, ignorando todo o histórico de percepções anteriores.

* **Como funciona:** Opera através de regras de **condição-ação** (se [condição], então [ação]). Por exemplo, um termostato que liga o ar quando a temperatura passa de 25°C.
* **Limitação:** Só funciona bem em ambientes totalmente observáveis. Se uma parte da informação estiver oculta, o agente "fica cego".

### Agente de Reflexo Baseado em Modelo

Diferente do reflexo simples, este agente mantém um **estado interno** que descreve partes do mundo que ele não consegue ver no momento (o "modelo" do mundo).

* **Como funciona:** Ele atualiza esse estado interno com base em como o mundo evolui e como suas próprias ações afetam o ambiente. Isso permite que ele lide com a observabilidade parcial.
* **Vantagem:** Consegue "lembrar" que um objeto ainda existe mesmo que ele tenha saído do seu campo de visão momentaneamente.

### Agente Baseado em Objetivos

Além de saber como o mundo funciona, este agente precisa de informações sobre **metas ou objetivos** para decidir o que fazer.

* **Como funciona:** Ele avalia diferentes sequências de ações para ver qual delas o levará ao objetivo desejado. Envolve técnicas de **busca e planejamento**.
* **Diferencial:** É mais flexível que os anteriores. Se o objetivo mudar (ex: um destino diferente no GPS), o agente simplesmente recalcula o novo plano, enquanto um agente de reflexo teria que ter todas as suas regras reescritas.

### Agente de Aprendizado

É o tipo mais sofisticado, capaz de atuar em ambientes desconhecidos e se tornar mais competente do que era inicialmente.

* **Componentes principais:**
  * **Elemento de Aprendizado:** Responsável por fazer melhorias.
  * **Elemento de Desempenho:** Responsável por selecionar as ações externas (o que os outros agentes já fazem).
  * **Crítico:** Dá feedback sobre o sucesso das ações em relação a um padrão fixo.
  * **Gerador de Problemas:** Sugere ações que levarão a experiências novas e informativas (exploração).
* **Vantagem:** Consegue aprender com seus erros e se adaptar a mudanças complexas no ambiente ao longo do tempo.
