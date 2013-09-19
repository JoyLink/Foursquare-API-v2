#Foursquare Objective-C API 2.0

###Features
* Native authentication with Foursquare app.
* In-app authentication.
* Asynchronous requests with blocks
* Build-in image uploader for photos.
* Made with native frameworks.


###How To

0. In case you already use this library and you want to switch on native login: you need to add new redirect URL in app settings on https://developer.foursquare.com and make sure you keep old redirect URL, otherwise current application on AppStore will not be able to open login page. For native login you must have redirect URL like this testapp123://foursquare. testapp123 is URL scheme of your application. It must be in plist(see steps below) and must be unique.

1. Create Your application here https://foursquare.com/developers/register
![](https://raw.github.com/Constantine-Fry/Foursquare-API-v2/master/img/site1.png)

2. Setup Foursquare to use your credentials


        - (BOOL)application:(UIApplication *)application didFinishLaunchingWithOptions:(NSDictionary *)launchOptions {
    
            [Foursquare2 setupFoursquareWithClientId:YOUR_KEY
                                     		 secret:YOUR_SECRET
	                                 callbackURL:YOUR_CALLBACK_URL];
        }
    
    
3. You need to make sure you set up the URL scheme in your info.plist properly

CFBundleURLTypes -> CFBundleURLName -> CFBundleURLSchemes -> {app_id}

![](https://github.com/Constantine-Fry/Foursquare-API-v2/blob/master/img/plist.png?raw=true)


###Useful tips
1. How to get sw and ne from MKMapView?

        CGPoint swPoint = CGPointMake(mapView.bounds.origin.x, mapView.bounds.origin.y+ mapView.bounds.size.height);
        CGPoint nePoint = CGPointMake((mapView.bounds.origin.x + mapView.bounds.size.width), (mapView.bounds.origin.y));
    
        //Then transform those point into lat,lng values
        CLLocationCoordinate2D swCoord;
        swCoord = [mapView convertPoint:swPoint toCoordinateFromView:mapView];
    
        CLLocationCoordinate2D neCoord;
        neCoord = [mapView convertPoint:nePoint toCoordinateFromView:mapView];









###Screnshots
![](https://raw.github.com/Constantine-Fry/Foursquare-API-v2/master/img/photo1.PNG)


![](https://raw.github.com/Constantine-Fry/Foursquare-API-v2/master/img/photo2.PNG)


I got blue pin [here](http://graphicclouds.com/map-pin-icons/).

