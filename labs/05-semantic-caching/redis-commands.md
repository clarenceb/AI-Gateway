# Redis CLI

## Connect to Azure Redis Enterprise Cache

```sh
export redis_key=<your_primary_key>

redis-cli -p 10000 -h rediscachecbx-6bysueg2m22xg.australiaeast.redisenterprise.cache.azure.net -a $redis_key --tls
```

## Redis Commands

```sh
KEYS *
# 1) "ApimSemanticCache:V1:Dim1536:australiaepreprobv2e728202a6tczocgzuuzapzbkhij00mg.2120192:openai-caching;rev=1.2123227:ChatCompletions_Create:4::670d1a6a-bd8a-45bb-8406-18f68bad0875"

TYPE "ApimSemanticCache:V1:Dim1536:australiaepreprobv2e728202a6tczocgzuuzapzbkhij00mg.2120192:openai-caching;rev=1.2123227:ChatCompletions_Create:4::670d1a6a-bd8a-45bb-8406-18f68bad0875"
# hash

TTL "ApimSemanticCache:V1:Dim1536:australiaepreprobv2e728202a6tczocgzuuzapzbkhij00mg.2120192:openai-caching;rev=1.2123227:ChatCompletions_Create:4::670d1a6a-bd8a-45bb-8406-18f68bad0875"
# 50
TTL "ApimSemanticCache:V1:Dim1536:australiaepreprobv2e728202a6tczocgzuuzapzbkhij00mg.2120192:openai-caching;rev=1.2123227:ChatCompletions_Create:4::670d1a6a-bd8a-45bb-8406-18f68bad0875"
# 49

HGETALL "ApimSemanticCache:V1:Dim1536:australiaepreprobv2e728202a6tczocgzuuzapzbkhij00mg.2120192:openai-caching;rev=1.2123227:ChatCompletions_Create:4::670d1a6a-bd8a-45bb-8406-18f68bad0875"
# 1) "Vector"
# 2) "\xa7(\xd6\xbc\xae\.............."
# 3) "CacheEntry"
# 4) "\x8f\x02\x00\x00\x1a.............\n"
# 5) "Vary"
# 6) "None"

HGET "ApimSemanticCache:V1:Dim1536:australiaepreprobv2e728202a6tczocgzuuzapzbkhij00mg.2120192:openai-caching;rev=1.2123227:ChatCompletions_Create:4::9ee113c8-d3a0-4e3b-b09a-cde585da9fe0" Vector
# "\x0f'\xd2\xbc{\xa3*\xbcz\x15\xed9\xc8\\\

exit
```

