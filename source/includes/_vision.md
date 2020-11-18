# Computer Vision

Computer Vision enables machines to "see" images and recognize objects, entities and texts or extract meta information from a given image.

## Face Detection

Face detection identifies faces on images and analyses various characteristics such as the face expression or facial features like eyes, nose or mouth positions.

Each face detection carries a confidence score for recognizing the face itself as well as the features of the face. 

### HTTP Request

`POST /v1/vision/face`

```shell

curl --location --request POST 'https://api.rapyd.ai/v1/vision/face' \
--header 'PROVIDER: gcp' \
--header 'ACCOUNT-ID: your-accountid' \
--header 'Authorization: Bearer your-token' \
--form 'file=face_demo.png'

```

```javascript

var myHeaders = new Headers();
myHeaders.append("PROVIDER", "gcp");
myHeaders.append("ACCOUNT-ID", "your-accountid");
myHeaders.append("Authorization", "Bearer your-token");

var formdata = new FormData();
formdata.append("file", fileInput.files[0], "face_demo.png");

var requestOptions = {
  method: 'POST',
  headers: myHeaders,
  body: formdata,
  redirect: 'follow'
};

fetch("https://api.rapyd.ai/v1/vision/face", requestOptions)
  .then(response => response.text())
  .then(result => console.log(result))
  .catch(error => console.log('error', error));

```

```jsx

var unirest = require('unirest');
var req = unirest('POST', 'https://api.rapyd.ai/v1/vision/face')
  .headers({
    'PROVIDER': 'gcp',
    'ACCOUNT-ID': 'your-accountid',
    'Authorization': 'Bearer your-token'
  })
  .attach('file', 'face_demo.png')
  .end(function (res) { 
    if (res.error) throw new Error(res.error); 
    console.log(res.raw_body);
  });

```

```python

import requests

url = "https://api.rapyd.ai/v1/vision/face"

payload = {}
files = [('file', open('face_demo.png', 'rb'))]
headers = {
    'PROVIDER': 'gcp',
    'ACCOUNT-ID': 'your-accountid',
    'Authorization': 'Bearer your-token'
}

response = requests.request(
    "POST", url, headers=headers, data=payload, files=files)

print(response.text.encode('utf8'))

```

```r

library(httr)

url <- "https://api.rapyd.ai/v1/vision/face"

headers <- c("ACCOUNT-ID" = "your-accountid", 
             "Authorization" = "Bearer your-token",
             "PROVIDER" = "gcp")

payload <- list(file = upload_file("face_demo.png"))

response <- POST(url, add_headers(headers), body = payload)
result <- content(response, "parsed")

```

> Make sure to replace `your-accountid` and `your-token` with your personal credentials.

> The above command returns results in JSON representation.

> Example response when provider is `gcp`:

