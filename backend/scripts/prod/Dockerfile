# this image is tagged and pushed to the production registry (such as ECR)
FROM python:3.8 as production
ENV PYTHONUNBUFFERED 1
ENV PYTHONDONTWRITEBYTECODE 1
RUN mkdir /code
WORKDIR /code
COPY requirements/base.txt /code/requirements/
RUN python3 -m pip install --upgrade pip
RUN pip install -r requirements/base.txt
COPY scripts/prod/start_prod.sh \
    scripts/dev/start_ci.sh \
    scripts/dev/start_asgi.sh \
    /
ADD . /code/
