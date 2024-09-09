# Week 1 - Command Line & Svelte

This is svelte skeleton template. It is a simple template that includes a basic setup for a svelte project. It includes a basic folder structure.

## Prerequisites

### Resources

1. Node.js https://nodejs.org/en
2. Git https://git-scm.com/

### VS Code Extension

1. `Svelte for VS Code` by Svelte
2. `Prettier - Code formatter` by Prettier
3. `SCSS Formatter` by Sibiraj S

Optional

1. `Color Highlight` by Sergii N
2. `Material Icon Theme` by Philipp Kief
    - You can change the color of the folder icon by pressing "Ctrl + Shift + P" and search for `Material Icons: Change Folder Color`. Then select the color you want. This helps with visualizing the folder structure, if you have a lot of folders.

### VS Code Settings

1. Setting > `Label Format` > Short
2. Setting > Workbench > `Tree: Indent` > 12 or 16 //default is 8
3. Setting > `Explorer: Sort Order`
4. Settings > `Explorer: Compact Folders` > unchecked

To find these settings, search for the highlighted keywords in the search bar, it should be the first option.

## Installation

1. Clone the repository `git clone https://...`
2. Run `npm install`
   Or use `npm i`, as i is the shorthand for install.
3. To start the project run `npm run dev`
4. The site will be live at `http://localhost:5173` by default, otherwise it will be mentioned in the terminal.

## Folder Structure

1. `.svelte` files are located in the `src` folder and contain HTML, CSS, and JavaScript.
2. In SvelteKit (the framework we are using), pages that are displayed must be named `+page.svelte`, similar to how `index.html` works in a regular HTML file. The homepage will be located at `src/routes/+page.svelte`.
3. The `routes` folder contains all the pages of a website, using file-based routing.
4. The `static` folder contains all static files, such as images.
   In `src/lib`, we typically place all reusable functions and components.

## Trying it out.

### Basic HTML

1. Going to `localhost:5173`, you should see the default SvelteKit page with the message "Welcome to SvelteKit."
2. Next, let's try changing the text. Go to `src/routes/+page`.svelte, replace the text in the `<h1>` tag with "Hello World," and delete the `<p>` tag.
3. Save the file and go back to the browser, you should see the changes.

### Adding CSS

1. In the same file, add a style tag at the bottom of the file. Then give the h1 tag a color of red, and font-family of Arial. Save the file, and you should see the changes.

    Your +page.svelte file should look like this:

    ```html
    <h1>Hello World</h1>

    <style>
    	h1 {
    		color: red;
    		font-family: 'Arial';
    	}
    </style>
    ```

### Creating a new page

1. In the same `+page.svelte file`, right below `<h1>`, add an `<a>` element with a `href` attribute of `"/contact"`.

    ```html
    <a href="/contact">Contact Me</a>
    ```

2. Click on the link, you should see a 404 page. This is because we haven't created the contact page yet.

3. Create a new folder named `contact` inside `src/routes`, and then create a new file called `+page.svelte` within this folder. The file location should be `src/routes/contact/+page.svelte`. Open the file and add the following code:

    ```html
    <h1>Contact Me</h1>
    <p>You can <a href="mailto:me@email.com">contact me here</a>.</p>
    ```

4. Save the file, and go back to the browser and click on the link. You should see the contact page.

5. In sveltekit, we create page by creating a folder with the name of the page, and a file called `+page.svelte`. The file name **must be +page.svelte**.

### Using SCSS

1. Open the file `src/routes/+page.svelte`, and replace the content with the following code:

    ```html
    <div class="card">
    	<div class="img-container">
    		<img src="cat.jpg" alt="" />
    	</div>
    	<div class="user">
    		<div class="name">My Name</div>
    		<div class="position">Software Developer</div>
    	</div>

    	<p>
    		Lorem ipsum dolor sit amet consectetur adipisicing elit. Eius provident qui, nisi at
    		eaque doloribus eveniet adipisci perspiciatis sequi magni iste nulla ducimus!
    	</p>

    	<div class="actions">
    		<a class="outlined" href="https://www.instagram.com/myHandle/">Follow</a>
    		<a href="/contact">Contact</a>
    	</div>
    </div>

    <style>
    	.card {
    		box-sizing: border-box;
    		font-family: Arial, Helvetica, sans-serif;
    		display: flex;
    		flex-direction: column;
    		align-items: center;
    		width: 300px;
    		height: auto;
    		border-radius: 1rem;
    		background-color: #4c566a;
    		padding: 2rem;
    		gap: 1rem;
    		color: #d8dee9;
    	}
    	.img-container {
    		height: 128px;
    		width: 128px;
    		border-radius: 100%;
    		overflow: clip;
    		border: 4px solid transparent;
    		outline: 4px solid #d8dee9;
    	}
    	.img-container img {
    		width: 100%;
    		height: 100%;
    		object-fit: cover;
    		transition: transform 0.3s;
    	}
    	.img-container img:hover {
    		transform: scale(1.1);
    	}
    	.user {
    		display: flex;
    		flex-direction: column;
    		align-items: center;
    	}
    	.user .name {
    		font-size: 1.25rem;
    		font-weight: 600;
    	}
    	p {
    		margin: 0;
    		font-size: 0.875rem;
    		text-align: center;
    	}
    	.actions {
    		display: flex;
    		gap: 1rem;
    		margin-inline: auto;
    	}
    	.actions a {
    		margin-top: 1rem;
    		text-decoration: none;
    		background-color: #d8dee9;
    		color: #4c566a;
    		font-weight: 600;
    		display: flex;
    		align-items: center;
    		padding-block: 0.75rem;
    		padding-inline: 1.5rem;
    		border-radius: 0.375rem;
    	}
    	.actions a.outlined {
    		border: 1px solid #d8dee9;
    		color: #d8dee9;
    		background-color: transparent;
    	}
    	a:hover {
    		filter: brightness(1.05) hue-rotate(180deg);
    	}
    </style>
    ```

