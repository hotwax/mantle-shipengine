# mantle-shipengine

Integration with ShipEngine for shipping rates, create labels, and void label. In this Integration we worked on staging environment. So, the rates may vary from production evironment.

To use simply:

Load the setup data in data/ShipEngineSetupData.xml
Load the demo configuration data in data/ShipEngineDemoData.xml or create your own configuration and load it; if you use the demo data, add your API token (SgoApiToken).

~ get#ShippingRates service: 
This API returns a rate as per the destination location and parcel attributes.

~ create#CreateLabel service :
This label API will return a URL to a label for an order.

~ put#VoidLabel service: 
You will need a 'label_id' from another Label Request to void a label. If the Label is too old to be voided this request will be denied. If the Label has been scanned in, at the originating facility then it will also be denied.