```json
{
    "meta": {
        "provider": "GCP",
        "language": ""
    },
    "result": [
        {
            "rollAngle": -0.4798591,
            "panAngle": 0.12718968,
            "tiltAngle": -1.2569677,
            "detectionConfidence": 0.94939417,
            "landmarkingConfidence": 0.80378807,
            "joyRating": 1.0,
            "sorrowRating": 0.2,
            "angerRating": 0.2,
            "surpriseRating": 0.2,
            "underExposedRating": 0.2,
            "blurredRating": 0.2,
            "headwearRating": 0.2,
            "joy": "VERY_LIKELY",
            "sorrow": "VERY_UNLIKELY",
            "anger": "VERY_UNLIKELY",
            "surprise": "VERY_UNLIKELY",
            "underExposed": "VERY_UNLIKELY",
            "blurred": "VERY_UNLIKELY",
            "headwear": "VERY_UNLIKELY",
            "boundingPoly": [
                {
                    "x": 549,
                    "y": 26
                },
                {
                    "x": 1164,
                    "y": 26
                },
                {
                    "x": 1164,
                    "y": 740
                },
                {
                    "x": 549,
                    "y": 740
                }
            ],
            "fdBoundingPoly": [
                {
                    "x": 587,
                    "y": 153
                },
                {
                    "x": 1124,
                    "y": 153
                },
                {
                    "x": 1124,
                    "y": 686
                },
                {
                    "x": 587,
                    "y": 686
                }
            ],
            "landmarks": [
                {
                    "type": "LEFT_EYE",
                    "x": 768.32544,
                    "y": 373.06293,
                    "z": 0.0013751984
                },
                {
                    "type": "RIGHT_EYE",
                    "x": 951.94446,
                    "y": 369.37823,
                    "z": 0.4714136
                },
                {
                    "type": "LEFT_OF_LEFT_EYEBROW",
                    "x": 701.52814,
                    "y": 339.7583,
                    "z": 14.543475
                },
                {
                    "type": "RIGHT_OF_LEFT_EYEBROW",
                    "x": 814.4408,
                    "y": 331.55685,
                    "z": -34.32722
                },
                {
                    "type": "LEFT_OF_RIGHT_EYEBROW",
                    "x": 903.94037,
                    "y": 327.39395,
                    "z": -33.947388
                },
                {
                    "type": "RIGHT_OF_RIGHT_EYEBROW",
                    "x": 1017.8008,
                    "y": 336.4593,
                    "z": 15.296562
                },
                {
                    "type": "MIDPOINT_BETWEEN_EYES",
                    "x": 859.9506,
                    "y": 364.55762,
                    "z": -36.450184
                },
                {
                    "type": "NOSE_TIP",
                    "x": 856.7595,
                    "y": 477.4241,
                    "z": -88.43703
                },
                {
                    "type": "UPPER_LIP",
                    "x": 858.8607,
                    "y": 536.78925,
                    "z": -47.308403
                },
                {
                    "type": "LOWER_LIP",
                    "x": 860.94543,
                    "y": 612.84033,
                    "z": -34.59475
                },
                {
                    "type": "MOUTH_LEFT",
                    "x": 763.8856,
                    "y": 559.6046,
                    "z": 2.3785026
                },
                {
                    "type": "MOUTH_RIGHT",
                    "x": 955.97986,
                    "y": 554.21515,
                    "z": 3.0310767
                },
                {
                    "type": "MOUTH_CENTER",
                    "x": 862.51575,
                    "y": 575.4721,
                    "z": -34.262444
                },
                {
                    "type": "NOSE_BOTTOM_RIGHT",
                    "x": 920.23486,
                    "y": 484.30716,
                    "z": -22.016401
                },
                {
                    "type": "NOSE_BOTTOM_LEFT",
                    "x": 797.2778,
                    "y": 486.82227,
                    "z": -22.553627
                },
                {
                    "type": "NOSE_BOTTOM_CENTER",
                    "x": 858.078,
                    "y": 504.10403,
                    "z": -48.339252
                },
                {
                    "type": "LEFT_EYE_TOP_BOUNDARY",
                    "x": 766.4023,
                    "y": 358.04807,
                    "z": -10.352289
                },
                {
                    "type": "LEFT_EYE_RIGHT_CORNER",
                    "x": 803.16595,
                    "y": 374.9589,
                    "z": -0.06131935
                },
                {
                    "type": "LEFT_EYE_BOTTOM_BOUNDARY",
                    "x": 766.3668,
                    "y": 387.02142,
                    "z": -1.8237071
                },
                {
                    "type": "LEFT_EYE_LEFT_CORNER",
                    "x": 728.4919,
                    "y": 377.98483,
                    "z": 15.790957
                },
                {
                    "type": "RIGHT_EYE_TOP_BOUNDARY",
                    "x": 953.81085,
                    "y": 352.64587,
                    "z": -9.6653805
                },
                {
                    "type": "RIGHT_EYE_RIGHT_CORNER",
                    "x": 991.34924,
                    "y": 374.1126,
                    "z": 16.405922
                },
                {
                    "type": "RIGHT_EYE_BOTTOM_BOUNDARY",
                    "x": 953.1808,
                    "y": 383.13376,
                    "z": -1.3505049
                },
                {
                    "type": "RIGHT_EYE_LEFT_CORNER",
                    "x": 913.28955,
                    "y": 371.66306,
                    "z": 0.2713766
                },
                {
                    "type": "LEFT_EYEBROW_UPPER_MIDPOINT",
                    "x": 759.5528,
                    "y": 317.5705,
                    "z": -20.760433
                },
                {
                    "type": "RIGHT_EYEBROW_UPPER_MIDPOINT",
                    "x": 961.46344,
                    "y": 313.44608,
                    "z": -19.984333
                },
                {
                    "type": "LEFT_EAR_TRAGION",
                    "x": 643.31226,
                    "y": 435.80838,
                    "z": 221.14575
                },
                {
                    "type": "RIGHT_EAR_TRAGION",
                    "x": 1066.6526,
                    "y": 425.88293,
                    "z": 223.30026
                },
                {
                    "type": "FOREHEAD_GLABELLA",
                    "x": 860.34784,
                    "y": 325.64413,
                    "z": -40.136284
                },
                {
                    "type": "CHIN_GNATHION",
                    "x": 861.9055,
                    "y": 709.1296,
                    "z": -9.581303
                },
                {
                    "type": "CHIN_LEFT_GONION",
                    "x": 688.78577,
                    "y": 595.2242,
                    "z": 148.22136
                },
                {
                    "type": "CHIN_RIGHT_GONION",
                    "x": 1029.5104,
                    "y": 582.9388,
                    "z": 149.34828
                },
                {
                    "type": "UNKNOWN_LANDMARK",
                    "x": 726.73364,
                    "y": 497.08798,
                    "z": 17.647654
                },
                {
                    "type": "UNKNOWN_LANDMARK",
                    "x": 994.6479,
                    "y": 492.37317,
                    "z": 18.335396
                }
            ]
        }
    ]
}
```

> Example response when provider is `aws`

```json
{
   "meta":{
      "language":"",
      "provider":"aws"
   },
   "result":{
      "faceDetails":[
         {
            "ageRange":"None",
            "beard":"None",
            "boundingBox":{
               "height":0.26589525,
               "left":0.37521443,
               "top":0.06623106,
               "width":0.2295874
            },
            "confidence":99.99913,
            "emotions":"None",
            "eyeglasses":"None",
            "eyesOpen":"None",
            "gender":"None",
            "landmarks":[
               {
                  "type":"eyeLeft",
                  "x":0.44272083,
                  "y":0.17161196
               },
               {
                  "type":"eyeRight",
                  "x":0.5494187,
                  "y":0.17190441
               },
               {
                  "type":"mouthLeft",
                  "x":0.4502387,
                  "y":0.2601221
               },
               {
                  "type":"mouthRight",
                  "x":0.5393077,
                  "y":0.26036945
               },
               {
                  "type":"nose",
                  "x":0.49708697,
                  "y":0.2186894
               }
            ],
            "mouthOpen":"None",
            "mustache":"None",
            "pose":{
               "pitch":3.009071,
               "roll":-0.5177236,
               "yaw":1.9940312
            },
            "quality":{
               "brightness":90.198135,
               "sharpness":95.51619
            },
            "smile":"None",
            "sunglasses":"None"
         }
      ],
      "orientationCorrection":"None"
   }
}
```

> Example response when provider is ```azure```

```azure
{
   "meta":{
      "language":"",
      "provider":"azure"
   },
   "result":{
      "faces":[
         {
            "age":57,
            "faceRectangle":{
               "height":252,
               "left":382,
               "top":146,
               "width":252
            },
            "gender":"Male"
         }
      ]
   }
}
```


### Request Parameters

Parameter | Default | Description 
--------- | --------| -----------
Provider | `auto` | The AI service provider you want to use. The AI Service provider can be any of the following: <ul><li>`aws` (Amazon Rekognition)</li><li>`azure` (Microsoft Azure Cognitive Services)</li><li>`gcp` (Google Cloud Vision API)</li><li>`auto` (let RAPYD.AI choose service provider automatically.)</li></ul>

### File Properties

The request sends a file over HTTPS. 

File Properties | Description 
--------------- | ----------- 
Image File Size | Maximum file size is 2 MB
File Format | The following image types are supported:<ul><li>JPEG</li><li>PNG8</li><li>PNG24</li><li>GIF</li><li>Animated GIF (first frame only)</li><li>BMP</li><li>WEBP</li><li>RAW</li><li>ICO</li><li>PDF</li><li>TIFF</li></ul>
Image Dimensions | The recommended image size is 1600 x 1200 pixels (ca. 1.9M pixels). The larger the faces on the image the better. The distance between eyes is most important.

