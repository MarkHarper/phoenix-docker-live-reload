# Use an official Elixir runtime as a parent image
FROM elixir:1.9.0-alpine

RUN apk update
RUN apk upgrade --no-cache
RUN apk add nodejs=10.14.2-r0 nodejs-npm=10.14.2-r0
RUN apk add inotify-tools=3.20.1-r1
RUN apk add postgresql-client=11.4-r0
RUN mix local.rebar --force
RUN mix local.hex --force

# Create app directory and copy the Elixir projects into it
RUN mkdir /app

WORKDIR /app

CMD ["sh", "./entrypoint.sh"]
