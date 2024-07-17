<h1 align="center"> Setup Python for Windows </h1>

<p>
Este repositório foi desenvolvido com objetivo de ser um guia rápido para a criação de um setup Python profissional.
</p>

### Sumário
<ul>
    <li>Python</li>
    <li>VS Code</li>
    <li>Git e Github</li>
    <li>Pyenv</li>
    <li>Pip + Venv</li>
    <li>Pipx</li>
    <li>Poetry</li>
</ul>

### 1.1 - Python
Inicialmente, iremos instalar o Python no seu computador. Para isso, devemos:
- Acessar o site oficial do Python: [`python.org`]([https://www.python.org/])
- Na aba **Downloads**, clicar para baixar a versão mais recente do Python, como aparece na imagem abaxo.

![python-download](https://github.com/Vinicius999/python-setup-win/blob/main/images/python-download.png)


### 2.1 - Pyenv

Principais comandos do **Pyenv**:
- `pyenv local <python-version>`: Configura a versão do Python que será usada no projeto. Este comando deve ser executado dentro da pasta do projeto

### 2.2 - Pip + Venv

Principais comandos do **pip**:
- `pip list`: lista todas as bibliotecas instaladas.
- `pip freeze`: lista e retorna todas as bibliotecas instaladas e suas respectivas versões.
- `pip uninstall <lib-name>`: Desinstala a biblioteca selecionada. Para desinstalar várias bibliotas de uma única vez, deve ser passado a lista dos nomes das bibliotecas separados por um espaço vazio. Ex: `pip uninstall pandas numpy steamlist`.
- `pip freeze | grep -v "^-e" | xargs pip uninstall -y`: Desinstala todas as bibliotecas de uma vez.

Principais comandos **venv**:
- `python -m venv <venv-name>`: Cria o ambiente virtual para armazenar e isolar as bibliotecas a serem instaladas no projeto python. Deve ser executado dentro da pasta do projeto. Por padrão, usa-se "venv" ou ".venv" como nome do ambiente virtual. 
- `source -m <venv-name>/Script/activate`: lista e retorna todas as bibliotecas instaladas e suas respectivas versões

### 2.3 - PipX

Cria ambientes virtuais por usuário do computador. Dessa forma, o usuário **user_1** poderá ter certos pacotes que ele sempre usa sem precisar ficar instalando em todos os projetos. A vantagem é que se tiver mais de um usuário em determinada máquina, cada usuário não irá "sujar" ou interferir nas bibliotecas dos demais usuários.

O **PipX** deve ser a única biblioteca que você deverá instalar instalar no **pip** de forma global. Dessa forma, ao executar o comando `pip list`, a saída deve ser exatamente como mostrado abaixo:

```
Package      Version
------------ -------
argcomplete  3.4.0
click        8.1.7
colorama     0.4.6
packaging    24.1
pip          24.1.2
pipx         1.6.0
platformdirs 4.2.2
userpath     1.9.2
```

Principais comandos **PipX**:
- `pip install pipx`: Instala o PipX.
- `pipx install <lib-name>`: Instala biblioteca de forma global por usuário.

### 2.4 - Poetry

Principais comandos **Poetry**:
- `poetry config --list`: Lista as configurações do Poetry.
- `poetry config virtualenvs.in-project true`: Informar ao poetry que ele deve a pasta `.venv` dos ambientes virtuais dentro dos diretórios dos projetos criados.
- `poetry new <project-name>`: Cria a pasta do projeto estruturada, já contendo README.md, pasta de testes, pasta do projeto principal e arquivo de gerenciamento de bibliotecas.
- `poetry env use <python-version>`: Cria o ambiente virtual e especifica qual a versão Python a ser usada. Deve ser usada a mesma versão especificada no comando `pyenv local <python-version>`
- `poetry install`: Ativa o ambiente virtual e instala as dependências.
- `poetry env info`: Printa informações sobre o ambiente virtual que está sendo usado.
- `poetry shell`: Ativa a visualização do terminal do Poetry para poder manipular e visualizar as bibliotecas no projeto atual.
- `poetry add <lib-name>`: Instala a biblioteca especificada e suas dependências no ambiente virtual.
- `poetry remove <lib-name>`: Desinstala a biblioteca especificada e suas dependências no ambiente virtual.
- `poetry init`: Inicia o gerenciamento com o Poetry dentro de um projeto já existente.
- `poetry install`: Verifica e instala as bibliotecas existentes no arquivo `pyproject.toml`.
- `poetry show`: Mostra todas as dependencias instaladas e suas versões exatas.
- `poetry show <lib-name>`: Mostra todas as informações de uma biblioteca instaladas.


### 2.5 Trabalhando com **Pyenv + Poetry**

1. Informar ao poetry que ele deve a pasta `.venv` dos ambientes virtuais dentro dos diretórios dos projetos criados:

```
poetry config virtualenvs.in-project true
```

2. Criar a pasta do projeto estruturada, já contendo:
- pasta do projeto principal
- pasta de testes
- README.md
- arquivo de gerenciamento de bibliotecas

```
poetry new <project-name>
```

3. Entrando na pasta do projeto criado pelo Poetry `cd <project-name>`, vamos configurar a versão do Python a ser usada no projeto.

```
pyenv local <python-version>
```

4. Criar o ambiente virtual `.venv` e especificar qual a versão Python a ser usada.

```
poetry env use <python-version>
```

5. Instalar todas as dependências, caso haja.

```
poetry install
```

6. Ativar o ambinete virtual.

```
poetry shell
```

7. Instala a biblioteca especificada e suas dependências no ambiente virtual.

```
poetry add <lib-name>
```

9. Desinstala a biblioteca especificada e suas dependências no ambiente virtual.

```
poetry remove <lib-name>
```

10. Sair do ambiente virtual sem desativá-lo.

```
exit
```

11. Desativar o ambiente virtual.

```
deactivate
```