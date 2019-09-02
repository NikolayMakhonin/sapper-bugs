# Bug description

Supper **v0.27.8** generates incorrect relative path to the image inside CSS, and I get this error in old browsers:
GET http://sapper.de/bug/client/legacy/images/img.png 404 (Not Found)

Use this repository to reproduce it:
https://github.com/NikolayMakhonin/sapper-bugs/tree/legacy-css-path-bug

Sapper generates same CSS for [legacy ](https://github.com/NikolayMakhonin/sapper-bugs/blob/legacy-css-path-bug/__sapper__/export/bug/client/legacy/index.43e20adf.css) and [newest ](https://github.com/NikolayMakhonin/sapper-bugs/blob/legacy-css-path-bug/__sapper__/export/bug/client/index.60cd7f29.css) browsers:
```CSS
h1.svelte-vbdcuh,figure.svelte-vbdcuh,p.svelte-vbdcuh{text-align:center;margin:0 auto;background:url(images/img.png)
	}h1.svelte-vbdcuh{font-size:2.8em;text-transform:uppercase;font-weight:700;margin:0 0 0.5em 0}figure.svelte-vbdcuh{margin:0 0 1em 0}img.svelte-vbdcuh{width:100%;max-width:400px;margin:0 0 1em 0}p.svelte-vbdcuh{margin:1em auto}@media(min-width: 480px){h1.svelte-vbdcuh{font-size:4em}}
```

For legacy image path should be `../images/img.png`