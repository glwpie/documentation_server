01_Desktop<strong>”I Dunno” </strong> Will serve as a documentation repository for the IT Department.
[TOC]

## Features

### For Desktop Support 

* [Printers and WIFI](01_Desktop/Printers_and_WIFI.md)
* [Computer Reformat](01_Desktop/Computer_ReFormat.md)
* [Github Flavored Markdown](01_Desktop/GitHub_Flavored_Markdown.md)
* [Auto created homepage/landing page](01_Desktop/Landing_page.md)
* [Multiple Output Formats](01_Desktop/Multiple_Output_Formats.md)
* [Multiple Languages Support](01_Desktop/Multilanguage.md)
* [No Build Step](01_Desktop/Live_mode.md)
* [Static Output Generation](01_Desktop/Static_Site_Generation.md)
* [Table of Contents](01_Desktop/Table_of_contents.md)

### For Clinicals

* [Auto Syntax Highlighting](01_Desktop/Computer_ReFormat.md)
* [Extend Daux.io with Processors](01_For_Developers/Creating_a_Processor.md)
* Full access to the internal API to create new pages programatically
* Work with pages metadata

### For Everything Else (common Links)

* 100% Mobile Responsive
* 4 Built-In Themes or roll your own
* Functional, Flat Design Style
* Optional code float layout
* Shareable/Linkable SEO Friendly URLs
* Supports Google Analytics and Piwik Analytics

## Hot Links

This is a list of sites commonly accessed:

* [Spiceworks](http://s-4609pw1-spice:9675/pro_users/login#)
* [Citrix](https://www.asp.siemensmedical.com/isc/10152/Citrix/AccessPlatform/auth/login.aspx)
* [Healthstream](http://www.healthstream.com/hlc/whmc)
* [VMware Admin](https://vdiview1/admin/?userLoggedOut=true#/pool/ProdClinical)
* [FuseMail](https://mc.fusemail.com/)
* [Impravata](https://vdiimpva1.whphdom.local/sso/administrator.html)

Do you use **I Dunno**? Send us a pull request or open an [issue](https://github.com/glwpie/documentation_server/issues) and I can add some features. (Probably?)

## Getting Started


```
# Different Environments
[For Production] (https://stormy-cayman.herokuapp.com/). 
[For Staging]    (https://stormy-macan.herokuapp.com/).
	"This will always be freaky fresh"
```

You can then use the `daux` command line to generate your documentation.

If the command isn't found, ensure your `$PATH` contains `~/.composer/vendor/bin`

### Writing pages

Creating new pages is very easy:
1. Create a markdown file (`*.md` or `*.markdown`)
2. Start writing

By default, the generator will look for folders in the `docs` folder.
Add your folders inside the `docs` folder. This project contains some example folders and files to get you started.

You can nest folders any number of levels to get the exact structure you want.
The folder structure will be converted to the nested navigation.

You must use underscores instead of spaces. Here are some example file names and what they will be converted to:

**Good:**

* 01_Getting_Started.md = Getting Started
* API_Calls.md = API Calls
* 200_Something_Else-Cool.md = Something Else-Cool
* _5_Ways_to_Be_Happy.md = 5 Ways To Be Happy

**Bad:**

* File Name With Space.md = FAIL

### See your pages

Now you can see your pages. you have two options for that : serve them directly, or generate to various formats.

We recommend the first one while you write your documentation, you get a much quicker feedback while writing.

#### Serving files

You can use PHP's embedded web server by running the following command in the root of your documentation

```
./serve
```

Upload your files to an apache / nginx server and see your documentation

[More informations here](01_Desktop/Live_mode.md)

#### Export to other formats

Daux.io is extendable and comes by default with three export formats:

- Export to HTML, same as the website, but can be hosted without PHP.
- Export all documentation in a single HTML page
- Upload to your Atlassian Confluence server.

[See a detailed feature comparison matrix](01_Desktop/Multiple_Output_Formats.md)

To export, run the `daux` command and your documentation will be generated in `static` (you can change the destination with the `--destination` option)

[See here for all options](01_Desktop/Static_Site_Generation.md)

## Configuration

Now that you got the basics, you can also [see what you can configure](05_Configuration/_index.md)

## PHP Requirements

Daux.io is compatible with PHP 5.5 and up.

The reason is because some dependencies we have (mainly Symfony and Guzzle) do not support php 5.4 anymore.

### Extensions

PHP Needs the following extension to work : `php-mbstring` and `php-xml`.

If you encounter an error similar to `utf8_decode() not found` this means that you're missing the `php-xml` package. (We've seen it happen only on PHP 7)

## Known Issues

- __Windows UTF-8 files support__ Files with UTF-8 characters cannot be handled on windows, this issue has no known fix yet.


## Support

If you need help using Daux.io, or have found a bug, please create an issue on the <a href="https://github.com/justinwalsh/daux.io/issues" target="_blank">GitHub repo</a>.
