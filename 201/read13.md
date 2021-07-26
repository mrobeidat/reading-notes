>> # What IS Local Storage ?

#### local storage is one of the areas where native client applications have held an advantage over web applications. For native applications, the operating system typically provides an abstraction layer for storing and retrieving application-specific data like preferences or runtime state. These values may be stored in the registry, INI files, XML files, or some other place according to platform convention.


## When was local storage introduced?

#### In 2002, Adobe introduced a feature in Flash 6 that gained the unfortunate and misleading name of “Flash cookies.” Within the Flash environment, the feature is properly known as Local Shared Objects. Briefly, it allows Flash objects to store up to 100 KB of data per domain.

![](https://res.cloudinary.com/de4rvmslk/image/upload/f_auto,q_auto/LocalStorage-cover_photo.png)


#### In 2007, Google launched Gears, an open source browser plugin aimed at providing additional capabilities in browsers. (We’ve previously discussed Gears in the context of providing a geolocation API in Internet Explorer.) Gears provides an API to an embedded SQL database based on SQLite. After obtaining permission from the user once, Gears can store unlimited amounts of data per domain in SQL database tables.


## How to use html5 local Storage ?

1.  You store data based on a named key, then you can retrieve that data with the same key.
2. Calling setItem() with a named key that already exists will silently overwrite the previous value.
3. Finally, there is a property to get the total number of values in the storage area, and to iterate through all of the keys by index (to get the name of each key).

![](https://images.slideplayer.com/13/3738484/slides/slide_48.jpg)

## TRACKING CHANGES TO THE HTML5 STORAGE AREA:

#### If you want to keep track programmatically of when the storage area changes, you can trap the storage event.

#### The storage event is supported everywhere the localStorage object is supported, which includes Internet Explorer 8. IE 8 does not support the W3C standard addEventListener (although that will finally be added in IE 9).  
  

if (window.addEventListener) {  
  window.addEventListener("storage", handle_storage, false);  
} else {  
  window.attachEvent("onstorage", handle_storage);  
};  


## ** Note :** The storage event is not cancelable. From within the handle_storage callback function, there is no way to stop the change from occurring. 