---
layout: post
title: "Primeira Postagem - Conhecendo mais sobre as séries"
author: "Ênio Abrantes"
date: 2017-07-09 20:16:26
published: true
tags: [htmlwidgets, r]
---


{% highlight r %}
library(tidyverse) 
{% endhighlight %}



{% highlight text %}
## Loading tidyverse: ggplot2
## Loading tidyverse: tibble
## Loading tidyverse: tidyr
## Loading tidyverse: readr
## Loading tidyverse: purrr
## Loading tidyverse: dplyr
{% endhighlight %}



{% highlight text %}
## Conflicts with tidy packages -----------------------------------------
{% endhighlight %}



{% highlight text %}
## filter(): dplyr, stats
## lag():    dplyr, stats
{% endhighlight %}



{% highlight r %}
# Leitura dos dados das séries.
dados <- read_csv(file = "../series_from_imdb.csv")
{% endhighlight %}



{% highlight text %}
## Error: '../series_from_imdb.csv' does not exist in current working directory ('C:/Users/enio/Documents/EnioAbrantes/_source/primeira-postagem').
{% endhighlight %}



{% highlight r %}
#Para iniciar a análise é preciso ver detalhadamente as informações referentes a cada uma das séries. Nos gráficos seguintes veremos diversos gráficos com informações relevante sobre a avaliação dos usuários.

# Mediana: É o valor que separa a metade maior e a metade menor de uma amostra.
# Desvio padrão: Indica uma medida de dispersão dos dados em torno de média amostral.
# IQR: Avalia o grau de espalhamento de dados (dispersão) em torno da medida de centralidade, basicamente subtraindo o terceiro quartil do primeiro quartil.

# Gráfico 1: Descreve a relação de cada temporada da série Narcos com a avaliação do usuários.
dados %>% filter(series_name %in% c("Narcos")) %>% 
  mutate(season = as.character(season)) %>% 
  ggplot(aes(x = season, y = UserRating, color = season)) + 
  geom_boxplot() +
  geom_point() + 
  stat_summary(fun.y=median, geom="line", aes(group=1))  + 
  stat_summary(fun.y=median, geom="point")
{% endhighlight %}



{% highlight text %}
## Error in eval(lhs, parent, parent): objeto 'dados' não encontrado
{% endhighlight %}



{% highlight r %}
# Gráfico 2: Descreve um boxplot de todos os episódios da série Narcos.
dados %>% filter(series_name %in% c("Narcos")) %>% 
  mutate(season = as.character(series_name)) %>% 
  ggplot(aes(x = series_name, y = UserRating, color = season)) + 
  geom_boxplot() + 
  geom_point() +
  geom_jitter(width = .1,
              height = 0,
              alpha = 0.7) 
{% endhighlight %}



{% highlight text %}
## Error in eval(lhs, parent, parent): objeto 'dados' não encontrado
{% endhighlight %}



{% highlight r %}
narcos <- dados %>% filter(series_name %in% c("Narcos"))
{% endhighlight %}



{% highlight text %}
## Error in eval(lhs, parent, parent): objeto 'dados' não encontrado
{% endhighlight %}



{% highlight r %}
# Calculo do valor da mediana para a série Narcos.
median(narcos$UserRating)
{% endhighlight %}



{% highlight text %}
## Error in median(narcos$UserRating): objeto 'narcos' não encontrado
{% endhighlight %}



{% highlight r %}
# Calculo do valor do desvio padrão para a série Narcos.
sd(narcos$UserRating)
{% endhighlight %}



{% highlight text %}
## Error in is.data.frame(x): objeto 'narcos' não encontrado
{% endhighlight %}



{% highlight r %}
# Calculo do IQR para a série Narcos.
IQR(narcos$UserRating)
{% endhighlight %}



{% highlight text %}
## Error in quantile(as.numeric(x), c(0.25, 0.75), na.rm = na.rm, names = FALSE, : objeto 'narcos' não encontrado
{% endhighlight %}



{% highlight r %}
# Gráfico 3: Descreve a relação de cada temporada da série Sherlock com a avaliação do usuários.
dados %>% filter(series_name %in% c("Sherlock")) %>% 
  mutate(season = as.character(season)) %>% 
  ggplot(aes(x = season, y = UserRating, color = season)) +
  geom_point() +
  geom_boxplot() + 
  stat_summary(fun.y=median, geom="line", aes(group=1))  + 
  stat_summary(fun.y=median, geom="point")
{% endhighlight %}



{% highlight text %}
## Error in eval(lhs, parent, parent): objeto 'dados' não encontrado
{% endhighlight %}



{% highlight r %}
# Gráfico 4: Descreve um boxplot de todos os episódios da série Sherlock.
dados %>% filter(series_name %in% c("Sherlock")) %>% 
  mutate(season = as.character(series_name)) %>% 
  ggplot(aes(x = series_name, y = UserRating, color = season)) + 
  geom_boxplot() +
  geom_point() 
{% endhighlight %}



