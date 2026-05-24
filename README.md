# tiny-b-links

A simple URL shortener for B's sites hosted on GitHub Pages.

## How it Works

Since this is hosted on GitHub Pages without a real backend server, we're using a few tricks to make the links work and look good on social media.

**The 404 router**
If someone goes to a short link like `/d` for Discord, GitHub can't find a file for it, so it loads `404.html`. Inside that file is a small script with a list of my links. It checks the URL and instantly sends the user to the right place.

**The main page**
If someone just goes to the main URL without any short link, `index.html` catches them and sends them straight to my homepage at `https://home.behr.dev`.

**Preview links for Discord and Twitter**
Bots for places like Discord or Twitter can't run JavaScript. So if I just use the 404 trick, the link previews will be blank. 

To fix this, I made an `r/` folder for important links (like dev blogs). By making a real file for them (like `r/b2.html`), I can put all the image and text data right in the file so the bots can see it. It also has a quick redirect so normal users just get sent to the article right away.

## Adding New Links

**For basic links (no fancy preview image):**
Just open up `404.html` and add it to the list at the top. 
Example: `"/new": "https://example.com"`

**For links that need a preview (like a blog post):**
Make a new `.html` file inside the `r/` folder. The easiest way is to copy one that's already there (like `r/b2.html`) and just change the title, description, image link, and the redirect url inside of it. 

When you share it, you have to include the `.html` part, like `https://tiny.behr.dev/r/b2.html`.
