# 3. Contexto para Produto/Protótipo

O **CamarVolt** será constituído por dois elementos principais:

- **Adaptador de tomada inteligente**  
- **Servidor de processamento e visualização de dados**

O objetivo do produto é monitorar e reportar o consumo de energia elétrica em tempo real, promovendo maior eficiência energética e controle de custos.

---

## 3.1 Ambiente de Uso

O aparelho será instalado diretamente em tomadas do padrão brasileiro (2P+T), atuando como um adaptador entre a tomada da parede e o dispositivo conectado.  
O protótipo foi projetado para uso em:

- Residências  
- Ambientes corporativos (prédios comerciais, escritórios)  
- Ambientes industriais (galpões, oficinas, fábricas)  

---

## 3.2 Usuários

| Categoria     | Perfil de Usuário                                         | Objetivo Principal                          |
|---------------|-----------------------------------------------------------|---------------------------------------------|
| Residenciais  | Moradores comuns                                          | Reduzir gastos e entender consumo energético |
| Corporativos  | Gestores prediais e técnicos de manutenção                | Monitorar vários pontos e otimizar consumo  |
| Industriais   | Engenheiros e técnicos de manutenção e eficiência energética | Prevenir sobrecargas e reduzir perdas elétricas |

---

## 3.4 Requisitos Funcionais

- RF1	O aparelho deve medir a corrente elétrica utilizando o sensor ZMCT103C.
- RF2	O microcontrolador ESP8266 deve processar os dados e enviá-los via rede Wi-Fi.
- RF3	O servidor central deve receber, armazenar e processar os dados de consumo.
- RF4	O sistema deve calcular consumo em tempo real e custo estimado com base em tarifas locais.
- RF5	O dashboard deve permitir visualização de dados em tempo real e históricos.
- RF6	O sistema deve permitir configuração de tarifas regionais e personalizadas.
- RF7	O sistema deve permitir registro de múltiplos dispositivos por usuário.
- RF8	O sistema deve alertar em caso de consumo anormal (opcional para MVP).
  
---

## 3.5 Requisitos Não Funcionais

- RNF1	O adaptador não deve ultrapassar 10 cm de profundidade e 5 cm de largura/altura.
- RNF2	O design deve ser semelhante a adaptadores tradicionais e visualmente neutro.
- RNF3	O material do adaptador deve minimizar riscos de incêndio e choque elétrico.
- RNF4	A comunicação entre adaptador e servidor deve ser criptografada (TLS/SSL).
- RNF5	O servidor deve suportar conexões simultâneas sem perda de dados.
- RNF6	O sistema deve operar continuamente, utilizando apenas a energia da tomada.
- RNF7	O firmware deve ser compatível com ambientes de desenvolvimento como Arduino IDE e PlatformIO.

## 3.6 Requisitos de Medição Elétrica

- RM1	O sistema deve medir corrente alternada entre 0 A e 15 A com precisão de ±5%.
- RM2	A medição deve ter uma taxa de amostragem mínima de 1 leitura por segundo.
- RM3	O sistema deve estimar a potência ativa (em Watts), considerando tensão média de 127V/220V.
- RM4	Deve haver compensação para distorções de sinal (ruído elétrico).
- RM5	Os dados devem ser registrados com timestamp preciso (sincronizado via NTP).

---

##3.7 Plataformas de Desenvolvimento

- Hardware: Protoboards, cabos jumper, fonte de bancada, multímetro.

- Estações de solda para montagem final.

### Software:

- Firmware: ESP8266 (Wemos D1 Mini) programado em C++ via Arduino IDE ou PlatformIO (VSCode).

- Servidor: Desenvolvido em Node.js, com banco de dados relacional (ex.: MySQL, PostgreSQL).

- Dashboard: Web responsivo usando HTML/CSS, JS e frameworks como React ou Vue.

## 3.8 Segurança e Confiabilidade

- A comunicação entre o adaptador e o servidor será criptografada utilizando TLS.

- O servidor será capaz de tratar simultaneamente múltiplas conexões de dispositivos distintos.

- A arquitetura visa operação contínua com reinício automático em caso de falhas.

- Logs de erro e de operação estarão disponíveis no servidor para diagnósticos.
