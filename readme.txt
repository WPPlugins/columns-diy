=== Columns DIY ===
Contributors: jupiterwise
Donate link: https://www.paypal.com/cgi-bin/webscr?cmd=_s-xclick&hosted_button_id=FC54RLA8U6VCC
Tags: shortcode, columns
Requires at least: 2.8
Tested up to: 3.9
Stable tag: 1_1
License: GPLv2

Simple shortcodes for div-based columns and rows. Wrap desired content in [column][/column]. Mark the end of a row with [endrow]. CSS not included.

== Description ==

This plugin is intended for theme developers and others who want to have full control of their column styles while still providing a quick and easy framework for adding/editing column content via WordPress's visual editor. It eliminates the need to type tedious, unmanageable chunks of HTML into the editor when specific posts or pages require a columnar layout.

That said, this plugin is not plug-and-play. It does not include any styles out-of-the-box, so if you start using the shortcodes without adding appropriate CSS rules, there probably won't be any visible changes to your content.

See the [Recipes](https://github.com/jupiterwise/Columns-DIY/wiki/Recipes) page on the GitHub wiki for some styling examples.

= Usage =

* Designate each column with `[column]` and `[/column]`
* Mark the end of a row with `[endrow]`

= Features =

* Includes enumerated column and row classes, allowing for per-column and -row styling. Also includes parity classes (odd/even) for striping.
* If a user forgets to add the last `[endrow]` shortcode, the plugin will automatically insert a closing `</div>` so the site layout doesn't get broken.
* Cleans up errant `<p>` and `<br />` tags that result from Wordpress's `wpautop()` function.
* All parameter inputs are escaped for security.

= Example =

Putting this into the visual editor:
> `[column]`
>
> This is the column of Foo.
>
> `[/column]`
>
> `[column]`
>
> This is the column of Bar.
>
> `[/column]` `[endrow]`

Will result in this output:
`<div class="diy-row diy-row-1 diy-row-odd">
<div class="diy-column diy-column-1 diy-column-odd">
<p>This is the column of Foo.</p>
</div><!-- end diy-column-1 -->

<div class="diy-column diy-column-2 diy-column-even">
<p>This is the column of Bar.</p>
</div><!-- end diy-column-2 -->
</div><!-- end diy-row-1 -->
`

= Parameters =

The following optional parameters can be added to the `[column]` shortcode:

* _class_ (String : '')
Classes for the column `<div>` element. Separate multiple classes with spaces.
* _rowclass_ (String : '')
Classes for the row `<div>` element. Only works when included with the first `[column]` shortcode in a row.
* _style_ (String : '')
Inline styles for the column `<div>` element.
* _rowstyle_ (String : '')
Inline styles for the row `<div>` element. Only works when included with the first `[column]` shortcode in a row.
* _norow_ (Boolean : false)
Set to true to omit the row wrapper `<div>`.

= Filters =

The following filter hooks can be used to alter the output of the shortcodes:

* `diy_colclass`
* `diy_colstyle`
* `diy_column`
* `diy_rowclass`
* `diy_rowstyle`
* `diy_beginrow`
* `diy_endrow`

== Installation ==

1. Upload the `columns-diy` folder to the `/wp-content/plugins/` directory
1. Activate the plugin through the 'Plugins' menu in WordPress

There are a few different options for adding the CSS to style your columns:

* Edit the style file in your theme (probably `style.css`). This is *not* recommended if you are using a third-party theme such as a commercial theme or one downloaded from the WordPress Theme Directory. Your changes will be lost if/when you update the theme to a new version.
* Create a [child theme](http://codex.wordpress.org/Child_Themes).
* Use a plugin such as [CSS & JavaScript Toolbox](http://wordpress.org/extend/plugins/css-javascript-toolbox/) to embed the styles without modifying your theme.
* Use the `style` parameter in the `[column]` shortcode to add inline styles. Only recommended for "one-off" scenarios (and how often does a "one-off" remain that way?).

== Frequently Asked Questions ==

Check out the [GitHub repository](https://github.com/jupiterwise/Columns-DIY) for more information.

== Changelog ==

= 1.1 =
* Added `rowstyle` parameter to allow for inline styles on the row `<div>`.
* Added filter hooks for altering the output of the shortcodes.
* Improved process for cleaning up `<p>` and `<br />` tags.

= 1.0 =
* The initial release to the WordPress plugin repository.

== Upgrade Notice ==
