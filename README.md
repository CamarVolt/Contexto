# Contexto
Item 3 do template 

## 3 Contexto para Produto/Protótipo

O CamarVolt será constituído por dois elementos principais: **o aparelho adaptador de tomada inteligente** e **o servidor de processamento e visualização de dados**.  

### 3.1 Ambiente de uso
O aparelho será instalado diretamente em tomadas padrão brasileiro (2P+T), funcionando como um adaptador entre a tomada da parede e o dispositivo conectado.  
O protótipo foi projetado para residências, empresas e ambientes industriais, onde o monitoramento de consumo de energia elétrica é relevante.  

### 3.2 Usuários
- **Residenciais:** moradores que desejam acompanhar e reduzir gastos de energia.  
- **Corporativos:** administradores de edifícios e gestores de manutenção.  
- **Industriais:** engenheiros e técnicos interessados em eficiência energética e prevenção de sobrecargas.  

### 3.3 Fluxo de interação
1. O **aparelho adaptador** coleta informações de corrente elétrica através do sensor ZMCT103C, processa localmente com o módulo Wemos ESP8266 e transmite os dados via rede Wi-Fi.  
2. Os dados são enviados de forma segura para o **servidor central**, que pode estar hospedado localmente em um computador ou em uma plataforma em nuvem (AWS, Azure, Oracle, etc.).  
3. O servidor recebe os dados, armazena-os em um banco de dados e processa os valores de consumo.  
4. O **dashboard web** permite que os usuários visualizem consumo em tempo real, relatórios históricos e valores calculados de custo de energia.  
5. Presets regionais (como tarifa de energia elétrica em Joinville) podem ser utilizados, além de valores customizados fornecidos pelo usuário.  

### 3.4 Restrições físicas e de design
- O adaptador não deve ultrapassar **10 cm** em profundidade nem **5 cm** em largura/altura em relação à tomada.  
- O aparelho deve ser visualmente semelhante a adaptadores tradicionais, não podendo conter aparência ofensiva.  
- Materiais e design devem reduzir risco de fogo e evitar choques elétricos.  

### 3.5 Plataformas de desenvolvimento
Para prototipagem, serão utilizados equipamentos de soldagem, protoboard, cabos jumper e ferramentas de programação (ex.: **VSCode + NodeJS**).  
O firmware será gravado no **ESP8266** através de cabo USB e ambiente de desenvolvimento compatível (Arduino IDE ou PlatformIO).  

### 3.6 Segurança e confiabilidade
- A comunicação entre aparelho e servidor deve ser **criptografada**.  
- O servidor deve tratar múltiplos dispositivos simultaneamente, sem perda ou desintegração de dados.  
- Tanto o aparelho quanto o servidor devem operar continuamente, utilizando apenas energia fornecida pela tomada (no caso do aparelho).  