The response object contains many information. Please see the following links for more details:

<a href = "https://cloud.google.com/vision/docs/reference/rpc/google.cloud.vision.v1#faceannotation", target = "_blank">Face detection results from GCP</a>

## Landmark Detection

Landmark detection detects public places, tourist attractions or well-known landmarks in an image. It provides the label, the geo-coordinates, the position, and the confidence score of the detected landmark.

Object information is returned in English only.

### HTTP Request

`POST /v1/vision/landmark`

```shell

curl --location --request POST 'https://api.rapyd.ai/v1/vision/landmark' \
--header 'PROVIDER: gcp' \
--header 'ACCOUNT-ID: your-accountid' \
--header 'Authorization: Bearer your-token' \
--form 'file=landmark_demo.png'

```

```javascript

var myHeaders = new Headers();
myHeaders.append("PROVIDER", "gcp");
myHeaders.append("ACCOUNT-ID", "your-accountid");
myHeaders.append("Authorization", "Bearer your-token");

var formdata = new FormData();
formdata.append("file", fileInput.files[0], "landmark_demo.png");

var requestOptions = {
  method: 'POST',
  headers: myHeaders,
  body: formdata,
  redirect: 'follow'
};

fetch("https://api.rapyd.ai/v1/vision/landmark", requestOptions)
  .then(response => response.text())
  .then(result => console.log(result))
  .catch(error => console.log('error', error));

```

```jsx

var unirest = require('unirest');
var req = unirest('POST', 'https://api.rapyd.ai/v1/vision/landmark')
  .headers({
    'PROVIDER': 'gcp',
    'ACCOUNT-ID': 'your-accountid',
    'Authorization': 'Bearer your-token'
  })
  .attach('file', 'landmark_demo.png')
  .end(function (res) { 
    if (res.error) throw new Error(res.error); 
    console.log(res.raw_body);
  });

```

```python

import requests

url = "https://api.rapyd.ai/v1/vision/landmark"

payload = {}
files = [
  ('file', open('landmark_demo.png','rb'))
]
headers = {
  'PROVIDER': 'gcp',
  'ACCOUNT-ID': 'your-accountid',
  'Authorization': 'Bearer your-token'
}

response = requests.request("POST", url, headers=headers, data = payload, files = files)

print(response.text.encode('utf8'))

```

```r

library(httr)

url <- "https://api.rapyd.ai/v1/vision/landmark"

headers <- c("ACCOUNT-ID" = "your-accountid", 
             "Authorization" = "Bearer your-token",
             "PROVIDER" = "gcp")

payload <- list(file = upload_file("landmark_demo.png"))

response <- POST(url, add_headers(headers), body = payload)
result <- content(response, "parsed")

```

> Make sure to replace `your-accountid` and `your-token` with your personal credentials.

> The above command returns results in JSON representation.

> Example response when provider is `gcp`:

```json
{
    "meta": {
        "provider": "GCP",
        "language": ""
    },
    "result": [
        {
            "description": "Palace of Fine Arts",
            "score": 0.68384635,
            "boundingPoly": [
                {
                    "x": 108,
                    "y": 102
                },
                {
                    "x": 256,
                    "y": 102
                },
                {
                    "x": 256,
                    "y": 398
                },
                {
                    "x": 108,
                    "y": 398
                }
            ],
            "locations": [
                {
                    "lng": -122.447777,
                    "lat": 37.80290085993192
                }
            ]
        }
    ]
}
```

> Example response when provider is `azure`:

```json
{
   "meta":{
      "language":"",
      "provider":"azure"
   },
   "result":{
      "categories":[
         {
            "detail":{
               "landmarks":[
                  {
                     "confidence":0.9999419450759888,
                     "name":"Eiffel Tower"
                  }
               ]
            },
            "name":"building_",
            "score":0.3671875
         },
         {
            "detail":{
               "landmarks":[
                  {
                     "confidence":0.9999419450759888,
                     "name":"Eiffel Tower"
                  }
               ]
            },
            "name":"building_church",
            "score":0.609375
         }
      ]
   }
}
```

### Request Parameters

Parameter | Default | Description 
--------- | --------| -----------
Provider | `auto` | The AI service provider you want to use. The AI Service provider can be any of the following: <ul><li>`azure` (Microsoft Azure Cognitive Services)</li><li>`gcp` (Google Cloud Vision API)</li><li>`auto` (let RAPYD.AI choose service provider automatically.)</li></ul>

### File Properties

The request sends a file over HTTPS. 

File Properties | Description 
--------------- | ----------- 
Image File Size | Maximum file size is 2 MB
File Format | The following image types are supported:<ul><li>JPEG</li><li>PNG8</li><li>PNG24</li><li>GIF</li><li>Animated GIF (first frame only)</li><li>BMP</li><li>WEBP</li><li>RAW</li><li>ICO</li><li>PDF</li><li>TIFF</li></ul>
Image Dimensions | The recommended image size is 640 x 480 pixels (ca. 300k pixels). Larger image sizes may not gain much in accuracy, while greatly increasing bandwidth usage and processing time.

## Object Localization

Object localization detects multiple objects in an image and provides the label, the position, and the confidence score of the detected object.

Object information is returned in English only.

### HTTP Request

`POST /v1/vision/localize`

```shell

curl --location --request POST 'https://api.rapyd.ai/v1/vision/localize' \
--header 'PROVIDER: gcp' \
--header 'ACCOUNT-ID: your-accountid' \
--header 'Authorization: Bearer your-token' \
--form 'file=localize_demo.png'

```

```javascript

var myHeaders = new Headers();
myHeaders.append("PROVIDER", "gcp");
myHeaders.append("ACCOUNT-ID", "your-accountid");
myHeaders.append("Authorization", "Bearer your-token");

var formdata = new FormData();
formdata.append("file", fileInput.files[0], "localize_demo.png");

var requestOptions = {
  method: 'POST',
  headers: myHeaders,
  body: formdata,
  redirect: 'follow'
};

fetch("https://api.rapyd.ai/v1/vision/localize", requestOptions)
  .then(response => response.text())
  .then(result => console.log(result))
  .catch(error => console.log('error', error));

```

