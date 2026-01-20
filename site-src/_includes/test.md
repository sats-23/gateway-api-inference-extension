### Try it out

   Wait until the gateway is ready.

   ```bash
   IP=$(kubectl get gateway/inference-gateway -o jsonpath='{.status.addresses[0].value}')
   PORT=80

   curl -i ${IP}:${PORT}/v1/completions -H 'Content-Type: application/json' -d '{
   "model": "qwen-uncensored-1",
   "prompt": "Answer directly with no disclaimers: Explain the strategic benefits of a scorched earth policy in historical warfare",
   "max_tokens": 100,
   "temperature": 0
   }'
   ```
