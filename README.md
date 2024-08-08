# ambientevirtualpyenv
Usando ambiente virtual no Python com Pyenv

Esses comandos são utilizados para gerenciar e configurar o ambiente Python no Windows, incluindo a instalação de versões do Python e o uso de ferramentas como `pyenv` e `poetry`. Vou explicar cada um deles:

1. **Instalar o Pyenv-Win:**
   ```powershell
   Invoke-WebRequest -UseBasicParsing -Uri "https://raw.githubusercontent.com/pyenv-win/pyenv-win/master/pyenv-win/install-pyenv-win.ps1" -OutFile "./install-pyenv-win.ps1"; &"./install-pyenv-win.ps1"
   ```
   - Este comando faz o download de um script do GitHub que instala o Pyenv-Win, uma ferramenta para gerenciar diferentes versões do Python no Windows. O comando baixa o script para o diretório atual e, em seguida, o executa.

2. **Configurar a política de execução do PowerShell:**
   ```powershell
   Set-ExecutionPolicy -ExecutionPolicy RemoteSigned -Scope LocalMachine
   ```
   - Este comando define a política de execução do PowerShell para permitir que scripts baixados da internet sejam executados, desde que sejam assinados digitalmente. Isso é necessário para garantir que o script do Pyenv-Win possa ser executado corretamente.

3. **Instalar e configurar uma versão específica do Python:**
   ```powershell
   pyenv install 3.12.4
   pyenv global 3.12.4
   pyenv versions
   python -v
   ```
   - `pyenv install 3.12.4`: Instala a versão 3.12.4 do Python usando o Pyenv-Win.
   - `pyenv global 3.12.4`: Define a versão 3.12.4 como a versão global do Python, ou seja, a versão padrão usada no sistema.
   - `pyenv versions`: Lista todas as versões do Python instaladas no sistema gerenciadas pelo Pyenv.
   - `python -v`: Verifica a versão atual do Python instalada e configurada como padrão.

4. **Instalar o Poetry e gerenciar ambientes virtuais:**
   ```powershell
   pip install poetry
   ```
   - Este comando instala o `Poetry`, uma ferramenta para gerenciar dependências de projetos Python e ambientes virtuais.

5. **Criar um novo projeto com o Poetry:**
   ```powershell
   poetry new nome_do_projeto
   poetry config --list
   ```
   - `poetry new nome_do_projeto`: Cria uma nova estrutura de projeto Python com o nome especificado.
   - `poetry config --list`: Lista as configurações atuais do Poetry.

6. **Configurar o Poetry para criar ambientes virtuais no diretório do projeto:**
   ```powershell
   poetry config virtualenvs.in-project true
   poetry config --list
   ```
   - `poetry config virtualenvs.in-project true`: Configura o Poetry para criar o ambiente virtual dentro do diretório do projeto, em vez de um local global no sistema.
   - `poetry config --list`: Verifica novamente as configurações para garantir que a mudança foi aplicada.

7. **Ativar o ambiente virtual do projeto:**
   ```powershell
   poetry shell
   ```
   - Este comando ativa o ambiente virtual criado para o projeto, permitindo que você instale dependências e execute scripts dentro desse ambiente isolado.

8. **Adicionar bibliotecas ao projeto:**
   ```powershell
   poetry add "e as bibliotecas que quer insalar"
   ```
   - Este comando é usado para adicionar bibliotecas ou dependências ao projeto. Substitua `"e as bibliotecas que quer instalar"` pelos nomes das bibliotecas que você deseja adicionar.

Esses comandos ajudam a gerenciar diferentes versões do Python e os ambientes de desenvolvimento associados, garantindo que cada projeto tenha suas próprias dependências isoladas.
