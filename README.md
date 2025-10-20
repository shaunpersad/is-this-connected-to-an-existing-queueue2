# Cloudflare Deploy Button With Queues Demo

Official template: Queue consumer & producer Worker
See: https://github.com/cloudflare/workers-sdk/tree/main/packages/create-cloudflare/templates/queues/ts


Deploy log:
```
2025-08-27T19:52:36.589Z	 ⛅️ wrangler 4.33.0
2025-08-27T19:52:36.589Z	───────────────────
2025-08-27T19:52:36.598Z
2025-08-27T19:52:36.680Z	✘ [ERROR] Processing wrangler.jsonc configuration:
2025-08-27T19:52:36.680Z
2025-08-27T19:52:36.680Z	    - "queues.consumers[0]" should have a string "queue" field but got {}.
2025-08-27T19:52:36.681Z	    - "queues.producers[0]" bindings should have a string "queue" field but got {"binding":"MY_QUEUE"}.
```

See: deploy.log file

Wrangler configuration after deploy in the new private repo:
```jsonc
/**
 * For more details on how to configure Wrangler, refer to:
 * https://developers.cloudflare.com/workers/wrangler/configuration/
 */
{
	"$schema": "node_modules/wrangler/config-schema.json",
	"name": "cloudflare-deploy-button-with-queues-demo-1",
	"main": "src/index.ts",
	"compatibility_date": "2025-08-26",
	"observability": {
		"enabled": true
	},
	"queues": {
		"consumers": [
			{
			}
		],
		"producers": [
			{
				"binding": "MY_QUEUE"
			}
		]
	}
}

```


[![Deploy to Cloudflare](https://deploy.workers.cloudflare.com/button)](https://deploy.workers.cloudflare.com/?url=https://github.com/shchahrykovich/cloudflare-deploy-button-with-queues-demo)