{% highlight text %}
## Error in eval(lhs, parent, parent): objeto 'dados' não encontrado
{% endhighlight %}



{% highlight r %}
sherlock <- dados %>% filter(series_name %in% c("Sherlock"))
{% endhighlight %}



{% highlight text %}
## Error in eval(lhs, parent, parent): objeto 'dados' não encontrado
{% endhighlight %}



{% highlight r %}
# Calculo do valor da mediana para a série Sherlock.
median(sherlock$UserRating)
{% endhighlight %}



{% highlight text %}
## Error in median(sherlock$UserRating): objeto 'sherlock' não encontrado
{% endhighlight %}



{% highlight r %}
# Calculo do valor do desvio padrão para a série Sherlock.
sd(sherlock$UserRating)
{% endhighlight %}



{% highlight text %}
## Error in is.data.frame(x): objeto 'sherlock' não encontrado
{% endhighlight %}



{% highlight r %}
# Calculo do IQR para a série Sherlock.
IQR(sherlock$UserRating)
{% endhighlight %}



{% highlight text %}
## Error in quantile(as.numeric(x), c(0.25, 0.75), na.rm = na.rm, names = FALSE, : objeto 'sherlock' não encontrado
{% endhighlight %}



{% highlight r %}
# Gráfico 5: Descreve um boxplot de todos os episódios da série Stranger Things.
dados %>% filter(series_name %in% c("Stranger Things")) %>% 
  mutate(season = as.character(series_name)) %>% 
  ggplot(aes(x = series_name, y = UserRating, color = season)) + 
  geom_boxplot() +
  geom_point() 
{% endhighlight %}



{% highlight text %}
## Error in eval(lhs, parent, parent): objeto 'dados' não encontrado
{% endhighlight %}



{% highlight r %}
strangerThings <- dados %>% filter(series_name %in% c("Stranger Things"))
{% endhighlight %}



{% highlight text %}
## Error in eval(lhs, parent, parent): objeto 'dados' não encontrado
{% endhighlight %}



{% highlight r %}
# Calculo do valor da mediana para a série Stranger Things.
median(strangerThings$UserRating)
{% endhighlight %}



{% highlight text %}
## Error in median(strangerThings$UserRating): objeto 'strangerThings' não encontrado
{% endhighlight %}



{% highlight r %}
# Calculo do valor do desvio padrão para a série Stranger Things.
sd(strangerThings$UserRating)
{% endhighlight %}



{% highlight text %}
## Error in is.data.frame(x): objeto 'strangerThings' não encontrado
{% endhighlight %}



{% highlight r %}
# Calculo do IQR para a série Stranger Things.
IQR(strangerThings$UserRating)
{% endhighlight %}



{% highlight text %}
## Error in quantile(as.numeric(x), c(0.25, 0.75), na.rm = na.rm, names = FALSE, : objeto 'strangerThings' não encontrado
{% endhighlight %}



{% highlight r %}
# Gráfico 6: Descreve a relação de cada temporada da série Breaking Bad com a avaliação do usuários.
dados %>% filter(series_name %in% c("Breaking Bad")) %>% 
  mutate(season = as.character(season)) %>% 
  ggplot(aes(x = season, y = UserRating, color = season)) + 
  geom_boxplot() +
  geom_point() + 
  stat_summary(fun.y=median, geom="line", aes(group=1))  + 
  stat_summary(fun.y=median, geom="point") +
  geom_jitter(width = .1,
              height = 0,
              alpha = 0.7) 
{% endhighlight %}



{% highlight text %}
## Error in eval(lhs, parent, parent): objeto 'dados' não encontrado
{% endhighlight %}



{% highlight r %}
# Gráfico 7: Descreve um boxplot de todos os episódios da série Braking Bad.
dados %>% filter(series_name %in% c("Breaking Bad")) %>% 
  mutate(season = as.character(series_name)) %>% 
  ggplot(aes(x = series_name, y = UserRating, color = season)) + 
  geom_boxplot() +
  geom_point() +
  geom_jitter(width = .1,
              height = 0,
              alpha = 0.7) 
{% endhighlight %}



{% highlight text %}
## Error in eval(lhs, parent, parent): objeto 'dados' não encontrado
{% endhighlight %}



{% highlight r %}
breakingBad <- dados %>% filter(series_name %in% c("Breaking Bad"))
{% endhighlight %}



{% highlight text %}
## Error in eval(lhs, parent, parent): objeto 'dados' não encontrado
{% endhighlight %}



{% highlight r %}
# Calculo do valor da mediana para a série Breaking Bad.
median(breakingBad$UserRating)
{% endhighlight %}



{% highlight text %}
## Error in median(breakingBad$UserRating): objeto 'breakingBad' não encontrado
{% endhighlight %}



{% highlight r %}
# Calculo do valor do desvio padrão para a série Braaking Bad.
sd(breakingBad$UserRating)
{% endhighlight %}



