# Sciencespo-Housing

## Steps to actually see the images 
1. You need to download two chrome extentions (I tried just using chrome, so better use chrome)
	- [Custom JavaScript for Websites 2](https://chrome.google.com/webstore/detail/custom-javascript-for-web/ddbjnfjiigjmcpcpkmhogomapikjbjdk)  
	- [Stylish - Custom themes for any website](https://chrome.google.com/webstore/detail/stylish-custom-themes-for/fjnbnpbmkenffdnngjfgmeleoegfcffe?hl=es)
	
2. Once you have those extentions installed you should go to one page which is not showing the images then:
	- Open the `Custom JavaScript for Websites 2` editor and paste the following code:
```const imageList = document.querySelectorAll('#list_images img');
const imageViewer = document.getElementById('image_viewer');
const listImages = document.getElementById('list_images');
const body = document.querySelector('body');

// Replace all images sources.
imageList.forEach(image => {
  let src = image.src.split("/")[6];
  src = src.replace('adjusted_', '');
  image.src = 'https://logements.sciencespo.fr/en/paris/cms/thumb/generate/800x600/' + src;
});

// Creates button to open gallery.
const openBtn = document.createElement("button");
openBtn.innerHTML = "Open images";
openBtn.setAttribute('class', 'open-images');
imageViewer.appendChild(openBtn);
openBtn.addEventListener('click', () => {
  listImages.classList.add('open');
});

// Exit image gallery clicking anywhere.
listImages.addEventListener('click', () => {
  listImages.classList.remove('open');
});

// Exit image gallery using escape key.
body.addEventListener("keydown", e => {
  if (e.key == "Escape") {
    listImages.classList.remove('open');
  }
});
```

  - Open the `Stylish - Custom themes for any website` create a new theme (following the extention instrutions to do it)  and paste the following code:
```

```
