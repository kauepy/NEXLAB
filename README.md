# NEXLAB

Plataforma modular de instrumentação, aquisição e análise de dados científicos.

O NEXLAB recebe medições de sensores (reais ou simulados), organiza tudo em experimentos, guarda os dados em um banco local, calcula estatísticas básicas e exporta os resultados para CSV. Tudo isso através de uma interface gráfica feita com PySide6.

> **Status:** em desenvolvimento inicial (versão 0.1.0). Veja a seção [Status do desenvolvimento](#status-do-desenvolvimento).

## Funcionalidades previstas

- **Experimentos:** criar, iniciar, acompanhar e finalizar experimentos, com as medições sempre ligadas ao experimento correto.
- **Aquisição de dados:**
  - Simulador de sensores para testes, com valores, unidades e intervalos configuráveis. Os dados simulados são sempre identificados como simulados.
  - Comunicação serial com dispositivos físicos (conexão, leitura, timeout e tratamento de erros).
- **Validação:** só entram no sistema medições com valor numérico válido, unidade, identificador e formato corretos. Mensagens inválidas são tratadas sem derrubar a aplicação.
- **Armazenamento:** banco SQLite local com experimentos, dispositivos, medições e eventos.
- **Análise:** média, mediana, desvio-padrão, mínimo e máximo.
- **Exportação:** CSV com timestamps, unidades, identificadores e origem (real ou simulada) de cada medição.
- **Interface gráfica:** dashboard, tela de experimentos, tela de sensores e tela de relatórios.

## Requisitos

- Python 3.11 ou superior
- Dependências (instaladas automaticamente): `PySide6` e `pyserial`

## Instalação

```bash
# 1. Clone o repositório
git clone https://github.com/kauepy/NEXLAB.git
cd NEXLAB

# 2. Crie e ative um ambiente virtual
python -m venv .venv

# Linux/macOS
source .venv/bin/activate
# Windows (PowerShell)
.venv\Scripts\Activate.ps1

# 3. Instale o projeto em modo editável, com as ferramentas de desenvolvimento
pip install -e ".[dev]"
```

## Como executar

Depois da instalação, a aplicação é iniciada com:

```bash
nexlab
```

ou, equivalente:

```bash
python -m nexlab.main
```

> O ponto de entrada (`src/nexlab/main.py`) ainda será criado. Até lá, estes comandos não funcionam.

## Testes e qualidade de código

```bash
# Rodar todos os testes
pytest

# Testes com relatório de cobertura
pytest --cov=nexlab

# Verificar o estilo do código
ruff check .
```

## Estrutura do projeto

```text
NEXLAB/
├── docs/                  # Documentação (arquitetura e protocolo)
├── src/nexlab/
│   ├── core/              # Modelos, validação e lógica de experimentos
│   ├── acquisition/       # Simulador, protocolo e comunicação serial
│   ├── storage/           # Banco SQLite e repositórios
│   ├── analysis/          # Estatísticas
│   ├── export/            # Exportação para CSV
│   ├── ui/                # Interface gráfica (PySide6)
│   └── main.py            # Ponto de entrada
├── tests/                 # Testes automatizados
├── pyproject.toml         # Configuração do projeto
└── README.md
```

Mais detalhes em `docs/ARCHITECTURE.md` e `docs/PROTOCOL.md`.

## Status do desenvolvimento

| Fase | Conteúdo                         | Situação        |
|------|----------------------------------|-----------------|
| 1    | Preparação e documentação        | Em andamento    |
| 2    | Núcleo do sistema                | Pendente        |
| 3    | Aquisição de dados               | Pendente        |
| 4    | Armazenamento                    | Pendente        |
| 5    | Análise e exportação             | Pendente        |
| 6    | Interface gráfica                | Pendente        |
| 7    | Inicialização                    | Pendente        |
| 8    | Testes                           | Pendente        |

## Licença

A definir.