2. Add an image in `static` folder, give it a name like `cat.jpg` or any other name. You can use any image you like. Replace the `src` attribute in the `img` tag at line 3 with the name of the image.

3. Replace the content of name, position, description and href in the card with your own information. At line 6, 7, 11 and 16.

4. Save the file, and go back to the browser. You should see a card with your information.

5. Currently we are using CSS, which is not very efficient. We can use SCSS to make our code more readable and maintainable. To use SCSS, we need to install the sass package. Run `npm i sass -D` in the terminal.

6. Open `svelte.config.js` file in the root directory, and add the following code at line 2:

    ```js
    import { vitePreprocess } from '@sveltejs/vite-plugin-svelte';
    ```

    then add the following code after the closing bracket of kit.

    ```js
    preprocess: [vitePreprocess()];
    ```

    it should look like this, after removing the comments:

    ```js
    import adapter from '@sveltejs/adapter-auto';
    import { vitePreprocess } from '@sveltejs/vite-plugin-svelte';

    /** @type {import('@sveltejs/kit').Config} */
    const config = {
    	kit: {
    		adapter: adapter()
    	},
    	preprocess: [vitePreprocess()]
    };

    export default config;
    ```

    Save the file, and in the terminal, you should see a message that says "server restarted"

7. Now go back to the `+page.svelte file`, and change the style tag to a style tag with `lang="scss"`. It should look like this:

    ```html
    <style lang="scss">
    	...
    </style>
    ```

8. Save the file, and go back to the browser. You should see the same card as before. Now we can refactor css to scss.

9. In SCSS, we can nest classes within parent classes. For example, if the `img-container` is inside `card`, we can nest `img-container` within the card class. Similarly, since the `img` tag is inside the `img-container` class, we can nest the `img` tag within `img-container`. This makes the code more readable.

    ```scss
    .card {
    	box-sizing: border-box;
    	font-family: Arial, Helvetica, sans-serif;
    	display: flex;
    	flex-direction: column;
    	align-items: center;
    	width: 300px;
    	height: auto;
    	border-radius: 1rem;
    	background-color: #4c566a;
    	padding: 2rem;
    	gap: 1rem;
    	color: #d8dee9;

    	.img-container {
    		height: 128px;
    		width: 128px;
    		border-radius: 100%;
    		overflow: clip;
    		border: 4px solid transparent;
    		outline: 4px solid #d8dee9;

    		img {
    			width: 100%;
    			height: 100%;
    			object-fit: cover;
    			transition: transform 0.3s;
    			&:hover {
    				transform: scale(1.1);
    			}
    		}
    	}
    }
    ```

    `name` are inside `user` class, therefore we can nest them inside `user` class.

    ```scss
    .user {
    	display: flex;
    	flex-direction: column;
    	align-items: center;
    	.name {
    		font-size: 1.25rem;
    		font-weight: 600;
    	}
    }
    ```

    Try to refactor the rest of the code to SCSS. There will be no visible changes in the browser, but the code will be more readable and maintainable. After refactoring check the below code to see if you have done it correctly.

    ```scss
    <style lang="scss">
    	.card {
    		box-sizing: border-box;
    		font-family: Arial, Helvetica, sans-serif;
    		display: flex;
    		flex-direction: column;
    		align-items: center;
    		width: 300px;
    		height: auto;
    		border-radius: 1rem;
    		background-color: #4c566a;
    		padding: 2rem;
    		gap: 1rem;
    		color: #d8dee9;
    		.img-container {
    			height: 128px;
    			width: 128px;
    			border-radius: 100%;
    			overflow: clip;
    			border: 4px solid transparent;
    			outline: 4px solid #d8dee9;
    			img {
    				width: 100%;
    				height: 100%;
    				object-fit: cover;
    				transition: transform 0.3s;
    				&:hover {
    					transform: scale(1.1);
    				}
    			}
    		}
    	}
    	.user {
    		display: flex;
    		flex-direction: column;
    		align-items: center;
    		.name {
    			font-size: 1.25rem;
    			font-weight: 600;
    		}
    	}
    	p {
    		margin: 0;
    		font-size: 0.875rem;
    		text-align: center;
    	}
    	.actions {
    		display: flex;
    		gap: 1rem;
    		margin-inline: auto;
    	a {
    		margin-top: 1rem;
    		text-decoration: none;
    		background-color: #d8dee9;
    		color: #4c566a;
    		font-weight: 600;
    		display: flex;
    		align-items: center;
    		padding-block: 0.75rem;
    		padding-inline: 1.5rem;
    		border-radius: 0.375rem;
    		&.outlined {
    			border: 1px solid #d8dee9;
    			color: #d8dee9;
    			background-color: transparent;
    		}
    		&:hover {
    			filter: brightness(1.05) hue-rotate(180deg);
    		}
    	}
    }
    </style>
    ```