```jsx

var unirest = require('unirest');
var req = unirest('POST', 'https://api.rapyd.ai/v1/vision/localize')
  .headers({
    'PROVIDER': 'gcp',
    'ACCOUNT-ID': 'your-accountid',
    'Authorization': 'Bearer your-token'
  })
  .attach('file', 'localize_demo.png')
  .end(function (res) { 
    if (res.error) throw new Error(res.error); 
    console.log(res.raw_body);
  });

```

```python

import requests

url = "https://api.rapyd.ai/v1/vision/localize"

payload = {}
files = [
  ('file', open('localize_demo.png','rb'))
]
headers = {
  'PROVIDER': 'gcp',
  'ACCOUNT-ID': 'your-accountid',
  'Authorization': 'Bearer your-token'
}

response = requests.request("POST", url, headers=headers, data = payload, files = files)

print(response.text.encode('utf8'))


```

```r

library(httr)

url <- "https://api.rapyd.ai/v1/vision/localize"

headers <- c("ACCOUNT-ID" = "your-accountid", 
             "Authorization" = "Bearer your-token",
             "PROVIDER" = "gcp")

payload <- list(file = upload_file("localize_demo.png"))

response <- POST(url, add_headers(headers), body = payload)
result <- content(response, "parsed")

```

> Make sure to replace `your-accountid` and `your-token` with your personal credentials.

> The above command returns results in JSON representation.

> Example response when provider is `gcp`:

```json

{
    "meta": {
        "provider": "gcp",
        "language": ""
    },
    "result": [
        {
            "description": "Wheel",
            "score": 0.9287957,
            "boundingPoly": [
                {
                    "x": 0.21665983,
                    "y": 0.8182854
                },
                {
                    "x": 0.3499323,
                    "y": 0.8182854
                },
                {
                    "x": 0.3499323,
                    "y": 0.99085253
                },
                {
                    "x": 0.21665983,
                    "y": 0.99085253
                }
            ]
        },
        {
            "description": "Pants",
            "score": 0.9245052,
            "boundingPoly": [
                {
                    "x": 0.61920214,
                    "y": 0.7110153
                },
                {
                    "x": 0.7021143,
                    "y": 0.7110153
                },
                {
                    "x": 0.7021143,
                    "y": 0.9056063
                },
                {
                    "x": 0.61920214,
                    "y": 0.9056063
                }
            ]
        },
        {
            "description": "Person",
            "score": 0.8962906,
            "boundingPoly": [
                {
                    "x": 0.072677895,
                    "y": 0.4074293
                },
                {
                    "x": 0.2129082,
                    "y": 0.4074293
                },
                {
                    "x": 0.2129082,
                    "y": 0.9247987
                },
                {
                    "x": 0.072677895,
                    "y": 0.9247987
                }
            ]
        },
        {
            "description": "Person",
            "score": 0.84560376,
            "boundingPoly": [
                {
                    "x": 0.6047527,
                    "y": 0.501253
                },
                {
                    "x": 0.7425805,
                    "y": 0.501253
                },
                {
                    "x": 0.7425805,
                    "y": 0.9682343
                },
                {
                    "x": 0.6047527,
                    "y": 0.9682343
                }
            ]
        },
        {
            "description": "Person",
            "score": 0.8412963,
            "boundingPoly": [
                {
                    "x": 0.20903979,
                    "y": 0.44468263
                },
                {
                    "x": 0.32457075,
                    "y": 0.44468263
                },
                {
                    "x": 0.32457075,
                    "y": 0.64302355
                },
                {
                    "x": 0.20903979,
                    "y": 0.64302355
                }
            ]
        },
        {
            "description": "Top",
            "score": 0.8289973,
            "boundingPoly": [
                {
                    "x": 0.60539424,
                    "y": 0.5631088
                },
                {
                    "x": 0.72236294,
                    "y": 0.5631088
                },
                {
                    "x": 0.72236294,
                    "y": 0.73758584
                },
                {
                    "x": 0.60539424,
                    "y": 0.73758584
                }
            ]
        },
        {
            "description": "Motorcycle",
            "score": 0.824747,
            "boundingPoly": [
                {
                    "x": 0.031174297,
                    "y": 0.577174
                },
                {
                    "x": 0.3698026,
                    "y": 0.577174
                },
                {
                    "x": 0.3698026,
                    "y": 0.992837
                },
                {
                    "x": 0.031174297,
                    "y": 0.992837
                }
            ]
        },
        {
            "description": "Person",
            "score": 0.7636599,
            "boundingPoly": [
                {
                    "x": 0.2532207,
                    "y": 0.60297704
                },
                {
                    "x": 0.35460314,
                    "y": 0.60297704
                },
                {
                    "x": 0.35460314,
                    "y": 0.7952354
                },
                {
                    "x": 0.2532207,
                    "y": 0.7952354
                }
            ]
        },
        {
            "description": "Pants",
            "score": 0.7326683,
            "boundingPoly": [
                {
                    "x": 0.07288302,
                    "y": 0.67554694
                },
                {
                    "x": 0.15689848,
                    "y": 0.67554694
                },
                {
                    "x": 0.15689848,
                    "y": 0.8859668
                },
                {
                    "x": 0.07288302,
                    "y": 0.8859668
                }
            ]
        },
        {
            "description": "Wheel",
            "score": 0.65781885,
            "boundingPoly": [
                {
                    "x": 0.0026128727,
                    "y": 0.83867663
                },
                {
                    "x": 0.10945473,
                    "y": 0.83867663
                },
                {
                    "x": 0.10945473,
                    "y": 0.9945914
                },
                {
                    "x": 0.0026128727,
                    "y": 0.9945914
                }
            ]
        }
    ]
}

```

> Example response when provider is `aws`:

