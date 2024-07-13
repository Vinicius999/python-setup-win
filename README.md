<h1 align="center"> Setup Python for Windows </h1>

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


### 2.2 - Pip + Venv

Principais comandos do **pip**:
- `pip list`: lista todas as bibliotecas instaladas
- `pip freeze`: lista e retorna todas as bibliotecas instaladas e suas respectivas versões
- `pip uninstall <lib-name>`: Desinstala a biblioteca selecionada. Para desinstalar várias bibliotas de uma única vez, deve ser passado a lista dos nomes das bibliotecas separados por um espaço vazio. Ex: `pip uninstall pandas numpy steamlist`
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

Principais comandos PipX:
- `pip install pipx`: Instala o PipX.
- `pipx install <lib-name>`: Instala biblioteca de forma global por usuário.
