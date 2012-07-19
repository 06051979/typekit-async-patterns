# Typekit Asynchronous Loading Patterns

This repository contains example pages that demonstrate different ways of loading the Typekit script asynchronously. These are alternatives to the standard Typekit embed code:

    <script type="text/javascript" src="//use.typekit.net/KITID.js"></script>
    <script type="text/javascript">try{Typekit.load();}catch(e){}</script>

The standard Typekit embed code has many advantages. It's simple, compact, very easy to implement, and automatically helps to prevent the flash of unstyled text (or FOUT). These advantages make it the right choice for the vast majority of sites.

The asynchronous loading patterns demonstrated in this repository provide a useful alternative in situations where you *must* eliminate any possibility that a problem loading the kit could interfere with loading the rest of the page. Asynchronous patterns are longer, more difficult to implement, and require extra work to avoid the FOUT. But these approaches ensure that your page won't wait for the kit in the unlikely event that something goes wrong somewhere between the font network and the user.

When looking at these examples, start with these two:

* Standard (standard.html)
* Font events (font-events.html)

These patterns provide the best balance of trade-offs.

If you're using jQuery on your page, you might additionally look at:

* Standard jQuery (standard-jquery.html)
* Font events jQuery (font-events-jquery.html)

These are very similar to the first two, but make use of jQuery to add slightly fewer bytes to the page. The downside is that fonts can't start downloading until jQuery has been downloaded and parsed.

Finally, these additional patterns have significant drawbacks, but are illustrated for completeness:

* Async attribute (async-attribute.html)
* Bottom of body (bottom-of-body.html)
