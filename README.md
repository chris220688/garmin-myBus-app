# MyBus Garmin watch app
This is a Garmin watch application that helps you keep track of the bus arrivals on your nearest bus stops.

It currently works only for London as it makes use of the TFL's unified API that can be found [here](https://api.tfl.gov.uk/)

The application is using the internal GPS of the watch to pick up your current location. It then makes two requests to TFL's endpoints:
* The first request returns the bus stops within a radius (selected by the user) of your location.
* The second request returns the buses and their prediction times for the stop that you select.

### Installation

If you already own a Garmin Fenix series watch, go ahead and download the application through Garmin IQ Connect [here](https://apps.garmin.com/en-US/)

### Supported devices

The app has been tested on a Garmin fenix3 watch.

It should be functional on any fenix 3, fenix 5 and Chronos series and might as well run on more Garmin watches, depending on screen dimensions.

### Issues

1. The application currently supports bus stops only within London since it is only using TFL's API. However, it is very easy to extend it by plugging in a class that extends APIRequest. See RequestAPIs/Samples for more information.

2. The accuracy depends on the information returned by the TFL's endpoints. After multiple tests, I found that using a small radius (<20m) won't return results even though there might be bus stops within that range. That being said, I have made the radius configurable by the users so that they can increase it and broaden the search.

3. Garmin watches can't deal with large responses.Since every call is made directly to the TFL's endpoints, I have no way to filter and shrink the responses. This can lead to dropping the responses completely if there are too many bus stops around your location. Try to minimize the search radius, but not too much as you might find yourself in the situation described in NO2 above.

### Acknowledgements

This application is Powered by TfL Open Data and contains OS data © Crown copyright and database rights 2016

### Authors

Chris Liontos