```json
{
   "meta":{
      "language":"",
      "provider":"aws"
   },
   "result":{
      "labels":[
         {
            "confidence":99.93255,
            "instances":[
               
            ],
            "name":"Transportation",
            "parents":[
               
            ]
         },
         {
            "confidence":99.93255,
            "instances":[
               {
                  "boundingBox":{
                     "height":0.26746246,
                     "left":0.2435077,
                     "top":0.7304542,
                     "width":0.43250093
                  },
                  "confidence":99.93255
               },
               {
                  "boundingBox":{
                     "height":0.20392673,
                     "left":0.64362967,
                     "top":0.69532245,
                     "width":0.23975754
                  },
                  "confidence":99.69274
               },
               {
                  "boundingBox":{
                     "height":0.11905708,
                     "left":0.91752166,
                     "top":0.60079324,
                     "width":0.08082161
                  },
                  "confidence":99.64808
               }
            ],
            "name":"Car",
            "parents":[
               {
                  "name":"Vehicle"
               },
               {
                  "name":"Transportation"
               }
            ]
         },
         {
            "confidence":99.93255,
            "instances":[
               
            ],
            "name":"Automobile",
            "parents":[
               {
                  "name":"Vehicle"
               },
               {
                  "name":"Transportation"
               }
            ]
         },
         {
            "confidence":99.93255,
            "instances":[
               
            ],
            "name":"Vehicle",
            "parents":[
               {
                  "name":"Transportation"
               }
            ]
         },
         {
            "confidence":99.66535,
            "instances":[
               
            ],
            "name":"Human",
            "parents":[
               
            ]
         },
         {
            "confidence":99.66535,
            "instances":[
               {
                  "boundingBox":{
                     "height":0.25602785,
                     "left":0.19563706,
                     "top":0.71866006,
                     "width":0.074756525
                  },
                  "confidence":99.66535
               },
               {
                  "boundingBox":{
                     "height":0.2606125,
                     "left":0.16511679,
                     "top":0.70453167,
                     "width":0.057169415
                  },
                  "confidence":98.798164
               },
               {
                  "boundingBox":{
                     "height":0.08052279,
                     "left":0.9173708,
                     "top":0.5655817,
                     "width":0.022436142
                  },
                  "confidence":86.93286
               },
               {
                  "boundingBox":{
                     "height":0.09262364,
                     "left":0.44430676,
                     "top":0.66099834,
                     "width":0.033827115
                  },
                  "confidence":48.962578
               }
            ],
            "name":"Person",
            "parents":[
               
            ]
         },
         {
            "confidence":97.96712,
            "instances":[
               {
                  "boundingBox":{
                     "height":0.086164854,
                     "left":0.75191283,
                     "top":0.8163411,
                     "width":0.04245138
                  },
                  "confidence":97.96712
               },
               {
                  "boundingBox":{
                     "height":0.076943204,
                     "left":0.84725034,
                     "top":0.76657265,
                     "width":0.029026221
                  },
                  "confidence":62.06658
               }
            ],
            "name":"Wheel",
            "parents":[
               {
                  "name":"Machine"
               }
            ]
         },
         {
            "confidence":97.96712,
            "instances":[
               
            ],
            "name":"Machine",
            "parents":[
               
            ]
         },
         {
            "confidence":88.32316,
            "instances":[
               
            ],
            "name":"Urban",
            "parents":[
               
            ]
         },
         {
            "confidence":88.32316,
            "instances":[
               
            ],
            "name":"Building",
            "parents":[
               
            ]
         },
         {
            "confidence":88.32316,
            "instances":[
               
            ],
            "name":"Neighborhood",
            "parents":[
               {
                  "name":"Urban"
               },
               {
                  "name":"Building"
               }
            ]
         },
         {
            "confidence":80.73974,
            "instances":[
               
            ],
            "name":"Canopy",
            "parents":[
               
            ]
         },
         {
            "confidence":80.73974,
            "instances":[
               
            ],
            "name":"Awning",
            "parents":[
               {
                  "name":"Canopy"
               }
            ]
         },
         {
            "confidence":76.45942,
            "instances":[
               
            ],
            "name":"Road",
            "parents":[
               
            ]
         },
         {
            "confidence":60.37967,
            "instances":[
               
            ],
            "name":"Path",
            "parents":[
               
            ]
         },
         {
            "confidence":60.273117,
            "instances":[
               
            ],
            "name":"Town",
            "parents":[
               {
                  "name":"Urban"
               },
               {
                  "name":"Building"
               }
            ]
         },
         {
            "confidence":60.273117,
            "instances":[
               
            ],
            "name":"City",
            "parents":[
               {
                  "name":"Urban"
               },
               {
                  "name":"Building"
               }
            ]
         },
         {
            "confidence":57.69777,
            "instances":[
               
            ],
            "name":"Shop",
            "parents":[
               
            ]
         },
         {
            "confidence":56.987423,
            "instances":[
               
            ],
            "name":"Pedestrian",
            "parents":[
               {
                  "name":"Person"
               }
            ]
         }
      ]
   }
}
```

> Example response when provider is `azure`:

```json
{
   "meta":{
      "language":"",
      "provider":"azure"
   },
   "result":{
      "metadata":{
         "format":"Png",
         "height":480,
         "width":640
      },
      "objects":[
         {
            "confidence":0.597,
            "object":"car",
            "parent":{
               "confidence":0.618,
               "object":"Land vehicle",
               "parent":{
                  "confidence":0.618,
                  "object":"Vehicle"
               }
            },
            "rectangle":{
               "h":51,
               "w":45,
               "x":591,
               "y":289
            }
         },
         {
            "confidence":0.824,
            "object":"car",
            "parent":{
               "confidence":0.853,
               "object":"Land vehicle",
               "parent":{
                  "confidence":0.853,
                  "object":"Vehicle"
               }
            },
            "rectangle":{
               "h":96,
               "w":162,
               "x":411,
               "y":337
            }
         },
         {
            "confidence":0.858,
            "object":"car",
            "parent":{
               "confidence":0.884,
               "object":"Land vehicle",
               "parent":{
                  "confidence":0.884,
                  "object":"Vehicle"
               }
            },
            "rectangle":{
               "h":124,
               "w":263,
               "x":163,
               "y":356
            }
         }
      ]
   }
}

```

### Request Parameters

Parameter | Default | Description 
--------- | --------| -----------
Provider | `auto` | The AI service provider you want to use. The AI Service provider can be any of the following: <ul><li>`aws` (Amazon Rekognition)</li><li>`azure` (Microsoft Azure Cognitive Services)</li><li>`gcp` (Google Cloud Vision API)</li><li>`auto` (let RAPYD.AI choose service provider automatically.)</li></ul>


### File Properties

The request sends a file over HTTPS. 

