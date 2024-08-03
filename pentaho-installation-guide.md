# Tutorial de Instalação

## 1. Baixar o JDK (Java Development Kit)

1. **Acesse o link para download:**

   [OpenLogic OpenJDK Downloads](https://www.openlogic.com/openjdk-downloads?field_java_parent_version_target_id=All&field_operating_system_target_id=All&field_architecture_target_id=All&field_java_package_target_id=396)

2. **Baixe o arquivo `.msi`** para a versão do Java desejada.

3. **Instale o JDK** seguindo as instruções no instalador.

4. **Verifique as variáveis de ambiente:**

   - Abra o "Painel de Controle" e vá para "Sistema e Segurança" > "Sistema" > "Configurações avançadas do sistema".
   - Clique em "Variáveis de Ambiente".

   **Caso o JDK não tenha criado as variáveis automaticamente, siga os passos abaixo:**

   - **Crie a variável de sistema `JAVA_HOME`:**
     - Clique em "Nova..." em "Variáveis de sistema".
     - Nome da variável: `JAVA_HOME`
     - Valor da variável: Caminho para a pasta de instalação do JDK
     - *Exemplo:* `C:\Program Files\Java\jdk-XX`

   - **Adicione o caminho ao `Path`:**
     - Selecione a variável `Path` e clique em "Editar..."
     - Clique em "Novo" e adicione o caminho para a pasta `bin` dentro do diretório do JDK.
     - *Exemplo:* `C:\Program Files\Java\jdk-XX\bin`

## 2. Baixar o Pentaho Data Integration

1. **Acesse o link para download:**

   [Pentaho Data Integration (CE)](https://github.com/ambientelivre/legacy-pentaho-ce)

2. **Descompacte a pasta baixada.**

3. **Localize o arquivo executável do Spoon:**

   - No Windows, procure pelo arquivo `spoon.bat`.
   - No Linux ou macOS, procure pelo arquivo `spoon.sh`.

4. **Execute o Spoon:**

   - **Via Terminal:** Navegue até o diretório descompactado e execute o comando correspondente ao seu sistema operacional:
     - Windows: `spoon.bat`
     - Linux/macOS: `./spoon.sh`

   - **Criar um atalho na área de trabalho (opcional):**
     - No Windows, clique com o botão direito no arquivo `spoon.bat` e selecione "Enviar para" > "Área de trabalho (criar atalho)"
