# mantle-shipengine

Integration with ShipEngine for shipping rates, create labels, and void label. In this Integration we worked on staging environment. So, the rates may vary from production evironment.

To use simply:

Load the setup data in data/ShipEngineSetupData.xml
Load the demo configuration data in data/ShipEngineDemoData.xml or create your own configuration and load it; if you use the demo data, add your API token (SgoApiToken).

~ get#ShippingRates service: 
This API returns rate as per the destination location and parcel attributes for shipment id.

~ create#SippingLabel service :
This label API will return a URL to a label for a shipment id and stores it in ShipmentPackageRouteSengment.

~ void#ShippingLabel service: 
You will need a 'label_id' from another label request to void a label. If the label is too old to be voided this request will be denied. If the label has been scanned in, at the originating facility then it will also be denied.
