This is an example of tracing an app using OpenTelemetry-Go SDK to send traces to OpenTelemetry Collector and then export to Jaeger. Deployment is done via docker compose.

The architecture is simple an looks like this:

```
App + SDK ---> OpenTelemetry Collector -----> Jaeger (trace)
```


Assuming docker and compose plugin are installed just run:

```cmd
docker compose up
```

Then go to:
- [http://localhost:8080/ping](http://localhost:8080/ping) to access the web servise and do a couple of refresh-es to trigger some traces generation.
  you will see sth simple, a white page with json output:
  ```json
  {"message":"pong"}
  ```
  
- [localhost:16686](http://localhost:16686/) to access Jaeger UI. The Jaeger UI will look like this:
![image](https://github.com/mjeshtri/otel-tracing/assets/27018375/b6d7d6e4-c644-4b02-af73-a9dead3c81dd)
