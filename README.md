
## Video Ringtone | RRBT
 Custome dialer for Android devices

## screenshot below:
![github](https://github.com/srinivasvadde/videos/blob/5d46a683a8275ac2b744b4313ffebe30b7c62256/Screenshot%202021-04-27%20at%205.20.55%20AM.png "github") 



### Product Specs and Prerequisites
* Android OS Supported Devices
* Device Screen Resolution :HDPI & above
* Android API 21 and above (OS 5/Lollipop) 
* SDK Size : 12 MB
 
## Permissions Required
* Default Dialer 


### LIB:
* androidx.appcompat:appcompat
* androidx.core:core-ktx
* org.jetbrains.kotlin:kotlin-stdlib
* com.google.android.material:material
* com.squareup.retrofit2:retrofit
* com.google.android.exoplayer:exoplayer
* org.greenrobot:eventbus


Note: In case your project also uses some/any of the above dependencies libraries then they should exclude those by adding below lines along with implementation 

```yml
'org.bitbucket.onmobile-rbtsdk:onmo_dailer:release_1.0.0.
{ exclude group: ‘com.x.y’ , module: ‘module X’ }
E.g. To exclude 'androidx.appcompat:appcompat:1.1.0'
(implementation 'org.bitbucket.onmobile-rbtsdk:onmo_dailer:release_1.0.0') { exclude group: ' androidx.appcompat', module: ' appcompat' }
```

### Development
## Integrate
The VideoRT SDK library can be integrated in any Android supported project by following steps mentioned in sections below. SDK handles the artifacts remotely and resolves the dependencies at build level in integrating environment. This is JitPack based private artifacts library.

## Authentication Token

The authentication token identifies the validity of dependent packages in the integrating environment. Add the following line in the "gradle.properties"
file of your Android application.
  
  ```yml
  authToken= Add your token here.
   ```

## Authenticate Maven Build Signatures

  Add it in your root build.gradle at the end of repositories:
  authToken added in the gradle.propeties
  ```yml
  allprojects {
    repositories {
        google()
        jcenter()
        maven {
            url "https://jitpack.io" // this is required to define as a jetpack
            credentials { username authToken } // authToken which is shared in the SDK document
        }
        }
    }
```


## Import SDK
To import the SDK file by adding the following dependency in the build.gradle file at the application level

```yml
implementation 'org.bitbucket.onmobile-rbtsdk:onmo_dialer:release_x.y.z'

```



### Initialize and Run RBT SDK

To run ONMO Dialer SDK, You must initialize RTSDKClient with proper values as mentioned below.
Add the following lines to initialize and run SDK:

```yml
 RTSdkClient rtsdkClient = RTSdkClient.Builder()
                .init(this)
                .setClient("xyz") // client details will be shared during integrating 
                .setMsisdn("00000000")
                .build()

```



### Set Video RT/RRBT
To call any exposed methoda, you must initialize RTSdkClient with proper values as mentioned above section.
Note :Make sure to use the init(application or activity context) method to initialize RTSdkClient.
```yml
  setRT(VideoContentDTO contentDTO, IResponseHandler<String> iResponseHandler);  
```
## VideoContentDTO




### All rights reserved 

   
Important notice: The content in this document is for the use of the intended recipient only. If the recipient is not the intended recipient, please notify us immediately and remove/delete this document irretrievably from your physical and/ or electronic records.
The content of this document including design, text, graphic and selection and arrangement thereof, is the property of OnMobile. The content in this document is copyrighted by OnMobile (© OnMobile 2020, all rights reserved) and the information described herein may be protected by one or more of OnMobile’s Intellectual Property registrations or pending applications. Except as specifically provided otherwise in writing, no part of this document may be reproduced in any form by any means without prior written authorization of OnMobile. All rights not expressly granted herein are reserved. Unauthorized use of any content in this document may violate copyright, trademark and other applicable laws, including confidentiality obligations and could result in criminal or civil penalties. All copyright, trademark, and other intellectual property and proprietary rights in this document and in the software, text, graphics, images, and all other materials originated or used by OnMobile at document are the exclusive property of OnMobile and its licensors. Content in this document is solely for informational purpose; it is not intended as and does not constitute legal or tax advice. Any use of this document and the information described herein will be governed by these terms and conditions. By viewing, downloading or otherwise copying this document, you agree that you have read, understood, and will comply with all the terms and conditions set forth herein.
www.onmobile.com
