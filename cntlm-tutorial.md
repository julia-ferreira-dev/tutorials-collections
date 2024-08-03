# Tutorial de Instalação do Cntlm no Windows

## 1. Download do Instalador

- Baixe o instalador a partir do [Cntlm no SourceForge](https://sourceforge.net/projects/cntlm/).

## 2. Extraia o Arquivo

- Extraia a pasta do arquivo `.zip` baixado.

## 3. Execute o Arquivo `.exe`

> **Nota:** O Windows por padrão oculta as extensões de arquivos. Para visualizar as extensões, vá para "Modo de Exibição" e desmarque a opção "Ocultar extensões para tipos de arquivo conhecidos".

- Navegue até a pasta extraída e execute o arquivo `.exe` para iniciar a instalação.

## 4. Editar o Arquivo de Configurações `cntlm.ini`

> **Nota:** O arquivo `cntlm.ini` é um arquivo de texto. Recomenda-se editá-lo usando o Notepad++ para facilitar a edição.

- Abra o arquivo `cntlm.ini` localizado na pasta de instalação.
- Exclua todo o conteúdo do arquivo e substitua pelo seguinte:

  ```ini
  ### Primeira e última linhas devem ser de comentário - não remova esta linha para evitar bug ###
  Username <SEU LOGIN>
  Domain <DOMÍNIO>
  Proxy <SEU_PROXY>:3128
  # NoProxy localhost, 127.0.0.*, 10.*, 192.168.*, *.seudominio.com
  Listen 3128
  ### Fim do arquivo ###

- Substitua `<SEU LOGIN>`, `<DOMÍNIO>`, e `<SEU_PROXY>` com suas informações específicas.

## 5. Coleta das Hashes NTLM

- Para garantir a segurança do seu usuário, não é aconselhável usar senha em texto plano no Cntlm. Portanto, é necessário coletar as hashes NTLM usando o comando `cntlm -H`:
```shell
C:\Program Files\Cntlm>cntlm.exe -H
````
- Insira sua senha quando solicitado e copie as linhas `PassLM`, `PassNT`, e `PassNTLMv2` geradas.

## 6. Atualizar o Arquivo `cntlm.ini`

- Cole as linhas `PassLM`, `PassNT`, e `PassNTLMv2` abaixo da linha `Domain` no arquivo `cntlm.ini`.
- Salve as alterações.

## 7. Reiniciar o Serviço Cntlm

- Para reiniciar o serviço Cntlm pelo terminal, use o seguinte comando:
```shell
C:\Program Files\Cntlm>cntlm.exe -r
```
- Alternativamente, você pode reiniciar o serviço manualmente pelo serviços do sistema.
## 8. Configuração de Aplicativos para Usar o Cntlm

- Configure todos os softwares que precisam utilizar o Cntlm com as seguintes configurações de proxy:
>  **IP:** `127.0.0.1`
>  **Porta:** `3128`
## 9. Configurar Variáveis de Ambiente (Opcional)

- Se o Cntlm não foi adicionado às variáveis de ambiente do sistema, você pode configurá-lo manualmente:
- Abra "Painel de Controle" > "Sistema e Segurança" > "Sistema" > "Configurações avançadas do sistema" > "Variáveis de Ambiente".
- Adicione `cntlm` ao `Path` para facilitar o gerenciamento do serviço via terminal:

   
``` shell   
   cntlm -start 
   cntlm -stop   
   ````

## 10. Verificar se o Servidor Cntlm Está Funcionando

Após configurar o Cntlm e reiniciar o serviço, você pode verificar se ele está funcionando corretamente seguindo um dos passos abaixo:

### 10.1. Verificar o Status do Serviço

- No terminal, execute o seguinte comando para verificar se o Cntlm está em execução:

  ```shell
  C:\Program Files\Cntlm>cntlm.exe -t
   ```

- O comando `-t` verifica o status do servidor e deve retornar uma mensagem indicando que o Cntlm está ativo e escutando na porta configurada.
### 10.2. Usar o `netstat` para Verificar a Porta
> **Nota:** O comando `netstat` pode não estar habilitado por padrão em algumas versões do Windows. Caso não funcione, você pode precisar habilitar a função "Netstat" ou usar uma ferramenta alternativa.

- No terminal, execute o seguinte comando para verificar se a porta `3128` está sendo utilizada pelo Cntlm:

 ``` shell
-netstat -an | find "3128"
```

- Se o comando retornar uma linha com `0.0.0.0:3128` ou `127.0.0.1:3128`, isso indica que o Cntlm está escutando na porta correta.

