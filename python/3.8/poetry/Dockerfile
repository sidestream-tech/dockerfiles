FROM acidrain/python-poetry:3.8 as python-base

ENV \
    # PYTHON
    PYTHONFAULTHANDLER=1 \
    # do not buffer python output at all
    PYTHONUNBUFFERED=1 \
    # do not write `__pycache__` bytecode
    PYTHONDONTWRITEBYTECODE=1 \
    # PIP
    # no pip caching
    PIP_NO_CACHE_DIR=off \
    # no pip version check on installing stuff
    PIP_DISABLE_PIP_VERSION_CHECK=on \
    PIP_DEFAULT_TIMEOUT=100 \
    # POETRY
    # make poetry create the virtual environment in the project's root as `.venv`
    POETRY_VIRTUALENVS_IN_PROJECT=true \
    # do not ask any interactive question
    POETRY_NO_INTERACTION=1

CMD ["poetry"]
