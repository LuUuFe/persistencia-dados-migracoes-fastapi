# API de Tarefas

**Integrante:** Luis Felipe Andrade Dias

CRUD de tarefas com FastAPI, SQLAlchemy, SQLite e migrações Alembic.

## Como executar

Requer Python 3.12+. Após clonar o repositório, entre na pasta e execute no PowerShell:

```powershell
python -m venv .venv
.\.venv\Scripts\python.exe -m pip install -r requirements.txt
.\.venv\Scripts\python.exe -m alembic upgrade head
.\.venv\Scripts\python.exe -m uvicorn app.main:app --reload
```

No Linux/macOS, use `python3` para criar o ambiente e substitua
`.\.venv\Scripts\python.exe` por `.venv/bin/python` nos demais comandos.

Acesse [http://127.0.0.1:8000/docs](http://127.0.0.1:8000/docs) para testar as rotas.

## Uso

As rotas `/tarefas` e `/tarefas/{id}` permitem criar, listar, consultar,
atualizar (PUT) e excluir tarefas. Exemplo de corpo para criação ou atualização:

```json
{"titulo": "Estudar migrações", "descricao": "Revisar Alembic", "concluida": false}
```

O Alembic cria o banco `tarefas.db`, ignorado pelo Git. Os dados permanecem
após reiniciar a API. As migrações estão em `alembic/versions/`.
