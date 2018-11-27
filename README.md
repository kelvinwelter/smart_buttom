# Tutorial para Botão de Pânico usando Nanofox IoT

Essa página apresenta um passo a passo do procedimento necessário para realizar seu primeiro projeto Nanofox IoT: o botão de pânico. 

## Recomendações:
- Arduino IDE instalada no computador. Disponível em: https://www.arduino.cc/en/Guide/HomePage
- Conta cadastrada na plataforma Tago. Acesse: https://tago.io/
- Ativação do kit Nanofox IoT. Tutorial disponível em: https://github.com/Gridya/NANOFOX-Activate/blob/master/README.md

## Aplicação do Projeto:
  O projeto trata-se de um botão de pânico que quando pressionado irá disparar um comando que enviará um e-mail a contatos cadastrados. A escolha da aplicação se deu pensando principalmente para uso em locais fixos como creches ou pontos de ônibus por exemplo, que poderiam ser socorridos rapidamente em casos de emergência através do sinal Sigfox. Tratando-se assim, de um dispositivo de segurança a mais para pessoas nessa situação.

## Resumo das etapas:
  O nosso projeto será dividido em 4 etapas principais, além de etapas que não fazem parte do projeto em si mas que são necessárias para a execução de tal.
  
## Primeiro passo: Implementação do hardware
  Na nossa primeira etapa do projeto, iremos realizar a integração da placa Nanofox IoT com o botão. Faremos isso a partir do uso de um botão conectado no pino D2.
  
  .
  .
  .
  
## Segundo passo: Programação do firmware para o projeto
  Em nossa segunda etapa trabalharemos com programação dentro do Arduino IDE. O código do projeto está fornecido no seguinte link: Enquanto que aqui iremos realizar somente breves explicações sobre o código para esclarecer algumas dúvidas que possam surgir durante a implementação do código. 
  #### Bibliotecas necessárias:
  Para nosso simples projeto, precisamos incluir apenas a biblioteca `Nanofox.h`, que será necessária para a transmissão de dados para a rede Sigfox.
  #### Variáveis Globais:
  Nossas variáveis globais são necessárias para o correto funcionamento de funções da biblioteca Nanofox como a transmissão e recebimento de dados por exemplo.
  #### Função Setup:
  Finalmente em nossa função setup, iniciaremos nossa lógica propriamente dita. Como necessitamos da leitura de um botão no nosso projeto devemos tratar o pino correspondente a esse botão como *input*, juntamente disso escolhemos o pino que usaremos para esse botão. Nesse caso, iremos escolher o pino D2. 
Além da nossa configuração necessária para o projeto, devemos adicionar mais algumas coisas como a configuração do Arduino Nano IO e a inicialização do Modem Sigfox WISOL. Além disso, no código fornecido configuramos algumas mensagens para serem mostradas no monitor serial, essa parte é totalmente opcional e o código funciona sem ela.
  #### Função Loop: 
  Temos agora a parte principal do código. Nosso loop trabalha da seguinte forma: o botão é constantemente lido, se caso o valor lido no botão saía de 1 e vá para 0, ou seja, o botão for apertado. Nosso código entra no while e confere a leitura do botão 2 segundos depois através do delay. Se o botão continua apertado, então é enviado um sinal para a rede Sigfox através de funções da biblioteca Nanofox. Caso o botão não continue apertado após esses dois segundos, o código trata tal fato como se fosse um aperto acidental e não toma nenhuma atitude além de enviar uma mensagem no monitor serial. 


  

