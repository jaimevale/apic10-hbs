# Proyecto de uso de templates en APIC10

## Contexto
Queremos crear OpenAPI de APIC de una forma más ágil


## Decisión
vamos a crear las API por linea de comando con este comando:

```
apic create:[api | product] --template template_file --title [api_title | product_title] options


apic create:api      --template template_api.hbs       --title api_title 
apic create:product  --template template_producto.hbs  --title product_title



apic create:api  --template openapi-apic-vcsoft.hbs  --filename api2.yaml --title API_title --name API_name --basepath /api/base/path 

```

Donde: 

 1. template_file: Un archivo .hbs
 2. los parametros adicionales estan descritos en este help

```
 Usage: apic create:api [flags]

Create an OpenAPI (Swagger) definition

Flags:
      --api_type string       The type of api (rest, wsdl-to-rest, or wsdl) (default "wsdl")
      --basepath string       basepath value (default derived from name)
      --disable_ws_security   Disable generation of WS-Security definitions in api
      --filename string       filename (default derived from name)
      --gateway-type string   The type of the gateway (datapower-gateway, datapower-api-gateway, event-gateway) (default "datapower-gateway")
  -h, --help                  Help for create:api
      --hostname string       host value (default $(catalog.host)
  -i, --interactive           use interactive mode
      --name string           x-ibm-name value (default derived from title)
      --product string        generate a product definition referencing the API
      --schemes string        list of schemes (valid options are http, https, ws and wss)
      --services string       service names separated by space
      --target-url string     target url
      --template string       use a provider template (if empty defaults to apic template)
      --title string          title value (required)
  -v, --version string        version value (default "1.0.0")
      --wsdl string           wsdl file to use as the source (required authentication via apic login)
```
