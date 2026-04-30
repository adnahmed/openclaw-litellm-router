# OpenClaw + LiteLLM Router

Start:

cd openclaw-litellm-router
copy .env.example .env
notepad .env
docker compose up -d

Test:

curl.exe http://localhost:4000/v1/chat/completions -H "Authorization: Bearer sk-change-me-local-router-key" -H "Content-Type: application/json" -d "{\"model\":\"openclaw-main\",\"messages\":[{\"role\":\"user\",\"content\":\"Say OK\"}]}"

OpenClaw should call:

litellm/openclaw-main

LiteLLM receives:

openclaw-main

To add providers, add another model_list block in litellm_config.yaml with:

model_name: openclaw-main

Then change model, api_key, api_base, rpm, tpm, weight, and model_info.id.
