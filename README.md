# Classificação de digitos usando Redes Convolucionais e o dataset MNIST.

Rode o código no [Google Collab](colab.research.google.com/drive/1QtcMR7E9p11DZEYILknSOnw2DfQso0dS)

O objetivo deste desafio foi desenvolver um classificador básico para o conjunto de dados MNIST usando uma Convolutional Neural Network (CNN). Este relatório aborda as escolhas e decisões feitas durante o processo de implementação.

1. Pré-processamento:
Os pixels das imagens foram normalizados para o intervalo [0, 1] dividindo por 255. Isso ajuda na convergência mais rápida do modelo e facilita o treinamento.

2. Escolha da CNN:
Optei por uma CNN devido à sua eficácia com matrizes, ou melhor, imagens. As CNNs são conhecidas por sua capacidade de aprender características espaciais, o que é essencial para reconhecer padrões em imagens, como os dígitos manuscritos do MNIST. 

3. Arquitetura da Rede:
A arquitetura foi escolhida seguindo princípios convencionais de CNN para classificação de imagens. Utilizei três camadas convolutivas (Conv2D) de tamanhos diferentes para tentar capturar todas as features espaciais das imagens. A etapa convolutiva é seguida por camadas de max pooling (MaxPooling2D) para redução de dimensionalidade. Isso foi feito para capturar características mas importantes e reduzir o tamanho dos mapas de características, potencialmente otimizando o trabalho computacional e reduzindo a chance de overfitting.

4. Camadas Densas e Softmax:
Após as camadas convolutivas e de pooling, adicionei duas camadas densas (Dense). A primeira visa conectar todas as features restantes para aprendizado de características mais abstratas, e a ultima é a camada de saída com ativação softmax para classificação dos 10 dígitos.

5. Função de Perda e Otimizador:
A função de perda escolhida foi a categorical_crossentropy, adequada para problemas de classificação multiclasse. O otimizador "adam" foi selecionado por sua eficiência em otimização de redes neurais.

6. Treinamento e Avaliação:
O modelo foi treinado por 5 épocas com um tamanho de lote de 64. Durante o treinamento, monitorei a perda e a precisão tanto nos dados de treinamento quanto nos dados de validação para avaliar a performance e verificar o overfitting.

7. Resultados:
Após a realização do treinamento diversas vezes, o modelo constantemente alcança a precisões na faixa de 98.9% a 99.3% nos dados de validação. Isso sugere que o modelo está aprendendo bem os padrões nos dados de treinamento e generalizando adequadamente para dados não vistos.

Conclusão:
A abordagem utilizada demonstrou ser eficaz na classificação dos dígitos MNIST. No entanto, para aplicações práticas, poderíamos explorar outras arquiteturas mais complexas, realizar ajustes nos hiperparâmetros e aplicar outras técnicas de normalização para melhorar ainda mais a precisão e a generalização do modelo. É importante ressaltar que este é um problema clássico com soluções muito boas já realizadas. Este quase sempre não é o caso no mundo real onde resolve-se problemas específicos muitas vezes nunca antes vistos.


