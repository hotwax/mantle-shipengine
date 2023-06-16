# mantle-shipengine
ShipEngine
Integration with ShipEngine for shipping rates, create labels, and void label. In this Integration we worked on staging environment. So, the rates may vary from production evironment.

To use simply:

Load the setup data in data/ShipEngineSetupData.xml
Load the demo configuration data in data/ShipEngineDemoData.xml or create your own configuration and load it; if you use the demo data, add your API token (SgoApiToken).

~ get#ShippingRates service: API path: https://api.shipengine.com/v1/rates This API call is to get shipping rates for your multiple carrier and service options. Display these at checkout to let your customers choose the fastest, cheapest, or most-trusted route when you ship your products. At minimum, a Rate request requires a delivery location and information on the parcels being delivered. However, different couriers and delivery methods can require additional fields to satisfy their requirements. ShipEngine requires all requests to be in JSON format, so this header should always be set to application/json.

~ post#CreateLabel service : API path: https://api.shipengine.com/v1/labels Set the content type header to application/json and the API Key of your ShipEngine. This call uses the request Body to be in json format. After successfull service call you will receive an HTTP response that included the label details. 

~ put#VoidLabel service: API path: https://api.shipengine.com/v1/labels/{label-id}/void You will need a 'label_id' from another Label Request to void a label. If the Label has left the originating facility and is in route to the destination the void label request will be denied. If the Label is too old to be voided this request will be denied. If the Label has been scanned in, at the originating facility then it will also b denied.