File Properties | Description 
--------------- | ----------- 
Image File Size | Maximum file size is 2 MB
File Format | The following image types are supported:<ul><li>JPEG</li><li>PNG8</li><li>PNG24</li><li>GIF</li><li>Animated GIF (first frame only)</li><li>BMP</li><li>WEBP</li><li>RAW</li><li>ICO</li><li>PDF</li><li>TIFF</li></ul>
Image Dimensions | The recommended image size is 640 x 480 pixels (ca. 300k pixels). Larger image sizes may not gain much in accuracy, while greatly increasing bandwidth usage and processing time.

## Text Detection

Text detection extracts text from an image using OCR (optical character recognition). 

Extracted text structures follow a strict hierarchy as follows (bottom to top level):
* Symbol -> Word -> Paragraph -> Block -> Page  

Each of these components have their own properties such as position and confidence score.

### HTTP Request

`POST /v1/vision/text`

```shell

curl --location --request POST 'https://api.rapyd.ai/v1/vision/text' \
--header 'PROVIDER: gcp' \
--header 'ACCOUNT-ID: your-accountid' \
--header 'Authorization: Bearer your-token' \
--form 'file=text_demo.png'

```

```javascript

var myHeaders = new Headers();
myHeaders.append("PROVIDER", "gcp");
myHeaders.append("ACCOUNT-ID", "your-accountid");
myHeaders.append("Authorization", "Bearer your-token");

var formdata = new FormData();
formdata.append("file", fileInput.files[0], "text_demo.png");

var requestOptions = {
  method: 'POST',
  headers: myHeaders,
  body: formdata,
  redirect: 'follow'
};

fetch("https://api.rapyd.ai/v1/vision/text", requestOptions)
  .then(response => response.text())
  .then(result => console.log(result))
  .catch(error => console.log('error', error));

```

```jsx

var unirest = require('unirest');
var req = unirest('POST', 'https://api.rapyd.ai/v1/vision/text')
  .headers({
    'PROVIDER': 'gcp',
    'ACCOUNT-ID': 'your-accountid',
    'Authorization': 'Bearer your-token'
  })
  .attach('file', 'text_demo.png')
  .end(function (res) { 
    if (res.error) throw new Error(res.error); 
    console.log(res.raw_body);
  });
  
```

```python

import requests

url = "https://api.rapyd.ai/v1/vision/text"

payload = {}
files = [
  ('file', open('text_demo.png','rb'))
]
headers = {
  'PROVIDER': 'gcp',
  'ACCOUNT-ID': 'your-accountid',
  'Authorization': 'Bearer your-token'
}

response = requests.request("POST", url, headers=headers, data = payload, files = files)

print(response.text.encode('utf8'))


```

```r

library(httr)

url <- "https://api.rapyd.ai/v1/vision/text"

headers <- c("ACCOUNT-ID" = "your-accountid", 
             "Authorization" = "Bearer your-token",
             "PROVIDER" = "gcp")

payload <- list(file = upload_file("text_demo.png"))

response <- POST(url, add_headers(headers), body = payload)
result <- content(response, "parsed")

```

> Make sure to replace `your-accountid` and `your-token` with your personal credentials.

> The above command returns results in JSON representation.

> Example response when provider is `gcp`:

```json
{
    "meta": {
        "provider": "GCP",
        "language": ""
    },
    "result": [
        {
            "description": "SCHOOL\nSPEED\nLIMIT\n25\nWHEN\nCHILDREN\nARE PRESENT\n",
            "boundingPoly": [
                {
                    "x": 596,
                    "y": 387
                },
                {
                    "x": 904,
                    "y": 387
                },
                {
                    "x": 904,
                    "y": 971
                },
                {
                    "x": 596,
                    "y": 971
                }
            ]
        },
        {
            "description": "SCHOOL",
            "boundingPoly": [
                {
                    "x": 596,
                    "y": 389
                },
                {
                    "x": 904,
                    "y": 387
                },
                {
                    "x": 904,
                    "y": 456
                },
                {
                    "x": 596,
                    "y": 458
                }
            ]
        },
        {
            "description": "SPEED",
            "boundingPoly": [
                {
                    "x": 612,
                    "y": 522
                },
                {
                    "x": 877,
                    "y": 520
                },
                {
                    "x": 877,
                    "y": 575
                },
                {
                    "x": 612,
                    "y": 577
                }
            ]
        },
        {
            "description": "LIMIT",
            "boundingPoly": [
                {
                    "x": 634,
                    "y": 604
                },
                {
                    "x": 849,
                    "y": 604
                },
                {
                    "x": 849,
                    "y": 659
                },
                {
                    "x": 634,
                    "y": 659
                }
            ]
        },
        {
            "description": "25",
            "boundingPoly": [
                {
                    "x": 608,
                    "y": 684
                },
                {
                    "x": 867,
                    "y": 684
                },
                {
                    "x": 867,
                    "y": 827
                },
                {
                    "x": 608,
                    "y": 827
                }
            ]
        },
        {
            "description": "WHEN",
            "boundingPoly": [
                {
                    "x": 685,
                    "y": 870
                },
                {
                    "x": 784,
                    "y": 870
                },
                {
                    "x": 784,
                    "y": 897
                },
                {
                    "x": 685,
                    "y": 897
                }
            ]
        },
        {
            "description": "CHILDREN",
            "boundingPoly": [
                {
                    "x": 642,
                    "y": 904
                },
                {
                    "x": 827,
                    "y": 902
                },
                {
                    "x": 827,
                    "y": 933
                },
                {
                    "x": 642,
                    "y": 935
                }
            ]
        },
        {
            "description": "ARE",
            "boundingPoly": [
                {
                    "x": 596,
                    "y": 940
                },
                {
                    "x": 670,
                    "y": 941
                },
                {
                    "x": 670,
                    "y": 970
                },
                {
                    "x": 596,
                    "y": 969
                }
            ]
        },
        {
            "description": "PRESENT",
            "boundingPoly": [
                {
                    "x": 699,
                    "y": 940
                },
                {
                    "x": 871,
                    "y": 941
                },
                {
                    "x": 871,
                    "y": 971
                },
                {
                    "x": 699,
                    "y": 970
                }
            ]
        }
    ]
}
```