{% highlight text %}
## Error in is.data.frame(x): objeto 'breakingBad' não encontrado
{% endhighlight %}



{% highlight r %}
# Calculo do IQR para a série Breaking Bad.
IQR(breakingBad$UserRating)
{% endhighlight %}



{% highlight text %}
## Error in quantile(as.numeric(x), c(0.25, 0.75), na.rm = na.rm, names = FALSE, : objeto 'breakingBad' não encontrado
{% endhighlight %}



{% highlight r %}
# Gráfico 7: Descreve um boxplot para cada série analisada onde as medianas de cada uma estão ligadas.
dados %>% filter(series_name %in% c("Narcos", "Sherlock", "Stranger Things", "Breaking Bad")) %>% 
  mutate(season = as.character(series_name)) %>% 
  ggplot(aes(x = series_name, y = UserRating, color = season)) + 
  geom_boxplot() +
  geom_point() + 
  stat_summary(fun.y=median, geom="line", aes(group=1))  + 
  stat_summary(fun.y=median, geom="point") +
  geom_jitter(width = .1) 
{% endhighlight %}



{% highlight text %}
## Error in eval(lhs, parent, parent): objeto 'dados' não encontrado
{% endhighlight %}



{% highlight r %}
selectedSeries <- dados %>% filter(series_name %in% c("Narcos", "Sherlock", "Stranger Things", "Breaking Bad"))
{% endhighlight %}



{% highlight text %}
## Error in eval(lhs, parent, parent): objeto 'dados' não encontrado
{% endhighlight %}



{% highlight r %}
# Calculo do valor da mediana para todas as 4 séries vistas acima.
median(selectedSeries$UserRating)
{% endhighlight %}



{% highlight text %}
## Error in median(selectedSeries$UserRating): objeto 'selectedSeries' não encontrado
{% endhighlight %}



{% highlight r %}
# Calculo do valor do desvio padrão para todas as 4 séries vistas acima.
sd(selectedSeries$UserRating)
{% endhighlight %}



{% highlight text %}
## Error in is.data.frame(x): objeto 'selectedSeries' não encontrado
{% endhighlight %}



{% highlight r %}
# Calculo do IQR para todas as 4 séries vistas acima.
IQR(selectedSeries$UserRating)
{% endhighlight %}



{% highlight text %}
## Error in quantile(as.numeric(x), c(0.25, 0.75), na.rm = na.rm, names = FALSE, : objeto 'selectedSeries' não encontrado
{% endhighlight %}



{% highlight r %}
# Agora que já temos tomas as informações necessárias vamos reponder as questões.
# a. Qual das séries que você escolheu é mais bem avaliada no IMDB? A diferença é grande? Pequena? 
# Apesar de Breaking Bad obter um número expressivo de boas notas, chegando até a obter nota 10, eu avalio Sherlock como sendo a melhor a série pois entre outros motivos conseguiu obter uma mediana de 9, coisa que nenhuma outra conseguiu atingir, com a segunda maior mediana está a série Stranger Things que conseguiu superar somente a quarta temporada de Sherlock, entretanto conseguiu ter uma mediana melhor do que quatro temporadas entre cinco de Breaking Bad. A diferença eu avalio como sendo bem pequena por terem medianas bem próximas(9, 8.95, 8.9) e por não haver uma vantagem absoluta entre as temporadas. OBS: A série narcos acabou ficando em quarto lugar de acordo com as avaliações do IMDB, porém como seguidor das 4 séries avaliadas eu prefiro Narcos.
# b. Qual das séries que você escolheu tem episódios de qualidade mais irregular segundo o IMDB? A diferença é grande? Pequena?
# Eu classificaria a série série Breaking Bad como sendo a mais irregular apesar de ter os valores de IQR e desvio padrão inferiores a série Sherlock. Essa classificação se dá a partir de uma boa observada no gráfico 6, nele podemos ver que a primeira temporada tem uma mediana bem abaixo da mediana geral da série, na segunda temporada temos uma melhoria considerável fazendo com que chegue bem próximo da mediana geral, na terceira temporada ocorre uma queda fazendo com que se distancie da mediana geral da série, na quarta temporada ocorreu uma melhoria semelhante ao que aconteceu entre a primeira e segunda temporada, já na quinta temporada ocorre uma elevação bastante significativa, fugindo dos padrões anterioes, fazendo com que a mediana da quinta temporada gire em torno de 9.4, elevando bastante a mediana geral da série. Na série Sherlock podemos observar com facilidade um pico na segunda temporada que acabou sendo desproporcional com relação as outras temporadas além de ter os maiores valores de IQR e desvio padrão. A diferença acabou sendo bem pequena, ficando sujeito a outras interpretações indicando o contrário, seja pelo fato de valores de IQR e desvio padrão tão próximos quanto pela interpretação dos gráficos.
{% endhighlight %}

