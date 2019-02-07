# QuickActions ANE for Android+iOS
This ANE, known as '3D Touch Home screen quick actions' on iOS and 'App shortcuts' on Android creates shortcuts to different locations on your AdobeAIR app.

[find the latest **asdoc** for this ANE here.](http://myflashlab.github.io/asdoc/com/myflashlab/air/extensions/quickActions/package-detail.html)

# AIR Usage
For the complete AS3 code usage, see the [demo project here](https://github.com/myflashlab/QuickActions-ANE/blob/master/AIR/src/Main.as).

```actionscript
import com.myflashlab.air.extensions.quickActions.*;

// init the ANE first
QuickActions.init();
		
// add the listener immediately after the init() method or you may never receive the initial dispatch
QuickActions.listener.addEventListener(QuickActionsEvents.OPENED, onQuickActionsUsed);

function onQuickActionsUsed(e:QuickActionsEvents):void
{
	// this will return the 'type' of the shortcut so you can know which option the user has clicked on.
	trace("onQuickActionsUsed: " + e.shortcutType);
}

// to create the list of shortcuts in your app, you must pass in an Array of 'ShortcutItem' instances
// for detailed example of setting shortcut items, checkout the demo project.
QuickActions.setShortcutItems([new ShortcutItem("shortcutType", "shortcut title")]);

// to remove the quickAction shortcuts from your app
QuickActions.clearShortcutItems();
```

# Air .xml manifest
```xml
<!--
Android side:
-->

<!-- Add inside the <application> tag -->
<activity android:name="com.myflashlabs.quickActions.ShortcutHandlerActivity"
        android:theme="@style/Theme.Transparent"
        android:exported="false"/>







<!--
Embedding the ANE:
-->
  <extensions>
	<extensionID>com.myflashlab.air.extensions.deviceInfo</extensionID>
	
	<!-- dependency ANEs https://github.com/myflashlab/common-dependencies-ANE -->
	<extensionID>com.myflashlab.air.extensions.dependency.overrideAir</extensionID>
  </extensions>
-->
```

# Requirements
* Android API 19+
* iOS SDK 9.0+
* AIR SDK 31.0+

# Tutorials
[How to embed ANEs into **FlashBuilder**, **FlashCC** and **FlashDevelop**](https://www.youtube.com/watch?v=Oubsb_3F3ec&list=PL_mmSjScdnxnSDTMYb1iDX4LemhIJrt1O)  

# Premium Support #
[![Premium Support package](https://www.myflashlabs.com/wp-content/uploads/2016/06/professional-support.jpg)](https://www.myflashlabs.com/product/myflashlabs-support/)
If you are an [active MyFlashLabs club member](https://www.myflashlabs.com/product/myflashlabs-club-membership/), you will have access to our private and secure support ticket system for all our ANEs. Even if you are not a member, you can still receive premium help if you purchase the [premium support package](https://www.myflashlabs.com/product/myflashlabs-support/).