# FSA Notes
----

# Anatomy of an HTML document
----

```html
<!DOCTYPE html>
<html lang="en-US">
	<head>
		<meta charset="utf-8" />
		<title>My test page</title>
	</head>
	<body>
		<p>This is my page</p>
	</body>
<html>
```

1. `<!DOCTYPE html>` : historic artifact that needs to be included for everything to work right. `<DOCTYPE html>` is the shortest string that counts as a valid doctype.
2. `<html></html>`: wraps all content - aka the root element
3. `<head></head>`: Acts as the container for item you want included in your HTML page that isn't content for the viewer. Can include keywords and page description that would appear in search results, CSS to style, etc....
4. `<meta charset=utf-8`> specifies character encoding as UTF-8
5. `<title></title>`: This sets the title of the page. Appears in the browser tab. 
6. `<body></body>`: Contains all the content that displays on the page.


# Void Elements
----
Self closing tags. Such as 
```html
<img src="#" alt="#" />
```
These insert / embed something in the document

# Meta
----
```html
<meta name="author" content="Phillip Choi" />
<meta
	  name="description"
	  content="What you want to show users in a search" />
```


# Favicon
----
icon shown in bookmarks and in a tab in a browser, left of the title. 

Can support `.ico` , `.gif`, or `.png`

```html
<link rel="icon" href="favicon.ico" type="image/xicon" />
```


# Apply CSS & JS Scripts
----

```html
<link rel="stylesheet" href="my-css-file.css" />
```

```html
<script src="my-js-file.js" defer></script>
```

defer loads the script after the html page ( this way you do not have to place your script on the bottom of your page.)

  













# Backlinks
-----
[Web Development](Web%20Development.md)
[Frontend](Frontend)

