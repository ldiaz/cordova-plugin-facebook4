# cordova-plugin-facebook4
Blank capacitor app to showcase plugin error

This is a ionic capacitor blank template project, with just the commands that creates and setups the project

executed commands to create the app:

    ionic start issue-ionic --capacitor
    npx cap init issue-ionic com.leonardo.FBDemoApp
    ionic build
    npx cap add ios
    npx cap open ios
    # until this point ios app works fine in emulator
    # now add the cordova-plugin-facebook4
    ionic cordova plugin add cordova-plugin-facebook4 --save --variable APP_ID="123456789" --variable APP_NAME="FBDemoApp"
    # in capacitor apps, those cordova params doesn't do much, as explained here: 
    # https://www.joshmorony.com/using-cordova-plugins-that-require-install-variables-with-capacitor/

    npx cap sync

 Now the app continuosly crash on start up with next error output:
    
    2019-07-09 18:33:59.970892-0500 App[31254:3253580] DiskCookieStorage changing policy from 2 to 0, cookie file: file:///Users/leonardo/Library/Developer/CoreSimulator/Devices/CC090A63-1C2E-4D78-8EBB-A34F3D38D2F4/data/Containers/Data/Application/F172EB16-BEF7-4191-999B-7C31EF687976/Library/Cookies/com.leonardo.FBDemoApp.binarycookies
    Loading network plugin   
    2019-07-09 18:34:00.131724-0500 App[31254:3253580] CAPKeyboard: resize mode - native
    2019-07-09 18:34:00.154023-0500 App[31254:3253580] Starting Facebook Connect plugin
    ⚡️  Loading app at capacitor://localhost...   
    2019-07-09 18:34:00.207189-0500 App[31254:3253580] +[FBSDKBasicUtility objectForJSONString:error:]: unrecognized selector sent to class 0x10d35aae0
    2019-07-09 18:34:00.217701-0500 App[31254:3253580] *** Terminating app due to uncaught exception 'NSInvalidArgumentException', reason: '+[FBSDKBasicUtility objectForJSONString:error:]: unrecognized selector sent to class 0x10d35aae0'
    *** First throw call stack:
    
    (
    	0   CoreFoundation                      0x0000000110cd96fb __exceptionPreprocess + 331
    	1   libobjc.A.dylib                     0x000000010e438ac5 objc_exception_throw + 48
    	2   CoreFoundation                      0x0000000110cf79b4 +[NSObject(NSObject) doesNotRecognizeSelector:] + 132
    	3   CoreFoundation                      0x0000000110cde443 ___forwarding___ + 1443
    	4   CoreFoundation                      0x0000000110ce0238 _CF_forwarding_prep_0 + 120
    	5   CordovaPlugins                      0x000000010d2d6037 +[FBSDKAppEventsUtility retrievePersistedAnonymousID] + 231
    	6   CordovaPlugins                      0x000000010d2d5469 +[FBSDKAppEventsUtility anonymousID] + 47
    	7   CordovaPlugins                      0x000000010d2e65a4 +[FBSDKAppEvents initialize] + 180
    	8   libobjc.A.dylib                     0x000000010e439698 CALLING_SOME_+initialize_METHOD + 19
    	9   libobjc.A.dylib                     0x000000010e439a2a initializeNonMetaClass + 269
    	10  libobjc.A.dylib                     0x000000010e43a54f _ZL24initializeAndMaybeRelockP10objc_classP11objc_objectR8mutex_ttILb0EEb + 144
    	11  libobjc.A.dylib                     0x000000010e4403e2 lookUpImpOrForward + 205
    	12  libobjc.A.dylib                     0x000000010e44e0d4 _objc_msgSend_uncached + 68
    	13  CordovaPlugins                      0x000000010d2b7b03 +[FBSDKApplicationDelegate initializeSDK:] + 230
    	14  CordovaPlugins                      0x000000010d2b79c7 +[FBSDKApplicationDelegate initializeWithLaunchData:] + 61
    	15  CoreFoundation                      0x0000000110c1b5ec
      ....


Platform Info: 
	
~~~~
Ionic:

   Ionic CLI                     : 5.2.0 (/usr/local/lib/node_modules/ionic)
   Ionic Framework               : @ionic/angular 4.6.1
   @angular-devkit/build-angular : 0.13.9
   @angular-devkit/schematics    : 7.3.9
   @angular/cli                  : 7.3.9
   @ionic/angular-toolkit        : 1.5.1

Capacitor:

   Capacitor CLI   : 1.1.0
   @capacitor/core : 1.1.0

Cordova:

   Cordova CLI       : 9.0.0 (cordova-lib@9.0.1)
   Cordova Platforms : none
   Cordova Plugins   : no whitelisted plugins (0 plugins total)

Utility:

   cordova-res : 0.5.1 (update available: 0.5.2)
   native-run  : 0.2.7 

System:

   Android SDK Tools : 26.1.1 (/Users/leonardo/Library/Android/sdk)
   NodeJS            : v10.16.0 (/usr/local/Cellar/node@10/10.16.0/bin/node)
   npm               : 6.9.0
   OS                : macOS Mojave
   Xcode             : Xcode 10.2.1 Build version 10E1001
   
~~~~
