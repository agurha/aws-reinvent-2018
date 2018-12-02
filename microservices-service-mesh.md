# Fully Realizing the Microservices Vision with Service Mesh

- everything gets a load balancer
- use cases:
    1. error handling
    2. load balancing
    3. request routing
    4. security (auth / encryption)
- istio = service mesh with employ proxy
- proxy as a microservice
- automatic policy config (and push)
- DEPLOY PATTERN: canary: update one node then push full
- DEPLOY PATTERN: blue/green: whole alternate instance
- monitoring:
    1. traces
    2. metrics
    3. logs
- can allow for auto-instrumentation... good for spotty adoption across technology platforms
- RED metrics:
    1. R - Rates (calls/sec)
    2. E - Errors
    3. D - Duration (latency)
- speaker from SignalFX 
    -- uses "NoSample" architecture .. meaning they watch everything and determine if the event was interesting afterwards
- 