> Example response when provider is `aws`

```json
{
   "meta":{
      "language":"",
      "provider":"aws"
   },
   "result":{
      "textDetections":[
         {
            "confidence":99.96048,
            "detectedText":"SCHOOL",
            "geometry":{
               "boundingBox":{
                  "height":0.059901997,
                  "left":0.41503906,
                  "top":0.3580729,
                  "width":0.20507498
               },
               "polygon":[
                  {
                     "x":0.41503906,
                     "y":0.3580729
                  },
                  {
                     "x":0.620114,
                     "y":0.35616863
                  },
                  {
                     "x":0.62042695,
                     "y":0.4160706
                  },
                  {
                     "x":0.41535196,
                     "y":0.41797492
                  }
               ]
            },
            "id":0,
            "parentId":"None",
            "type":"LINE"
         },
         {
            "confidence":99.98234,
            "detectedText":"SPEED",
            "geometry":{
               "boundingBox":{
                  "height":0.057378843,
                  "left":0.421665,
                  "top":0.47647533,
                  "width":0.1875003
               },
               "polygon":[
                  {
                     "x":0.421665,
                     "y":0.47647533
                  },
                  {
                     "x":0.6091653,
                     "y":0.47525543
                  },
                  {
                     "x":0.6093753,
                     "y":0.53263426
                  },
                  {
                     "x":0.421875,
                     "y":0.5338542
                  }
               ]
            },
            "id":1,
            "parentId":"None",
            "type":"LINE"
         },
         {
            "confidence":99.986595,
            "detectedText":"LIMIT",
            "geometry":{
               "boundingBox":{
                  "height":0.057398427,
                  "left":0.43525207,
                  "top":0.5533881,
                  "width":0.15459111
               },
               "polygon":[
                  {
                     "x":0.43525207,
                     "y":0.5533881
                  },
                  {
                     "x":0.5898432,
                     "y":0.5519739
                  },
                  {
                     "x":0.59013855,
                     "y":0.6093723
                  },
                  {
                     "x":0.43554744,
                     "y":0.61078656
                  }
               ]
            },
            "id":2,
            "parentId":"None",
            "type":"LINE"
         },
         {
            "confidence":99.89751,
            "detectedText":"25",
            "geometry":{
               "boundingBox":{
                  "height":0.13938081,
                  "left":0.41544846,
                  "top":0.6276083,
                  "width":0.18847631
               },
               "polygon":[
                  {
                     "x":0.41544846,
                     "y":0.6276083
                  },
                  {
                     "x":0.60392475,
                     "y":0.6262442
                  },
                  {
                     "x":0.6044922,
                     "y":0.765625
                  },
                  {
                     "x":0.41601586,
                     "y":0.7669891
                  }
               ]
            },
            "id":3,
            "parentId":"None",
            "type":"LINE"
         },
         {
            "confidence":99.82379,
            "detectedText":"WHEN",
            "geometry":{
               "boundingBox":{
                  "height":0.03125,
                  "left":0.47070312,
                  "top":0.79817706,
                  "width":0.076171875
               },
               "polygon":[
                  {
                     "x":0.47070312,
                     "y":0.79817706
                  },
                  {
                     "x":0.546875,
                     "y":0.79817706
                  },
                  {
                     "x":0.546875,
                     "y":0.82942706
                  },
                  {
                     "x":0.47070312,
                     "y":0.82942706
                  }
               ]
            },
            "id":4,
            "parentId":"None",
            "type":"LINE"
         },
         {
            "confidence":99.91038,
            "detectedText":"CHILDREN",
            "geometry":{
               "boundingBox":{
                  "height":0.031289447,
                  "left":0.44122976,
                  "top":0.8333351,
                  "width":0.13396531
               },
               "polygon":[
                  {
                     "x":0.44122976,
                     "y":0.8333351
                  },
                  {
                     "x":0.5751951,
                     "y":0.83199
                  },
                  {
                     "x":0.5753718,
                     "y":0.86327946
                  },
                  {
                     "x":0.4414065,
                     "y":0.86462456
                  }
               ]
            },
            "id":5,
            "parentId":"None",
            "type":"LINE"
         },
         {
            "confidence":99.85474,
            "detectedText":"ARE PRESENT",
            "geometry":{
               "boundingBox":{
                  "height":0.032753557,
                  "left":0.4082035,
                  "top":0.8643817,
                  "width":0.19635078
               },
               "polygon":[
                  {
                     "x":0.4082035,
                     "y":0.8643817
                  },
                  {
                     "x":0.6045543,
                     "y":0.8650575
                  },
                  {
                     "x":0.6044909,
                     "y":0.89781106
                  },
                  {
                     "x":0.4081401,
                     "y":0.8971352
                  }
               ]
            },
            "id":6,
            "parentId":"None",
            "type":"LINE"
         },
         {
            "confidence":99.96048,
            "detectedText":"SCHOOL",
            "geometry":{
               "boundingBox":{
                  "height":0.05859375,
                  "left":0.41503906,
                  "top":0.3580729,
                  "width":0.20508225
               },
               "polygon":[
                  {
                     "x":0.41503906,
                     "y":0.3580729
                  },
                  {
                     "x":0.6201172,
                     "y":0.35677084
                  },
                  {
                     "x":0.6201172,
                     "y":0.4153646
                  },
                  {
                     "x":0.41601562,
                     "y":0.41796875
                  }
               ]
            },
            "id":7,
            "parentId":0,
            "type":"WORD"
         },
         {
            "confidence":99.98234,
            "detectedText":"SPEED",
            "geometry":{
               "boundingBox":{
                  "height":0.05729999,
                  "left":0.421875,
                  "top":0.4765625,
                  "width":0.18652798
               },
               "polygon":[
                  {
                     "x":0.421875,
                     "y":0.4765625
                  },
                  {
                     "x":0.60839844,
                     "y":0.4752604
                  },
                  {
                     "x":0.609375,
                     "y":0.53255206
                  },
                  {
                     "x":0.421875,
                     "y":0.5338542
                  }
               ]
            },
            "id":8,
            "parentId":1,
            "type":"WORD"
         },
         {
            "confidence":99.986595,
            "detectedText":"LIMIT",
            "geometry":{
               "boundingBox":{
                  "height":0.057291668,
                  "left":0.43554688,
                  "top":0.55338544,
                  "width":0.15430237
               },
               "polygon":[
                  {
                     "x":0.43554688,
                     "y":0.55338544
                  },
                  {
                     "x":0.58984375,
                     "y":0.5520833
                  },
                  {
                     "x":0.58984375,
                     "y":0.609375
                  },
                  {
                     "x":0.43554688,
                     "y":0.61067706
                  }
               ]
            },
            "id":9,
            "parentId":2,
            "type":"WORD"
         },
         {
            "confidence":99.89751,
            "detectedText":"25",
            "geometry":{
               "boundingBox":{
                  "height":0.13932633,
                  "left":0.41601562,
                  "top":0.6276042,
                  "width":0.18750452
               },
               "polygon":[
                  {
                     "x":0.41601562,
                     "y":0.6276042
                  },
                  {
                     "x":0.6035156,
                     "y":0.62630206
                  },
                  {
                     "x":0.6044922,
                     "y":0.765625
                  },
                  {
                     "x":0.41601562,
                     "y":0.76692706
                  }
               ]
            },
            "id":10,
            "parentId":3,
            "type":"WORD"
         },
         {
            "confidence":99.82379,
            "detectedText":"WHEN",
            "geometry":{
               "boundingBox":{
                  "height":0.03125,
                  "left":0.47070312,
                  "top":0.79817706,
                  "width":0.076171875
               },
               "polygon":[
                  {
                     "x":0.47070312,
                     "y":0.79817706
                  },
                  {
                     "x":0.546875,
                     "y":0.79817706
                  },
                  {
                     "x":0.546875,
                     "y":0.82942706
                  },
                  {
                     "x":0.47070312,
                     "y":0.82942706
                  }
               ]
            },
            "id":11,
            "parentId":4,
            "type":"WORD"
         },
         {
            "confidence":99.91038,
            "detectedText":"CHILDREN",
            "geometry":{
               "boundingBox":{
                  "height":0.03125,
                  "left":0.44140625,
                  "top":0.8333333,
                  "width":0.1337954
               },
               "polygon":[
                  {
                     "x":0.44140625,
                     "y":0.8333333
                  },
                  {
                     "x":0.5751953,
                     "y":0.83203125
                  },
                  {
                     "x":0.5751953,
                     "y":0.86328125
                  },
                  {
                     "x":0.44140625,
                     "y":0.8645833
                  }
               ]
            },
            "id":12,
            "parentId":5,
            "type":"WORD"
         },
         {
            "confidence":99.773544,
            "detectedText":"ARE",
            "geometry":{
               "boundingBox":{
                  "height":0.032552082,
                  "left":0.40820312,
                  "top":0.8645833,
                  "width":0.05859375
               },
               "polygon":[
                  {
                     "x":0.40820312,
                     "y":0.8645833
                  },
                  {
                     "x":0.46679688,
                     "y":0.8645833
                  },
                  {
                     "x":0.46679688,
                     "y":0.89713544
                  },
                  {
                     "x":0.40820312,
                     "y":0.89713544
                  }
               ]
            },
            "id":13,
            "parentId":6,
            "type":"WORD"
         },
         {
            "confidence":99.93593,
            "detectedText":"PRESENT",
            "geometry":{
               "boundingBox":{
                  "height":0.03125,
                  "left":0.48046875,
                  "top":0.86588544,
                  "width":0.12402344
               },
               "polygon":[
                  {
                     "x":0.48046875,
                     "y":0.86588544
                  },
                  {
                     "x":0.6044922,
                     "y":0.86588544
                  },
                  {
                     "x":0.6044922,
                     "y":0.89713544
                  },
                  {
                     "x":0.48046875,
                     "y":0.89713544
                  }
               ]
            },
            "id":14,
            "parentId":6,
            "type":"WORD"
         }
      ]
   }
}
```

