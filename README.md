# tcp-ip
Passo a passo da camada tcp/ip
<p>O TCP ("Transmission Control Protocol" ou "Protocolo de Controle de Transmissão") é um dos principais protocolos de comunicação da Internet, usado para garantir a transferência confiável de dados entre dispositivos.</p>
<p>Ele opera na Camada de Transporte do modelo OSI (ou do modelo TCP/IP) e divide as funções em várias etapas. Vamos explicar o passo a passo e o propósito de cada fase.</p>

## 1. Estabelecimento da Conexão ("Three-Way Handshake" ou "Aperto de mão triplo")
<p>O TCP é um protocolo orientado à conexão, ou seja, antes de transmitir dados, os dispositivos precisam estabelecer uma conexão confiável.</p>

<p>Passos:</p>
<p>SYN ("Synchronize" ou "Sincronizar"):</p>
<p>O dispositivo A (cliente) envia uma mensagem SYN para o dispositivo B (servidor), indicando que deseja iniciar a comunicação.</p>
SYN-ACK ("Synchronize-Acknowledge" ou "Sincronizar-Reconhecer"):
<p>O dispositivo B responde com uma mensagem SYN-ACK, confirmando a solicitação e dizendo que também está pronto para a comunicação.</p>
<p>ACK ("Acknowledge" ou "Reconhecer"):</p>
<p>O dispositivo A confirma o recebimento do SYN-ACK enviando um ACK. A conexão agora está estabelecida.</p>
<p>Objetivo:</p>
<p>Estabelecer uma conexão confiável entre os dispositivos, sincronizando os números de sequência para o envio de dados.</p>

## 2. Transferência de Dados
<p>Após a conexão ser estabelecida, os dados podem ser transmitidos em segmentos TCP.</p>
<p>Passos:</p>
<p>Divisão dos Dados em Segmentos:</p>
<p>O TCP divide os dados em partes menores chamadas de segmentos e os numera sequencialmente.</p>
<p>Envio e Reconhecimento:</p>
<p>Cada segmento enviado recebe um número de sequência.</p>
<p>Quando o receptor recebe o segmento, ele envia um ACK (confirmação) com o próximo número esperado.</p>
<p>Retransmissão em Caso de Erro:</p>
<p>Se um segmento for perdido ou corrompido durante a transmissão, o receptor não enviará um ACK, e o remetente retransmitirá o segmento perdido.</p>
<p>Objetivo:</p>
<p>Garantir que todos os dados sejam entregues na ordem correta e sem perda.</p>

## 3. Controle de Fluxo
<p>O TCP usa um mecanismo chamado Janela Deslizante para ajustar a quantidade de dados que pode ser enviada antes de receber uma confirmação do receptor.</p>
<p>Como funciona:</p>
<p>O receptor informa o tamanho da janela (a quantidade de dados que pode processar de uma vez).</p>
<p>O remetente ajusta sua taxa de envio para não sobrecarregar o receptor.</p>
<p>Objetivo:</p>
<p>Evitar congestionamento ou sobrecarga, garantindo que os dispositivos não enviem mais dados do que o receptor pode lidar.</p>

## 4. Controle de Congestionamento
<p>Se houver congestionamento na rede (muitas transmissões ao mesmo tempo), o TCP reduz a velocidade de envio.</p>
<p>Como funciona:</p>
<p>O protocolo usa algoritmos como o Slow Start para detectar congestionamento e diminuir a taxa de transmissão.</p>
<p>Conforme a rede se estabiliza, o TCP aumenta gradualmente a taxa de envio.</p>
<p>Objetivo:</p>
<p>Evitar perda de pacotes devido ao congestionamento da rede.</p>

## 5. Finalização da Conexão ("Four-Way Handshake" ou "Aperto de mão de quatro vias")
<p>Depois que os dados foram transferidos, a conexão precisa ser encerrada.</p>
<p>Passos:</p>
<p>O dispositivo A envia um FIN ("Finish" ou "Terminar") para indicar que terminou de enviar dados.</p>
<p>O dispositivo B responde com um ACK para confirmar o FIN.</p>
<p>O dispositivo B também envia um FIN quando termina de enviar seus dados.</p>
<p>O dispositivo A responde com um ACK para confirmar o encerramento.</p>
<p>Objetivo:</p>
<p>Finalizar a conexão de forma ordenada, garantindo que todos os dados foram transmitidos.</p>

<p><h3>Resumo das Funções do TCP</h3></p>
<p>Confiabilidade: Garante que os dados sejam entregues corretamente e na ordem certa.</p>
<p>Controle de Fluxo: Ajusta a taxa de envio de dados para evitar sobrecarga no receptor.</p>
<p>Controle de Congestionamento: Reduz a taxa de envio em caso de congestionamento na rede.</p>
<p>Entrega Segura: Retransmite dados perdidos ou corrompidos.</p>
<p>Por Que o TCP é Importante?</p>
<p>O TCP é usado em aplicações onde a confiabilidade é essencial, como:</p>

<p><h3>Navegadores (HTTP/HTTPS)</h3></p>
<p>Transferência de arquivos (FTP)</p>
<p>E-mails (SMTP, IMAP, POP3)</p>
