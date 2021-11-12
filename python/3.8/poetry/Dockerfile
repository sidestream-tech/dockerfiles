FROM python:3.8.0

ENV \
    # make poetry install to this location
    POETRY_HOME="/opt/poetry" \
    # make poetry create the virtual environment in the project's root as `.venv`
    POETRY_VIRTUALENVS_IN_PROJECT=true \
    # do not ask any interactive question
    POETRY_NO_INTERACTION=1 \
    # do not buffer python output at all
    PYTHONUNBUFFERED=1 \
    # do not write `__pycache__` bytecode
    PYTHONDONTWRITEBYTECODE=1

# install poetry
# before that make sure that we fail on pipe failurese (see https://github.com/hadolint/hadolint/wiki/DL4006)
SHELL ["/bin/bash", "-o", "pipefail", "-c"]
RUN curl -sSL https://raw.githubusercontent.com/sdispater/poetry/master/get-poetry.py | python

# add poetry to path
ENV PATH="$POETRY_HOME/bin:$VENV_PATH/bin:$PATH"

CMD ["poetry"]