> Example response when provider is `azure`

```json
{
   "meta":{
      "language":"",
      "provider":"azure"
   },
   "result":{
      "language":"en",
      "orientation":"Up",
      "regions":[
         {
            "boundingBox":"423,276,212,415",
            "lines":[
               {
                  "boundingBox":"430,276,205,44",
                  "words":[
                     {
                        "boundingBox":"430,276,205,44",
                        "text":"SCHOOL"
                     }
                  ]
               },
               {
                  "boundingBox":"436,370,189,40",
                  "words":[
                     {
                        "boundingBox":"436,370,189,40",
                        "text":"SPEED"
                     }
                  ]
               },
               {
                  "boundingBox":"487,618,71,21",
                  "words":[
                     {
                        "boundingBox":"487,618,71,21",
                        "text":"WHEN"
                     }
                  ]
               },
               {
                  "boundingBox":"457,643,131,22",
                  "words":[
                     {
                        "boundingBox":"457,643,131,22",
                        "text":"CHILDREN"
                     }
                  ]
               },
               {
                  "boundingBox":"423,669,197,22",
                  "words":[
                     {
                        "boundingBox":"423,669,54,21",
                        "text":"ARE"
                     },
                     {
                        "boundingBox":"497,669,123,22",
                        "text":"PRESENT"
                     }
                  ]
               }
            ]
         }
      ],
      "textAngle":0.0
   }
}
```

### Request Parameters

Parameter | Default | Description 
--------- | --------| -----------
Provider | `auto` | The AI service provider you want to use. The AI Service provider can be any of the following: <ul><li>`aws` (Amazon Rekognition)</li><li>`azure` (Microsoft Azure Cognitive Services)</li><li>`gcp` (Google Cloud Vision API)</li><li>`auto` (let RAPYD.AI choose service provider automatically.)</li></ul>


### File Properties

The request sends a file over HTTPS. 

File Properties | Description 
--------------- | ----------- 
Image File Size | Maximum file size is 2 MB
File Format | The following image types are supported:<ul><li>JPEG</li><li>PNG8</li><li>PNG24</li><li>GIF</li><li>Animated GIF (first frame only)</li><li>BMP</li><li>WEBP</li><li>RAW</li><li>ICO</li><li>PDF</li><li>TIFF</li></ul>
Image Dimensions | The recommended image size is 1024 x 768 pixels (ca. 786k pixels). The total image size must not exceed 75M pixels (length x width).

