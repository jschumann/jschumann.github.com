This is a presentation/slidedeck framework for presenters at the [Guelph Web Maker Meetup](http://www.gwmm.ca/).
Using this framework, presenters can author their presentation using HTML5, 
and present it using nothing more than a web browser. The intent is 
to make it easy to create, present, and share a talk using just the basics 
of our favourite medium: the web.

This framework was originally forked from the [Google IO 2012/2013 HTML5 Slide Template](https://code.google.com/p/io-2012-slides)
by Eric Bidelman <ebidel@gmail.com> and Luke Mahé <lukem@google.com>.

## Getting stared

Clone or fork [the GitHub repository](https://github.com/jschumann/gwmm-slides), 
or download the framework from GitHub as a 
[.zip](https://github.com/jschumann/gwmm-slides/archive/master.zip). 

The slides are all found in one file: template.html. Just open it in your
favourite editor and go nuts, following the examples in the file.

When you want to view your work in progress, just open the template.html 
file in your browser. Refresh as needed while you continue to create your 
presentation.

## Configuring the framework

You'll also want to configure the framework with the details of 
your presentation.

Much of the deck is customized by changing the settings in [`slide_config.js`](slide_config.js).
Some of the customizations include the title, speaker information 
(name, social urls, blog), web fonts to load, themes, and other
general behaviour.

## Delivering your presentation

During your presentation, your slides can be run locally, just like
you did when authoring the presentation. No web server is needed. 
Just open the template.html file in your browser of choice (though 
Firefox and Chrome will likely work best).

## Customizing the `#gwmm` hash

The bottom of the slides include `#gwmm` by default. If you'd like to change
this, please update the variable `$social-tags: '#gwmm';` in
[`/theme/scss/default.scss`](theme/scss/default.scss).

See the next section on "Editing CSS" before you go editing all the things.

## Editing CSS

[Compass](http://compass-style.org/install/) is a CSS preprocessor used to compile
SCSS/SASS into CSS. We chose SCSS for the new slide deck for maintainability,
easier browser compatibility, and because...it's the future!

That said, if not comfortable working with SCSS or don't want to learn something
new, not a problem. The generated .css files can already be found in
(see [`/theme/css`](theme/css)). You can just edit those and bypass SCSS altogether.
However, our recommendation is to use Compass. It's super easy to install and use.

### Installing Compass and making changes

First, install compass (assuming you already have Ruby and RubyGems):

    sudo gem update --system
    sudo gem install compass

Or, if you're using Bundler, just enter the project directory and run:

    bundle install

This project includes a .rvmrc file which will create a gemset specific to the project. If you're
using RVM (and Bundler), entering the project directory will create the gemset, using your
current/default Ruby, and then running "bundle install" from within the project directory 
will install compass (and its required gems) into this project-specific gemset.

Next, you'll want to watch for changes to the exiting .scss files in [`/theme/scss`](theme/scss)
and any new one you add:

    $ cd gwmm-slides
    $ compass watch

This command automatically recompiles the .scss file when you make a change.
Its corresponding .css file is output to [`/theme/css`](theme/css). Slick.

By default, [`config.rb`](config.rb) in the main project folder outputs minified
.css. It's a best practice after all! However, if you want unminified files,
run watch with the style output flag:

    compass watch -s expanded

*Note:* You should not need to edit [`_base.scss`](theme/scss/_base.scss).

## Differences from Google's framework

We've removed 3 features from the original framework:
* Running from a webserver
* Presenter mode (still there; not documented)
* Generating slides from Markdown

We removed these features to simplify the framework, assuming they
wouldn't see much, if any, use. If you'd like any of these features restored, 
please fork the [GitHub repository](https://github.com/jschumann/gwmm-slides), 
add the feature back in, and submit a pull 
request. Or you can, of course, just add the feature to your own fork. 

## Contributing

Issues can be submitted to the 
[project's issue queue on GitHub](https://github.com/jschumann/gwmm-slides/issues). 

Contributions to the code should be made via the regular GitHub 
fork-and-pull-request pattern. If that's not your thing, you might want to 
give it a try. 

Failing that, you can submit your patch via the issue queue, or in a gist
linked to from an issue.

## License

Like the original framework, this project is licensed under the 
[Apache License 2.0](http://www.apache.org/licenses/LICENSE-2.0)

---

That's all she wrote!
