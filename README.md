Cordova CameraPreview Plugin
====================

Cordova plugin that allows camera interaction from HTML code.<br/>
Show camera preview popup on top of the HTML.<br/>

<p><b>Features:</b></p>
<ul>
  <li>Start a camera preview from HTML code.</li>
  <li>Drag the preview box.</li>
  <li>Set camera color effect (Android and iOS).</li>
  <li>Send the preview box to back of the HTML content.</li>
  <li>Set a custom position for the camera preview box.</li>
  <li>Set a custom size for the preview box.</li>
  <li>Maintain HTML interactivity.</li>
</ul>

<p><b>Installation:</b></p>

```cordova plugin add https://github.com/mbppower/CordovaCameraPreview.git```

<p><b>Methods:</b></p>

<p>
  <b>startCamera(rect, defaultCamera, tapEnabled, dragEnabled, toBack)</b><br/>
  <info>
  	Starts the camera preview instance.
  	<br/>
	<br/>
	When setting the toBack to TRUE, remember to add the style bellow on your app's HTML body element:
	<br/>
	<code>style="background-color='transparent'"</code>
  </info><br/>
  <i>Usage:</i><br/>
  ```
  	var tapEnabled = true; //enable tap take picture
	var dragEnabled = true; //enable preview box drag across the screen
	var toBack = true; //send preview box to the back of the webview							cordova.plugins.camerapreview.startCamera({x: 100, y: 100, width: 200, height:200}, "front", tapEnabled, dragEnabled, toBack);
```
</p>
<p>
  <b>stopCamera()</b><br/>
  <info>Stops the camera preview instance.</info><br/>
  <i>Usage:</i><br/>
  ```
  cordova.plugins.camerapreview.stopCamera();
  </code>
</p>
<p>
  <b>takePicture(size)</b><br/>
  <info>Take the picture, the parameter size is optional</info><br/>
  <i>Usage:</i><br/>
  ```
  cordova.plugins.camerapreview.takePicture({maxWidth:640, maxHeight:640});
  ```
</p>
<p>
  <b>setOnPictureTakenHandler(callback)</b><br/>
  <info>Register a callback function that receives the original picture and the image captured from the preview box.</info><br/>
  <i>Usage:</i><br/>
  ```
cordova.plugins.camerapreview.setOnPictureTakenHandler(function(result){
	document.getElementById('originalPicture').src = result[0];//originalPicturePath;
	document.getElementById('previewPicture').src = result[1];//previewPicturePath;
});
  ```
</p>
<p>
  <b>switchCamera()</b><br/>
  <info>Switch from the rear camera and front camera, if available.</info><br/>
  <i>Usage:</i><br/>
  ```
  cordova.plugins.camerapreview.switchCamera();
  ```
</p>
<p>
  <b>show()</b><br/>
  <info>Show the camera preview box.</info><br/>
  <i>Usage:</i><br/>
  <code>cordova.plugins.camerapreview.show();</code>
</p>
<p>
  <b>hide()</b><br/>
  <info>Hide the camera preview box.</info><br/>
  <i>Usage:</i><br/>
```
cordova.plugins.camerapreview.hide();
```
</p>
<p>
<b>Base64 image:</b><br/>
	Use the cordova-file in order to read the picture file and them get the base64.<br/>
	Please, refer to this documentation: http://docs.phonegap.com/en/edge/cordova_file_file.md.html<br/>
	Method <i>readAsDataURL</i>: Read file and return data as a base64-encoded data URL.
</p>
<p><b>Sample:</b><br/>
Please see the <a href="https://github.com/mbppower/CordovaCameraPreviewApp">CordovaCameraPreviewApp</a> for a complete working example for Android and iOS platforms.</p>

<p><b>Android Screenshots:</b></p>
<p><img src="https://raw.githubusercontent.com/mbppower/CordovaCameraPreview/master/docs/img/android-1.png"/></p>
<p><img src="https://raw.githubusercontent.com/mbppower/CordovaCameraPreview/master/docs/img/android-2.png"/></p>





