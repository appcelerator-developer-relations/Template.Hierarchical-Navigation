# Template.Hierarchical-Navigation


The Barebones template provides the necessary scaffolding to implement native hierarchical, also known as Parent-Child or Master-Detail, using platform-specific containers with content reusability, ensuring the best native user experience with high code reusability when required.  Here's what it offers:

![](http://drops.ricardoalcocer.com/drops/readme_image-Nxc2gu6gH5.png)
![](http://sht.tl/VYhJar)

* **Index.xml** is platform specific and lives inside the iOS and Android folders
* **Index.js** picks up the request, which "Requires" the "sharedhome" controller.  This file is a single cross-platform controller used by all supported platforms.  From here we can "talk" to the "sharedhome" files, effectively providing platform-specific containers with shared content

## Important to keep in mind
This template project is using platform-specific folders to organize your **main app containers** and keep them in separate places.  This practice is perfectly fine for the main container.  For all other windows I recommend you keep your code in a single View file and use the platform attribute, for example:

```xml
<Alloy>
  <Window backgroundColor="#fff">

    <!-- this tag is Android-only -->
    <ActionBar platform="android" title="Window Title"/>

    <!-- this tag is iOS-only -->
    <Toolbar platform="ios" title="Window Title" top="20">
      <Items>
        <FlexSpace/>
        <Label id="wintitle">Window Title</Label>
        <FlexSpace/>
      </Items>
    </Toolbar>

  </Window>
</Alloy>
```

The same thing goes for your controllers, where you can use platform variables like:

```javascript

if (OS_IOS){
  // do some iOS stuff
}else if (OS_ANDROID){
  // do some Android stuff
}

```

---

# License

This code is licensed under the Apache Public License (Version 2).
