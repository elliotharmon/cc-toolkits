The CC Toolkits project is built with HTML and Markdown pages, strung together with a static website generator called Jekyll, and hosted on the social coding website Github. The site has been set up to make it simple for anyone to suggest updates and edit to the site's pages (mostly consisting of toolkits), add new pages/toolkits to the site, or to clone/fork the site to make a CC affiliate-focused toolkit site.

![Imgur](http://i.imgur.com/sLOIBgCl.png)

Content (images, videos, other media) on the website is licensed as marked, and is otherwise licensed under a CC BY 4.0 International License. See http://creativecommons.org/licenses/by/4.0/ for more information. The site is based on the Freelancer Theme by Jerome Lachaud: https://github.com/jeromelachaud/freelancer-theme, which utilizes the Bootstrap framework (http://getbootstrap.com/), which is licensed under an MIT license: https://github.com/twbs/bootstrap/blob/master/LICENSE .

# Painless CC Toolkit Making

## Overview:

The CC Toolkits project files can be edited in a number of ways. Suggestions and edits for the pages can be filed as issues here:

<insert repo issue page>

<insert options for editing, forking>

### File organization follows this structure:

	/cc-toolkits/
		/img/ <-- the image files are in here
		/layouts/ <-- the page templates are in here
		/default.html
		/toolkit.html
		/page.html
		...
		/_includes/ <-- the common parts of the pages are in here
			/head.html
			/submenu.html
			/footer-toolkit.html
			...
		/basics/index.html <-- the 'Basics of CC' toolkit page, in English
		/basics-de/index.html <-- the 'Basics of CC' toolkit page, in German (Deutsch)
		/culture/index.html <-- The 'CC and Culture' toolkit page, in English
		/science/index.html <-- The 'Science and CC' toolkit page, in English
		...
		/collaborate/index.html <-- The collaborate page is here
		...


### To add a translation of a toolkit page:

- Browse to an existing toolkit folder (ie /cc-toolkits/basics/)
- Make a copy of the folder, and place it next to the original
- Change the folder name to represent the translation language (ie /basics-de/)
- Open the toolkit page HTML file inside (/basics-de/index.html) with a plain text editor (ie Notepad, TextEdit)
- Edit the HTML to replace original text with translated text
- Change the front matter title (text at the top of the page) to reflect the translation language (ie 'title: Basics of CC - Deutsch')
- Replace embedded video iframes, images, and links to your preferred or language-appropriate items
- If the images you are including in your page are not hosted somewhere else (ie "https://yourwebsite.cc/picture.jpg"), then place them in the ../cc-toolkits/img/ folder

## And bam! You have a translation started.

### Translating the menu, footer

You will also want to replace the common parts of the page (header, footer, etc) with a translated version too? To translate the page menu and footer, browse to these files:

	/cc-toolkits/_includes/submenu.html <-- the toolkit template menu (videos, case studies, etc)
	/cc-toolkits/_includes/footer-toolkit.html <-- the toolkit template footer (links, license, etc)

Edit those files to include translated text/items.

### A couple more things

Now that you have a translated page menu and footer, you need to make a new toolkit page template that calls those items into your page (instead of the items in the former language).

- Browse to the toolkit page template folder at ../cc-toolkits/_layouts/toolkit.html
- Make a copy of toolkit.html and save the file name to represent the translation language (ie /toolkit-de.html)
- Edit the HTML to replace the original menu (submenu.html) and footer (footer-toolkit.html) and call for your translated items (ie /submenu-de.html and /footer-toolkit-de.html) instead.
- Browse back to your translated toolkit page (../cc-toolkits/basics-de/index.html)
- Change the front-matter (text at the top of the page) to 

Now your /basics-de/index.html toolkit is using the 'toolkit-de.html' template, which uses the 'submenu-de.html' and 'footer-toolkit.de'

### Want to make a translation of the landing page?

The landing page is located at ../cc-toolkits/index.html, which has front matter (http://jekyllrb.com/docs/frontmatter/) which says it uses the 'default' layout. The "default layout" is located at ../cc-toolkits/layouts/default.html and looks like this:

	<!DOCTYPE html>
	<html>

  	{% include head.html %}

    <body id="page-top" class="index">

    {% include header.html %}
    {% include grid.html %}
	{% include archive.html %}
	{% include collaborate.html %}
    {% include map.html %}

    <!--
      <div class="page-content">
        <div class="wrap">
        {{ content }}
        </div>
      </div>
    -->

    {% include footer.html %}
    {% include js.html %}

    </body>
	</html>

Since this template calls for multiple files (head.html, header.html, etc), translations will need to be made at those locations:

- header.html <-- where the landing page menu lives
- grid.html (topic icons)
- archive.html
- collaborate.html
- map.html
- footer.html

Name your translated landing page sections to reflect the language you translated into (ie header-de.html) and place them in the /cc-toolkits/_includes/ folder so that Jekyll knows where to find them when called.

Lastly, go back to the ../cc-toolkits/index.html file you were looking at, and make a copy of it when the appropriate filename for the language being translated to (ie ../cc-toolkits/index-de.html. Now we will have a translation of the landing page, using the new layout (template) that calls for your translated sections of the homepage (header-de.html, grid-de.html, etc).

## Not sure where to go next?
###Reply to this issue on Github, and we'll get back to you soonly:

<insert issue thread link>