### Layouts

Layouts are used to wrap around the content of a page. For example, if you have a header and footer that are common to all pages, you can create a layout that contains the header and footer and wrap the content of the page with the layout.

1. Create a empty file at `src/routes/+layout.svelte`. The layout file must be named `+layout.svelte`.

2. Go to the browser, and you should see a blank page. This is because we haven't added any content to the layout file. To include the content of the page in the layout, use the `<slot/>` tag. Add `<slot/>` at line 1. Save the file and return to the browser. You should see the content of the page as before.

3. Now we can add header to the page. You can copy the following code to `+layout.svelte`

    ```html
    <header>
    	<nav>
    		<a href="/">Home</a>
    		<a href="/about">About</a>
    		<a href="/contact">Contact</a>
    	</nav>
    </header>

    <main>
    	<slot />
    </main>

    <style lang="scss">
    	header {
    		nav {
    			padding-block: 1rem;
    			display: flex;
    			gap: 2rem;
    			justify-content: center;
    			a {
    				font-size: 1rem;
    				font-weight: 600;
    				text-decoration: none;
    				color: inherit;
    			}
    		}
    	}
    	main {
    		display: flex;
    		justify-content: center;
    		padding-top: 2rem;
    	}
    </style>
    ```

4. Save the file, and go back to the browser. You should see a header with links to Home, and Contact. The content of the page should be centered. Clicking on about should show a 404 page, because we haven't created the about page yet. But the header should be visible on all pages.

### Global Style

1. Sveltekit styling is scoped by default, which means that styles in a file, only apply to that file. In web development, we often have styles that are common to all pages, like body, h1, p, etc. We can create a global style file that contains these styles.

2. Create a new file at `src/main.scss`. This file will contain the global styles. Add the following code to the file:

    ```scss
    body {
    	margin: 0;
    	padding: 0;
    	font-family: Arial, Helvetica, sans-serif;
    	background-color: #2e3440;
    	color: #d8dee9;
    }
    ```

3. Back to `+layout.svelte file`, create a `script` tag at the top of the file, and import the `main.scss` file. It should look like this:

    ```html
    <script>
    	import '../main.scss';
    </script>

    ...
    ```

4. Save the file, and go back to the browser. You should see the background color in navy.

5. We can add more global styles to the `main.scss` file, common elements are button, a tag, inputs, etc...

6. Fonts also can be imported in the `main.scss` file. For example, if you want to use a [google font](https://fonts.google.com/) , you can import it in the `main.scss` file. We usually place them at the top of the file.

    ```scss
    @import url('https://fonts.googleapis.com/css2?family=Poppins:ital,wght@0,100;0,200;0,300;0,400;0,500;0,600;0,700;0,800;0,900;1,100;1,200;1,300;1,400;1,500;1,600;1,700;1,800;1,900&display=swap');
    ```

    Then in the `body` tag, you can set the `font-family` to the imported font.

    ```scss
    body{
    	font-family: 'Poppins', sans-serif;
    	...
    }
    ```

    Save the file, and go back to the browser. You should see the font change to the imported font, except for text inside the card, because we have set the `font-family` to Arial. Go back to the `+page.svelte` file, and remove the `font-family` from the card class. It will inherit the `font-family` from the body tag.

## Conclusion

In this tutorial, we learn how to install modules, start the server, use SvelteKit's file-based routing, create a layout, and use SCSS.
