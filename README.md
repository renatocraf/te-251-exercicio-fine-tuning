# Fine Tuning do Modelo GPT-4.1 

Este projeto implementa um sistema de classificação automática de requirements de software em duas categorias: **funcionais** e **não-funcionais**, utilizando modelos de linguagem da OpenAI com técnicas de fine-tuning.

## Objetivos

- **Automatizar** a classificação de requirements de software
- **Comparar** o desempenho entre modelo base e modelo fine-tuned
- **Avaliar** a eficácia do fine-tuning para tarefas específicas de engenharia de software

## Pré-requisitos

- Python 3.11 ou superior instalado no sistema
- pip (geralmente vem incluído com Python)

Para verificar se o Python está instalado:
```bash
python --version
```
ou
```bash
python3 --version
```

## Configuração do Ambiente

### 1. Criando o Ambiente Virtual (venv)

No diretório raiz do projeto, execute:

```bash
python -m venv venv
```

ou se você usa `python3`:

```bash
python3 -m venv venv
```

Isso criará uma pasta chamada `venv` contendo o ambiente virtual isolado.

### 2. Ativando o Ambiente Virtual

#### No Windows:

**Command Prompt (cmd):**
```cmd
venv\Scripts\activate
```

**PowerShell:**
```powershell
venv\Scripts\Activate.ps1
```

**Git Bash:**
```bash
source venv/Scripts/activate
```

#### No Linux/macOS:

```bash
source venv/bin/activate
```

Quando o ambiente estiver ativo, você verá `(venv)` no início da linha de comando.

### 3. Instalando as Dependências

#### Requisitos

```python
pandas
openai
python-dotenv
ipykernel
openpyxl
json (nativo)
os (nativo)
```

Com o ambiente virtual ativado, instale as dependências do projeto:

```bash
pip install -r requirements.txt
```

### 4. Desativando o Ambiente Virtual

Quando terminar de trabalhar no projeto, desative o ambiente virtual:

```bash
deactivate
```

## Configuração das Variáveis de Ambiente

### Criando o arquivo .env

Após instalar as dependências, você precisa criar um arquivo `.env` na raiz do projeto para configurar as variáveis de ambiente necessárias.

1. Crie um arquivo chamado `.env` na raiz do projeto:
```bash
touch .env  # Linux/macOS
# ou crie manualmente no Windows
```

2. Adicione a(s) seguinte(s) variável(is) ao arquivo `.env`:
```env
OPENAI_API_KEY=sua_chave_api_aqui
```

**OPENAI_API_KEY:**
- Esta é sua chave de API pessoal da OpenAI
- Necessária para autenticar e fazer requisições para os modelos da OpenAI (GPT-3.5, GPT-4, etc.)
- Você pode obter sua chave em: https://platform.openai.com/api-keys
- **Importante:** Mantenha esta chave em segredo e nunca a compartilhe publicamente

## Metodologia

1. **Preparação dos Dados**: Conversão de datasets Excel para formato JSONL compatível com OpenAI
2. **Fine-tuning**: Treinamento personalizado do modelo GPT-4.1-nano para a tarefa específica
3. **Avaliação Comparativa**: Teste de acurácia entre modelo base vs modelo fine-tuned

## Estrutura do Projeto

```
te-251-exercicio-fine-tuning
├── projeto.ipynb
├── requirements.txt      # Lista de dependências
├── README.md            # Este arquivo
├── data/
    ├── xlsx/           # Datasets originais em Excel│   
    │   └── dataset-test2.xlsx
    └── jsonl/          # Datasets convertidos para fine-tuning
        ├── dataset-test2.jsonl
        ├── dataset-test.jsonl
        ├── dataset-test-final.jsonl
        ├── dataset-train.jsonl
        └── dataset.jsonl
```

## Funcionalidades Principais

- **Conversão de Dados**: Transformação Excel → JSONL
- **Concatenação de Datasets**: Combinação de múltiplos arquivos de treinamento
- **Fine-tuning**: Personalização de modelos OpenAI
- **Avaliação Automatizada**: Comparação de performance entre modelos

## Resultados Esperados

O projeto gera métricas comparativas de acurácia entre:
- **Modelo Base**: GPT-4.1-nano padrão
- **Modelo Fine-tuned**: Versão personalizada para classificação de requirements

## Aplicações

- Automatização em processos de engenharia de requisitos
- Análise de especificações de software
- Suporte a analistas de sistemas na categorização de requirements
- Pesquisa em classificação automática de textos técnicos