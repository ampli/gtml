# GTML - an HTML pre-processor

GTML is a simple yet powerful HTML pre-processor written in Perl.  Its syntax is very close to the C language preprocessor, and it supports macros, conditional processing, file inclusion, sitemap generation, and more.  It was designed in the 1990s, for a world where HTML files were still regularly maintained by hand, but some of us still find it useful today.

## History

GTML was originally written in 1996 by Gihan Perera and was enhanced in starting in 1999 by Bruno Beaufils.  In 2004, Andrew E. Schulman took it over and moved the code to [SourceForge](https://gtml.sourceforge.net), where older releases still live today.  I have maintained the [Debian package for GTML](https://salsa.debian.org/debian/gtml) since 2010.  In 2014, Andrew communicated to me that he had abandoned the code, so I began to maintain the Debian packages idependently.  In early 2022, Bruno and I got some questions about GTML from a user.  I decided to fork the code to GitHub so there would be a real home for it again.  

The [`HISTORY.md`](docs/HISTORY.md) file contains some additional history taken from the original `README` file on SourceForge.  The original website on SourceForge is maintained using GTML itself, and the source code for that website is found in the [`docs/sourceforge/src`](docs/sourceforge/src) directory.

## How does it work?

You embed GTML commands among the HTML in your source files. GTML reads and processes the GTML commands, but leaves the rest of the text unchanged (so it will work straight away on your existing web pages).  HTML files generated by GTML are just like any other HTML files.  Because GTML doesn't attempt to interpret your HTML commands in any way, it's fully compatible with all versions of HTML, and doesn't require any specific browser or server.
   
## Is GTML for you?

If you write the HTML in your web pages by hand using a simple text editor, then you'll find GTML useful. If, on the other hand, you use a sophisticated graphical tool to generate your HTML, you probably won't be able to use GTML. There are three reasons for this:

- Your sophisticated tool won't understand the GTML commands, and might even complain violently about them
- GTML operates in a command-line batch mode, and your sophisticated tool probably operates from a graphical environment
- The source for GTML is in files ending in `.gtm` (or `.gtml`), and it generates the `.html` files, while your sophisticated tool probably generates the .html files itself
       
## Features

Here are some of the things you can do with GTML:

- Create a project file with the names of all your web pages, so you can update them all with one simple click or command
- Process only files which sources have changed directly, or with the help of makefiles
- Generate a makefile to control the process of your web pages, based on their dependencies
- Give a specific alias to a filename, useable as constants, so that it is easy to move files and have links preserved
- Specify a tree-like hierarchy of web pages, so you can add next, previous and up links automatically to your site
- Automatically generate a map of your site, with the possibility of customizing the way this table of contents will look like
- Use named constants for HTML fragments to save typing, ensure consistency and make changes easily
- Use environment variables as named constants
- Include header, footer and other common files into all your HTML files without server-side includes
- Include timestamps (in any format you like) to show the time of last process, or of last modification
- Use conditional commands to create different versions of the output under different circumstances
- Generate output to different directories to generate different versions of your site (for example, a frames version and a non-frames version)
- Change extensions of output files from `.html` to whatever you want, so that you may, for instance, use MultiViews options of Apache server, or create non-HTML files
- Guard special characters `<', `>`, and `&` in normal text so that they don't get confused with HTML commands
- Define your own characters translations, so that you may easily input your non-ASCII characters into GTML source
- Embed Perl or shell code into your source, so that you may easily generate pages with computed information
- Generate pages with all superfluous HTML code removed, so that readers retrieve them faster and may save bandwidth

See [REFERENCE.md](docs/REFERENCE.md) for a complete description of these features and how to use them.
