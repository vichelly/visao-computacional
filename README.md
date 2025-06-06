# Análise de Imagens com Visão Computacional

Este repositório apresenta um projeto de processamento de imagens que utiliza técnicas de visão computacional. Ele demonstra uma sequência de operações para analisar e extrair informações visuais de diferentes tipos de imagens.

## Como Utilizar

Para executar este código e gerar os relatórios visuais, siga estes passos:

1. Abra o notebook no Google Colab: Você pode carregar o arquivo .ipynb fornecido neste repositório diretamente no Google Colab.
2. Ajuste o caminho da imagem: Dentro do código, localize a variável nome_do_arquivo_imagem. Altere seu valor para o nome do arquivo da imagem que você quer processar (por exemplo, 'minha_foto.jpg'). Certifique-se de que a imagem esteja no ambiente do Colab ou acessível via um caminho válido.
3. Execute as células: Siga a ordem das células no notebook e execute-as. O código vai processar a imagem e exibir os resultados gráficos, além de salvá-los no seu ambiente.

## Detalhamento das Etapas de Processamento

O processo de análise da imagem é dividido em várias fases, cada uma contribuindo para a extração de características e o aprimoramento da visualização:

Leitura da Imagem Original: A imagem é lida do seu local de armazenamento para ser carregada na memória do programa.
Ajuste de Canais de Cores (BGR para RGB): Imagens carregadas pelo OpenCV vêm no formato BGR (Azul, Verde, Vermelho). Para garantir a correta exibição e compatibilidade com outras bibliotecas como Matplotlib, a imagem é convertida para o padrão RGB (Vermelho, Verde, Azul).
Aplicação de Desfoque Suave: Um filtro de média (kernel 5x5) é aplicado para suavizar a imagem, reduzindo ruídos e preparando-a para as etapas seguintes, como detecção de bordas.
Conversão para Tons de Cinza: A imagem colorida é transformada em uma versão em escala de cinza. Isso simplifica cálculos posteriores e foca na intensidade dos pixels, não na cor.
Limiarização Binária: Um limite é definido para converter a imagem em tons de cinza em uma imagem binária (preto e branco). Isso ajuda a segmentar objetos do fundo, facilitando a identificação de formas.
Operações Morfológicas:
        Dilatação: Expande as áreas brancas de uma imagem, útil para preencher pequenas lacunas ou conectar regiões próximas.
        Erosão: Contrai as áreas brancas, o que pode ajudar a remover pequenos ruídos ou separar objetos conectados.
        Abertura: Realiza uma erosão seguida de uma dilatação. Essa sequência é eficaz para remover pequenos objetos (ruídos) sem distorcer significativamente as formas maiores.
        Fechamento: Inverte a ordem, realizando uma dilatação seguida de uma erosão. É ideal para fechar pequenos buracos dentro de objetos e conectar componentes próximos.
Detecção de Bordas (Canny): O algoritmo de Canny é usado para identificar as bordas nítidas na imagem, baseando-se nas variações de intensidade dos pixels.
Identificação de Contornos: A partir da imagem processada (especialmente a binária e após operações morfológicas), são encontrados os contornos que representam os limites dos objetos.
Desenho de Contornos Finais: Os contornos detectados são sobrepostos à imagem original em RGB, geralmente destacados em uma cor específica (como azul), para apresentar o resultado final da análise.

Exemplos de Saída

Abaixo estão alguns exemplos dos resultados visuais gerados após o processamento de diferentes imagens:

## Resultados
![Imagem](https://raw.githubusercontent.com/vichelly/visao-computacional/refs/heads/master/girafa2.png)
![Imagem](https://raw.githubusercontent.com/vichelly/visao-computacional/refs/heads/master/girafa3.png)
![Imagem](https://raw.githubusercontent.com/vichelly/visao-computacional/refs/heads/master/aviao2.png)
![Imagem](https://raw.githubusercontent.com/vichelly/visao-computacional/refs/heads/master/aviao3.png)
![Imagem](https://raw.githubusercontent.com/vichelly/visao-computacional/refs/heads/master/satelite2.png)
![Imagem](https://raw.githubusercontent.com/vichelly/visao-computacional/refs/heads/master/satelite3.png)


