# Chatbot service

## Contents

- [Chatbot service](#chatbot-service)
	- [Contents](#contents)
	- [Setup](#setup)
		- [With Docker:](#with-docker)
		- [Without Docker:](#without-docker)
	- [Usage](#usage)
		- [REST Channels](#rest-channels)
		- [WebSockets](#websockets)
	- [Backlog](#backlog)

&rarr; TODO: write chatbot service description

## Setup

### With Docker:

The easiest way to run this microservice individually is to use Docker (for a global setup of the whole project refer to [the root readme](../README.md))

All you have to do is to run the following command (at the [chatbot microservice root folder](../chatbot/)) if your using `powershell`:

```powershell
docker run --rm -it -v "${pwd}:/app" -p 5005:5005 --entrypoint bash rasa/rasa
```

or this one if you're using `bash`:

```bash
docker run --rm -it -v "$(pwd):/app" -p 5005:5005 --entrypoint bash rasa/rasa
```

And then cd into the app folder:

```bash
cd /app
```

And start the chatbot server

```bash
rasa run -m models --enable-api --cors "*" --debug
```

### Without Docker:

If you choose, for whatever reason, not to use Docker, then you will have to go throught the process of installing Rasa locally. You can then run the following command to start the chatbot:

```bash
rasa run -m models --enable-api --cors "*" --debug
```

## Usage

This will enable you to use the bot in 2 ways:

### REST Channels

Either using the [REST channel](https://rasa.com/docs/rasa/connectors/your-own-website/#rest-channels), by sending HTTP POST requests:

```bash
curl --location --request POST 'http://localhost:5005/webhooks/rest/webhook' \
--header 'Content-Type: application/json' \
--data-raw '{
  "sender": "test_user",
  "message": "Hi there!"
}'
```

### WebSockets

Or using a Socket.io client, that connects to the [Rasa WebSocket channel](https://rasa.com/docs/rasa/connectors/your-own-website/#websocket-channel) and sending your JSON message to it, at the event you specified in `credentials.yml`, that is `message` in this project:

```json
{
  "sender": "test_user",
  "message": "Hi there!",
  "session_id": "some id"
}
```

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;You will then receive the response (also JSON) in the event `reply`:

```json
{
  "text": "Hey! How are you?"
}
```

## Backlog

- [x] Generate project with Rasa CLI
- [ ] Add intents
- [ ] Add stories
- [x] Add socket endpoint
- [ ] Add Redis Tracker store
- [ ] Add Redis Lock store
- [ ] Add story tests
- [ ] Implement actions
- [ ] Add message broker
