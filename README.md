<img width=100% src="https://capsule-render.vercel.app/api?type=waving&color=00bfbf&height=120&section=header"/>
<h1 align="center"><img align="center" style="border-radius: 100%;" src="https://github.com/user-attachments/assets/d96d3f73-4cff-4f9f-9feb-cf8a7ccfd9d3" width="300px;" alt=""><br>Comunicação Serial BitDogLab</h1>

<h3 align="center">
   Comunicação Serial na placa BitDogLab em Linguagem C
</h3>

---

Tabela de conteúdos
=================
<!--ts-->
   * [Sobre o projeto](#-sobre-o-projeto)
   * [Layout Repositorio Github](#-layout-repositorio-github)
   * [Funcionalidades](#-Funcionalidades)
   * [Como executar o projeto](#-como-executar-o-projeto)
   * [Imagens do Projeto](#-imagens-do-projeto)
     * [Imagem](#-projeto-na-extensão-wokwi-simulator-no-visual-studio)
   * [Tecnologias](#-tecnologias)
     * [Websites](#-websites)
     * [Utilitários](#user-content-server--nodejs----typescript)
   * [Contribuidores](#-contribuidores)
   * [Licença](#-licença)
<!--te-->

---

## 💻 Sobre o projeto

Este projeto implementa a comunicação serial e a interação entre a placa BitDogLab (Raspberry Pi Pico W) e diversos componentes, incluindo uma matriz de LEDs WS2812, um LED RGB, botões físicos e um display SSD1306.

Os principais objetivos incluem:
- Exibir caracteres digitados no Serial Monitor no display SSD1306.
- Exibir números na matriz 5x5 WS2812 conforme digitado no Serial Monitor.
- Alternar estados do LED RGB ao pressionar os botões A e B.
- Registrar operações via Serial Monitor e no display SSD1306.

### Componentes Utilizados
- Matriz de LEDs WS2812 (5x5) - Conectada à GPIO 7.
- LED RGB - Conectado às GPIOs 11, 12 e 13.
- Botão A - Conectado à GPIO 5.
- Botão B - Conectado à GPIO 6.
- Display SSD1306 (I2C) - Conectado às GPIOs 14 e 15.


## 🎨 Layout Repositorio Github
<i>
EmbarcaTech_U4_Atvd6

   - assets/&emsp;&emsp;&emsp;&emsp;# Midias do Projeto
       - diagrama.png
       - Video_Demonstration

   - CMakeLists.txt
   
   - diagram.json&emsp;&emsp;&emsp;&emsp;# Arquivo Wokwi do BitDogLab
   
   - main.c&emsp;&emsp;&emsp;&emsp; # Código principal do projeto
   
   - pico_sdk_import.cmake
   
   - wokwi.toml


</i>

---

## ⚙️ Funcionalidades

### Modificação da Biblioteca font.h
- Adicionar caracteres minúsculos ao font.h para exibição no display SSD1306.

### Entrada de Caracteres via Serial Monitor
- Exibir o caractere digitado no Serial Monitor no display SSD1306.
- Caso um número de 0 a 9 seja digitado, exibir um símbolo correspondente na matriz 5x5 WS2812.
### Interação com os Botões
- Botão A (GPIO 5): Alterna o estado do LED Verde (GPIO 13).
- Exibe mensagem no display SSD1306.
- Envia um texto descritivo ao Serial Monitor.
- Botão B (GPIO 6): Alterna o estado do LED Azul (GPIO 11).
- Exibe mensagem no display SSD1306.
- Envia um texto descritivo ao Serial Monitor.

---

## 🚀 Como executar o projeto

💡Siga as instruções abaixo para configurar, compilar e executar o programa.

### Pré-requisitos

Antes de começar, você vai precisar ter instalado em sua máquina as seguintes ferramentas:
  - Sistema operacional Linux, macOS ou Windows (com suporte a Makefile).
  - [Git](https://git-scm.com) (Opcional, mas recomendado),
  - [GCC compilador](https://gcc.gnu.org)
  - [Biblioteca Pico-Sdk](https://github.com/raspberrypi/pico-sdk.git) (OBS: Necessário caso queira modificar o projeto)

Além disto é bom ter um editor para trabalhar com o código como [VSCode](https://code.visualstudio.com/) com a extensão [Raspberry](https://marketplace.visualstudio.com/items?itemName=raspberry-pi.raspberry-pi-pico)  e usar o simulador web [Wokwi](https://wokwi.com) (ou a extensão do Vscode [Wokwi Simulator](https://marketplace.visualstudio.com/items?itemName=Wokwi.wokwi-vscode))

### 🎲 Dowload do Projeto

#### Dowload do Projeto no Desktop
- Opção 1:
  - Abra o terminal de comando Git Bash 
  - Clone o repositório do GitHub com o comando:
```
$ git clone https://github.com/Dyeorn/EmbarcaTech_U4_Atvd6
```
- Opção 2:
  - No repósitorio [EmbarcaTech_U4_Clock-Temporizadores](https://github.com/Dyeorn/EmbarcaTech_U4_Atvd6) aperte o Botão <i><>code</i>
  - Aperte a opção <i>Dowload ZIP</i>


### 🎲 Rodando a Animação no Wokwi

#### Wokwi Web
- Entre no navegador e digite [Wokwi.com]()
- Faça Upload dos Arquivos <i>diagram.json</i>
- Faça upload do aquivo main <i>main.c</i> e da pasta <i>src/</i>

#### Extensão Wokwi
- Abra o Visual Studio
- Na aba da extensão [Raspberry Pi Pico](https://marketplace.visualstudio.com/items?itemName=raspberry-pi.raspberry-pi-pico), aperte para Importar o projeto
- Compile o projeto
- crie um arquivo (caso não tenha no projeto) <i>wokwi.toml</i> e digite o código:
```
[wokwi]
version = 1
firmware = 'build/main.hex'
elf = 'build/main.elf'
```
- Abra o arquivo <i>diagram.json</i>


### 🎲 Rodando as Animações na placa BitdogLab

#### Placa BitDogLab
- Através de um cabo USB conecte a placa ao seu Disposito
- Aperte o Botão Bootsel e Reset 

#### VsCode Studio
- Abra o Visual Studio
- Na aba da extensão [Raspberry Pi Pico](https://marketplace.visualstudio.com/items?itemName=raspberry-pi.raspberry-pi-pico), aperte para Importar o projeto
- Compile o projeto
- Entre na pasta <i>build/</i>
- Cole o arquivo <i>nmain.uf2</i> no armazenamento placa BitDog
- Ou, apenas compile o projeto e clique em "Run Project (USB)
<br>

---

## 🎥 Imagens do Projeto

### 💿 Diagrama Visual do Projeto

Atividade 1:
<p align="center"><img width="700" height="400" src="assets/Diagrama.png"></p>

---

## 🛠 Tecnologias

As seguintes ferramentas foram usadas na construção do projeto:

#### **Websites**
-   **[Github](https://github.com)**
-   **[Wokwi Web](https://gcc.gnu.org)**


#### **Utilitários**

-   Editor:  **[Visual Studio Code](https://code.visualstudio.com/)**  → Extensions:  **[C/C++](https://marketplace.visualstudio.com/items?itemName=ms-vscode.cpptools), [C/C++ Compile Run](https://marketplace.visualstudio.com/items?itemName=danielpinto8zz6.c-cpp-compile-run), [Raspberry Pi Pico](https://marketplace.visualstudio.com/items?itemName=raspberry-pi.raspberry-pi-pico) e [Wokwi Simulator](https://marketplace.visualstudio.com/items?itemName=Wokwi.wokwi-vscode)**

### **Versionamento**
-   **[Git](https://git-scm.com)**


---

## 👨‍💻 Contribuidores

- João Pedro Jacó Leite
- Mentor: MANOEL MESSIAS DA SILVA JUNIOR

<table>
  <tr>
    <td align="center"><img style="border-radius: 50%;" src="https://avatars.githubusercontent.com/u/112970376?v=4" width="100px;"/><br/><a href="https://github.com/Dyeorn">João Pedro Jacó<a/><br/><br/><a title="Integrante">🌐</a></td>
  </tr>
</table>
      
---

<img width=100% src="https://capsule-render.vercel.app/api?type=waving&color=00bfbf&height=120&section=footer"/>

