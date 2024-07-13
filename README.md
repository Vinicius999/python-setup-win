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
