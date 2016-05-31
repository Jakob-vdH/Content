Microsoft Cognitive Services is a set of 21 REST APIs that enable developers of any platform or language to add machine learning smarts to their applications.

Whilst there are 21 APIs, many of the APIs have several distinct functions within them. For example, the Computer Vision API facilitates the following capabilities:
* **Analyse an image**: Gives information about the content of the image such as identifying colour schemes, objects, adult content
* **Recognise celebrities**: Identify celebrities within an image
* **Read text in images**: Recognises text embedded within an image and returns it as text
* **Generate a thumbnail**: Smartly resizes an image based on the area of interest

You would never assume that the Computer Vision API has all of these distinct but powerful capabilities from its name. But it does and it is easy to overlook a feature that might take your application to the next level because you never knew it was there.

In this article, I'll provide a very brief overview of each individual function across all of the Cognitive APIs. This should be your 'go to' article if you've ever asked yourself "I wonder if Microsoft Cognitive can do ....".

_Just so you know_ ... some of the text in this article has been extracted from the [Microsoft Cognitive Services website](https://www.microsoft.com/cognitive-services) but I've added to it and re-worded it where i think it makes sense.

## Computer Vision
<https://www.microsoft.com/cognitive-services/en-us/computer-vision-api>

Extracts rich information from images to categorize and process visual data—and protect your users from unwanted content. 

![ComputerVisionAnalyse.png](.\Images\ComputerVisionAnalyse.png)

* **Analyze an image**: This feature returns information about visual content found in an image. Use tagging, descriptions and domain-specific models to identify content and label it with confidence. Apply the adult/racy settings to enable automated restriction of adult content. provides a description of the image and identifies keywords, image format, dimensions, clip art type, line drawing type, black and white images, adult content, categories, faces and dominant colours. There are two API functions called [POST Analyze Image](https://dev.projectoxford.ai/docs/services/56f91f2d778daf23d8ec6739/operations/56f91f2e778daf14a499e1fa) and [POST Describe Image](https://dev.projectoxford.ai/docs/services/56f91f2d778daf23d8ec6739/operations/56f91f2e778daf14a499e1fe)
* **Recognize celebrities**: The Celebrity Model is an example of Domain Specific Models. Our new celebrity recognition model recognizes 200K celebrities from business, politics, sports and entertainment around the World. Domain-specific models is a continuously evolving feature within Computer Vision API. There are two API functions called [GET List Domain Specific Models](https://dev.projectoxford.ai/docs/services/56f91f2d778daf23d8ec6739/operations/56f91f2e778daf14a499e1fd) and [POST Recognize Domain Specific Content](https://dev.projectoxford.ai/docs/services/56f91f2d778daf23d8ec6739/operations/56f91f2e778daf14a499e200)
* **Read text in images**: Optical Character Recognition (OCR) detects text in an image and extracts the recognized words into a machine-readable character stream. Analyze images to detect embedded text, generate character streams and enable searching. Allow users to take photos of text instead of copying to save time and effort. There are two API functions [POST OCR](https://dev.projectoxford.ai/docs/services/56f91f2d778daf23d8ec6739/operations/56f91f2e778daf14a499e1fc) and [POST Tag Image](https://dev.projectoxford.ai/docs/services/56f91f2d778daf23d8ec6739/operations/56f91f2e778daf14a499e1ff)
* **Generate a thumbnail**: Generate a high quality storage-efficient thumbnail based on any input image. Use thumbnail generation to modify images to best suit your needs for size, shape and style. Apply smart cropping to generate thumbnails that differ from the aspect ratio of your original image, yet preserve the region of interest. There is a single API function [POST Get Thumbnail](https://dev.projectoxford.ai/docs/services/56f91f2d778daf23d8ec6739/operations/56f91f2e778daf14a499e1fb)

## Emotion
<https://www.microsoft.com/cognitive-services/en-us/emotion-api>

The Emotion API takes an facial expression in an image as an input, and returns the confidence across a set of emotions for each face in the image, as well as bounding box for the face, using the Face API. The emotions detected are anger, contempt, disgust, fear, happiness, neutral, sadness, and surprise.

![CSEmotion.png](.\Images\CSEmotion.png)

* **Emotion Recognition**: This features takes an image (a link or a binary stream) containing a human face and returns an analysis of the emotions being exhibited. There are two API functions called [POST Emotion Recognition](https://dev.projectoxford.ai/docs/services/5639d931ca73072154c1ce89/operations/563b31ea778daf121cc3a5fa) which will identify faces automatically and [POST Emotion Recognition with Face Rectangles](https://dev.projectoxford.ai/docs/services/5639d931ca73072154c1ce89/operations/56f23eb019845524ec61c4d7) which allows face rectangles to be sent with the request. This is useful if you are using the [Face API](https://www.microsoft.com/cognitive-services/en-us/face-api) to identify particular faces
* **Emotion Recognition in Video**: This features takes a video containing human faces and returns an analysis of the emotions being exhibited. The video is posted with one request and then the resulted are obtained by a separate request after the video has been processed. There are two API functions called [POST Emotion Recognition in Video](https://dev.projectoxford.ai/docs/services/5639d931ca73072154c1ce89/operations/56f8d40e1984551ec0a0984e) which is where you'd post a video to the API and [GET Recognition in Video Operation Result](https://dev.projectoxford.ai/docs/services/5639d931ca73072154c1ce89/operations/56f8d4471984551ec0a0984f) which is where the result would be obtained. See [How to Call Emotion API for Video](https://www.microsoft.com/cognitive-services/en-us/emotion-api/documentation/howtocallemotionforvideo) for more details
* 