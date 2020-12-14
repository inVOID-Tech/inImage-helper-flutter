## Getting Started

Add this to your package's `pubspec.yaml` file:

```yaml
dependencies:
  image_helper:
```

## Android

### Minimum Requirements

- `AndroidX`
-  `minSdkVersion 21 `

## iOS

Add one row to the `ios/Runner/Info.plist`:

* one with the key `Privacy - Camera Usage Description` and a usage description.

Or in text format add the key:

```xml
<key>NSCameraUsageDescription</key>
<string>Can I use the camera please?</string>
```


## Authorization 
To Obtain your organisation's ```authkey```, contact us at hello@invoid.co


## Usage

Then you just have to import the package with

```dart
import 'package:image_helper/image_helper.dart';
```
instantiate

```ImageHelperData _imageHelperData;```

Call the SDK, Note
* ```authkey``` is of type ```String```
* ```imageType``` is of type ```String```
* ```accessToGallery``` is of type ```bool```

``` async {  _imageHelperData = await ImageHelper.launch( context, authkey , imageType , accessToGallery); } ```

#### ```imageType``` Parameters are 
* ImageHelper.SELFIE_ONLY
* ImageHelper.SELFIE_WITH_AADHAAR
* ImageHelper.SELFIE_WITH_DL
* ImageHelper.SELFIE_WITH_VOTER
* ImageHelper.SELFIE_WITH_PAN
* ImageHelper.SELFIE_WITH_PASSPORT
* ImageHelper.AADHAAR
* ImageHelper.DL
* ImageHelper.VOTER
* ImageHelper.PAN
* ImageHelper.PASSPORT

## Response returned from the SDK

Before extracting the result check if process completed successfully or not.
```
    if (_imageHelperData.status == ImageHelperData.SUCCESS) {
      // Process completed successfully
      //Extract file path of selfie, front and back of document
    
    } else if(_imageHelperData.status == ImageHelperData.CANCEL) {
      //  User pressed back button
    
    } else {
      // Error
      print('Error msg: ${_imageHelperData.message}');
    }
```

- Status  ``` _imageHelperData.status```
- Message ```_imageHelperData.message```

- For Selfie Path ``` _imageHelperData.selfiePath```
- For Aadhaar Front Path ``` _imageHelperData.aadhaarFrontPath```
- For Aadhaar Front Full Path ``` _imageHelperData.aadhaarFrontFullPath```
- For Aadhaar Back Path ``` _imageHelperData.aadhaarBackPath```
- For Aadhaar Back Full Path ``` _imageHelperData.aadhaarBackFullPath```
- For Back DL ``` _imageHelperData.backDl```
- For Back Full DL ``` _imageHelperData.backfullDl```
- For Front DL ``` _imageHelperData.frontDl```
- For Front Full DL ``` _imageHelperData.frontfullDl```
- For Front Full Voter ``` _imageHelperData.frontFullVoter```
- For Front Voter ``` _imageHelperData.frontVoter```
- For Back Full Voter ``` _imageHelperData.backFullVoter```
- For Back Voter ``` _imageHelperData.backVoter```
- For Front Full Pan ``` _imageHelperData.frontFullPan```
- For Front Pan ``` _imageHelperData.frontPan```
- For Back Full Pan ``` _imageHelperData.backFullPan```
- For Back Pan ``` _imageHelperData.backPan```
- For Front Full Passport ``` _imageHelperData.frontFullPassport```
- For Front Passport ``` _imageHelperData.frontPassport```
- For Back Full Passport ``` _imageHelperData.backFullPassport```
- For Back Passport ``` _imageHelperData.backPassport```

