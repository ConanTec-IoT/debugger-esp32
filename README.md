<img width="100%" src="https://capsule-render.vercel.app/api?type=waving&color=C62718&height=120&section=header"/>

# Debugando o ESP32 com ESP-Prog

Este repositório apresenta um exemplo prático e direto de como utilizar a placa **ESP-Prog**, da Espressif, para depurar (debugar) aplicações no **ESP32** via interface **JTAG**.

O exemplo consiste em um simples **blink** utilizando o LED onboard da placa, com o código desenvolvido no ambiente **PlatformIO**.

---

## 🔧 Ligações ESP32 ↔ ESP-Prog (JTAG)

Para que a depuração funcione corretamente, é necessário realizar as conexões entre os pinos JTAG do ESP32 e do ESP-Prog conforme a tabela abaixo:

| Pino ESP32 | Pino ESP-Prog | Observações                                                           |
| ---------- | ------------- | --------------------------------------------------------------------- |
| GPIO15     | TDO           | Saída de dados do debug                                               |
| GPIO14     | TMS           | Sinal de seleção de teste                                             |
| GPIO13     | TCK           | Clock do barramento JTAG                                              |
| GPIO12     | TDI           | Entrada de dados do debug                                             |
| GND        | GND           | Todos os GNDs devem estar conectados entre si                         |
| 5V         | VPROG         | Certifique-se de que o jumper do ESP-Prog esteja ajustado para **5V** |

---

## ▶️ Executando o Debug

Com todas as conexões devidamente feitas, basta:

1. Abrir o projeto no **VS Code + PlatformIO**;
2. Clicar em **"Run Debugger"** ou pressionar **F5**;
3. O código será carregado no ESP32, e a aplicação poderá ser depurada passo a passo, com breakpoints, inspeção de variáveis e mais.

---

## 📎 Links úteis

* [ESP32 - Debugging your ESP-IDF code using JTAG \[VS Code\]](https://www.youtube.com/watch?v=uq93H7T7cOQ)
* [A very comprehensive ESP32 Debugging Guide.](https://www.youtube.com/watch?v=ENLhW0MQuu0)
