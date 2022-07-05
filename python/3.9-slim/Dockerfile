FROM python:3.9-slim as python-base

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
    POETRY_VERSION=1.1.13 \
    # make poetry install to this location
    POETRY_HOME="/opt/poetry" \
    # make poetry create the virtual environment in the project's root as `.venv`
    POETRY_VIRTUALENVS_IN_PROJECT=true \
    # do not ask any interactive question
    POETRY_NO_INTERACTION=1 \
    # PATHS
    PYSETUP_PATH="/opt/pysetup" \
    VENV_PATH="/opt/pysetup/.venv"

# add poetry to path
ENV PATH="$POETRY_HOME/bin:$VENV_PATH/bin:$PATH"

FROM python-base as building-base
# install poetry
# before that make sure that we fail on pipe failurese (see https://github.com/hadolint/hadolint/wiki/DL4006)
SHELL ["/bin/bash", "-o", "pipefail", "-c"]
RUN apt-get update && \
    apt-get install --no-install-recommends -y \
    curl=7.74.0-1.3+deb11u1 \
    build-essential=12.9

SHELL ["/bin/bash", "-o", "pipefail", "-c"]
RUN curl -sSL https://raw.githubusercontent.com/sdispater/poetry/master/get-poetry.py | python

SHELL ["/bin/bash", "-o", "pipefail", "-c"]
RUN apt-get purge curl build-essential -y

CMD ["poetry"]
