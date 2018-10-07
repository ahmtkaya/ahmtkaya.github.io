# ahmetkaya.github.io
Skip to content
 
Search or jump to…

Pull requests
Issues
Marketplace
Explore
 @ahmetkaya0107 Sign out
1
0 1 fsarigoz/fsarigoz.github.io
 Code  Issues 0  Pull requests 0  Projects 0  Wiki  Insights
fsarigoz.github.io/author/fatih-sarigoz.html
e48138d  on Jan 10, 2017
@fsarigoz fsarigoz Update documentation
     
Executable File  2900 lines (2823 sloc)  159 KB
<!DOCTYPE html>
<html lang="en">
<head>
        <meta charset="utf-8" />
        <title>Fatih Sarigoz - Fatih Sarigoz</title>
        <link rel="stylesheet" href="http://fatihsarigoz.com/theme/css/main.css" />
        <link href="http://fatihsarigoz.com/feeds/all.atom.xml" type="application/atom+xml" rel="alternate" title="Fatih Sarigoz Atom Feed" />

        <!--[if IE]>
            <script src="https://html5shiv.googlecode.com/svn/trunk/html5.js"></script>
        <![endif]-->
</head>

<body id="index" class="home">
<a href="http://github.com/fsarigoz">
<img style="position: absolute; top: 0; right: 0; border: 0;" src="https://s3.amazonaws.com/github/ribbons/forkme_right_red_aa0000.png" alt="Fork me on GitHub" />
</a>
        <header id="banner" class="body">
                <h1><a href="http://fatihsarigoz.com/">Fatih Sarigoz  <strong>Data Science Blog</strong></a></h1>
                <nav><ul>
                    <li><a href="/archives.html">Archives</a></li>
                    <li><a href="http://fatihsarigoz.com/category/about.html">About</a></li>
                    <li><a href="http://fatihsarigoz.com/category/posts.html">Posts</a></li>
                    <li><a href="http://fatihsarigoz.com/category/resume.html">Resume</a></li>
                </ul></nav>
        </header><!-- /#banner -->

            <aside id="featured" class="body">
                <article>
                    <h1 class="entry-title"><a href="http://fatihsarigoz.com/opti-ML.html">Optimization of ML Regression Models</a></h1>
<footer class="post-info">
        <abbr class="published" title="2017-01-03T23:50:00-08:00">
                Published: Tue 03 January 2017
        </abbr>

        <address class="vcard author">
                By                         <a class="url fn" href="http://fatihsarigoz.com/author/fatih-sarigoz.html">Fatih Sarigoz</a>
        </address>
<p>In <a href="http://fatihsarigoz.com/category/posts.html">Posts</a>.</p>
<p>tags: <a href="http://fatihsarigoz.com/tag/optimization-machine-learning-regression.html">optimization machine-learning regression</a> </p>
</footer><!-- /.post-info --><style type="text/css">/*!
*
* IPython notebook
*
*/
/* CSS font colors for translated ANSI colors. */
.ansibold {
  font-weight: bold;
}
/* use dark versions for foreground, to improve visibility */
.ansiblack {
  color: black;
}
.ansired {
  color: darkred;
}
.ansigreen {
  color: darkgreen;
}
.ansiyellow {
  color: #c4a000;
}
.ansiblue {
  color: darkblue;
}
.ansipurple {
  color: darkviolet;
}
.ansicyan {
  color: steelblue;
}
.ansigray {
  color: gray;
}
/* and light for background, for the same reason */
.ansibgblack {
  background-color: black;
}
.ansibgred {
  background-color: red;
}
.ansibggreen {
  background-color: green;
}
.ansibgyellow {
  background-color: yellow;
}
.ansibgblue {
  background-color: blue;
}
.ansibgpurple {
  background-color: magenta;
}
.ansibgcyan {
  background-color: cyan;
}
.ansibggray {
  background-color: gray;
}
div.cell {
  /* Old browsers */
  display: -webkit-box;
  -webkit-box-orient: vertical;
  -webkit-box-align: stretch;
  display: -moz-box;
  -moz-box-orient: vertical;
  -moz-box-align: stretch;
  display: box;
  box-orient: vertical;
  box-align: stretch;
  /* Modern browsers */
  display: flex;
  flex-direction: column;
  align-items: stretch;
  border-radius: 2px;
  box-sizing: border-box;
  -moz-box-sizing: border-box;
  -webkit-box-sizing: border-box;
  border-width: 1px;
  border-style: solid;
  border-color: transparent;
  width: 100%;
  padding: 5px;
  /* This acts as a spacer between cells, that is outside the border */
  margin: 0px;
  outline: none;
  border-left-width: 1px;
  padding-left: 5px;
  background: linear-gradient(to right, transparent -40px, transparent 1px, transparent 1px, transparent 100%);
}
div.cell.jupyter-soft-selected {
  border-left-color: #90CAF9;
  border-left-color: #E3F2FD;
  border-left-width: 1px;
  padding-left: 5px;
  border-right-color: #E3F2FD;
  border-right-width: 1px;
  background: #E3F2FD;
}
@media print {
  div.cell.jupyter-soft-selected {
    border-color: transparent;
  }
}
div.cell.selected {
  border-color: #ababab;
  border-left-width: 0px;
  padding-left: 6px;
  background: linear-gradient(to right, #42A5F5 -40px, #42A5F5 5px, transparent 5px, transparent 100%);
}
@media print {
  div.cell.selected {
    border-color: transparent;
  }
}
div.cell.selected.jupyter-soft-selected {
  border-left-width: 0;
  padding-left: 6px;
  background: linear-gradient(to right, #42A5F5 -40px, #42A5F5 7px, #E3F2FD 7px, #E3F2FD 100%);
}
.edit_mode div.cell.selected {
  border-color: #66BB6A;
  border-left-width: 0px;
  padding-left: 6px;
  background: linear-gradient(to right, #66BB6A -40px, #66BB6A 5px, transparent 5px, transparent 100%);
}
@media print {
  .edit_mode div.cell.selected {
    border-color: transparent;
  }
}
.prompt {
  /* This needs to be wide enough for 3 digit prompt numbers: In[100]: */
  min-width: 14ex;
  /* This padding is tuned to match the padding on the CodeMirror editor. */
  padding: 0.4em;
  margin: 0px;
  font-family: monospace;
  text-align: right;
  /* This has to match that of the the CodeMirror class line-height below */
  line-height: 1.21429em;
  /* Don't highlight prompt number selection */
  -webkit-touch-callout: none;
  -webkit-user-select: none;
  -khtml-user-select: none;
  -moz-user-select: none;
  -ms-user-select: none;
  user-select: none;
  /* Use default cursor */
  cursor: default;
}
@media (max-width: 540px) {
  .prompt {
    text-align: left;
  }
}
div.inner_cell {
  /* Old browsers */
  display: -webkit-box;
  -webkit-box-orient: vertical;
  -webkit-box-align: stretch;
  display: -moz-box;
  -moz-box-orient: vertical;
  -moz-box-align: stretch;
  display: box;
  box-orient: vertical;
  box-align: stretch;
  /* Modern browsers */
  display: flex;
  flex-direction: column;
  align-items: stretch;
  /* Old browsers */
  -webkit-box-flex: 1;
  -moz-box-flex: 1;
  box-flex: 1;
  /* Modern browsers */
  flex: 1;
}
@-moz-document url-prefix() {
  div.inner_cell {
    overflow-x: hidden;
  }
}
/* input_area and input_prompt must match in top border and margin for alignment */
div.input_area {
  border: 1px solid #cfcfcf;
  border-radius: 2px;
  background: #f7f7f7;
  line-height: 1.21429em;
}
/* This is needed so that empty prompt areas can collapse to zero height when there
   is no content in the output_subarea and the prompt. The main purpose of this is
   to make sure that empty JavaScript output_subareas have no height. */
div.prompt:empty {
  padding-top: 0;
  padding-bottom: 0;
}
div.unrecognized_cell {
  padding: 5px 5px 5px 0px;
  /* Old browsers */
  display: -webkit-box;
  -webkit-box-orient: horizontal;
  -webkit-box-align: stretch;
  display: -moz-box;
  -moz-box-orient: horizontal;
  -moz-box-align: stretch;
  display: box;
  box-orient: horizontal;
  box-align: stretch;
  /* Modern browsers */
  display: flex;
  flex-direction: row;
  align-items: stretch;
}
div.unrecognized_cell .inner_cell {
  border-radius: 2px;
  padding: 5px;
  font-weight: bold;
  color: red;
  border: 1px solid #cfcfcf;
  background: #eaeaea;
}
div.unrecognized_cell .inner_cell a {
  color: inherit;
  text-decoration: none;
}
div.unrecognized_cell .inner_cell a:hover {
  color: inherit;
  text-decoration: none;
}
@media (max-width: 540px) {
  div.unrecognized_cell > div.prompt {
    display: none;
  }
}
div.code_cell {
  /* avoid page breaking on code cells when printing */
}
@media print {
  div.code_cell {
    page-break-inside: avoid;
  }
}
/* any special styling for code cells that are currently running goes here */
div.input {
  page-break-inside: avoid;
  /* Old browsers */
  display: -webkit-box;
  -webkit-box-orient: horizontal;
  -webkit-box-align: stretch;
  display: -moz-box;
  -moz-box-orient: horizontal;
  -moz-box-align: stretch;
  display: box;
  box-orient: horizontal;
  box-align: stretch;
  /* Modern browsers */
  display: flex;
  flex-direction: row;
  align-items: stretch;
}
@media (max-width: 540px) {
  div.input {
    /* Old browsers */
    display: -webkit-box;
    -webkit-box-orient: vertical;
    -webkit-box-align: stretch;
    display: -moz-box;
    -moz-box-orient: vertical;
    -moz-box-align: stretch;
    display: box;
    box-orient: vertical;
    box-align: stretch;
    /* Modern browsers */
    display: flex;
    flex-direction: column;
    align-items: stretch;
  }
}
/* input_area and input_prompt must match in top border and margin for alignment */
div.input_prompt {
  color: #303F9F;
  border-top: 1px solid transparent;
}
div.input_area > div.highlight {
  margin: 0.4em;
  border: none;
  padding: 0px;
  background-color: transparent;
}
div.input_area > div.highlight > pre {
  margin: 0px;
  border: none;
  padding: 0px;
  background-color: transparent;
}
/* The following gets added to the <head> if it is detected that the user has a
 * monospace font with inconsistent normal/bold/italic height.  See
 * notebookmain.js.  Such fonts will have keywords vertically offset with
 * respect to the rest of the text.  The user should select a better font.
 * See: https://github.com/ipython/ipython/issues/1503
 *
 * .CodeMirror span {
 *      vertical-align: bottom;
 * }
 */
.CodeMirror {
  line-height: 1.21429em;
  /* Changed from 1em to our global default */
  font-size: 14px;
  height: auto;
  /* Changed to auto to autogrow */
  background: none;
  /* Changed from white to allow our bg to show through */
}
.CodeMirror-scroll {
  /*  The CodeMirror docs are a bit fuzzy on if overflow-y should be hidden or visible.*/
  /*  We have found that if it is visible, vertical scrollbars appear with font size changes.*/
  overflow-y: hidden;
  overflow-x: auto;
}
.CodeMirror-lines {
  /* In CM2, this used to be 0.4em, but in CM3 it went to 4px. We need the em value because */
  /* we have set a different line-height and want this to scale with that. */
  padding: 0.4em;
}
.CodeMirror-linenumber {
  padding: 0 8px 0 4px;
}
.CodeMirror-gutters {
  border-bottom-left-radius: 2px;
  border-top-left-radius: 2px;
}
.CodeMirror pre {
  /* In CM3 this went to 4px from 0 in CM2. We need the 0 value because of how we size */
  /* .CodeMirror-lines */
  padding: 0;
  border: 0;
  border-radius: 0;
}
/*
Original style from softwaremaniacs.org (c) Ivan Sagalaev <Maniac@SoftwareManiacs.Org>
Adapted from GitHub theme
*/
.highlight-base {
  color: #000;
}
.highlight-variable {
  color: #000;
}
.highlight-variable-2 {
  color: #1a1a1a;
}
.highlight-variable-3 {
  color: #333333;
}
.highlight-string {
  color: #BA2121;
}
.highlight-comment {
  color: #408080;
  font-style: italic;
}
.highlight-number {
  color: #080;
}
.highlight-atom {
  color: #88F;
}
.highlight-keyword {
  color: #008000;
  font-weight: bold;
}
.highlight-builtin {
  color: #008000;
}
.highlight-error {
  color: #f00;
}
.highlight-operator {
  color: #AA22FF;
  font-weight: bold;
}
.highlight-meta {
  color: #AA22FF;
}
/* previously not defined, copying from default codemirror */
.highlight-def {
  color: #00f;
}
.highlight-string-2 {
  color: #f50;
}
.highlight-qualifier {
  color: #555;
}
.highlight-bracket {
  color: #997;
}
.highlight-tag {
  color: #170;
}
.highlight-attribute {
  color: #00c;
}
.highlight-header {
  color: blue;
}
.highlight-quote {
  color: #090;
}
.highlight-link {
  color: #00c;
}
/* apply the same style to codemirror */
.cm-s-ipython span.cm-keyword {
  color: #008000;
  font-weight: bold;
}
.cm-s-ipython span.cm-atom {
  color: #88F;
}
.cm-s-ipython span.cm-number {
  color: #080;
}
.cm-s-ipython span.cm-def {
  color: #00f;
}
.cm-s-ipython span.cm-variable {
  color: #000;
}
.cm-s-ipython span.cm-operator {
  color: #AA22FF;
  font-weight: bold;
}
.cm-s-ipython span.cm-variable-2 {
  color: #1a1a1a;
}
.cm-s-ipython span.cm-variable-3 {
  color: #333333;
}
.cm-s-ipython span.cm-comment {
  color: #408080;
  font-style: italic;
}
.cm-s-ipython span.cm-string {
  color: #BA2121;
}
.cm-s-ipython span.cm-string-2 {
  color: #f50;
}
.cm-s-ipython span.cm-meta {
  color: #AA22FF;
}
.cm-s-ipython span.cm-qualifier {
  color: #555;
}
.cm-s-ipython span.cm-builtin {
  color: #008000;
}
.cm-s-ipython span.cm-bracket {
  color: #997;
}
.cm-s-ipython span.cm-tag {
  color: #170;
}
.cm-s-ipython span.cm-attribute {
  color: #00c;
}
.cm-s-ipython span.cm-header {
  color: blue;
}
.cm-s-ipython span.cm-quote {
  color: #090;
}
.cm-s-ipython span.cm-link {
  color: #00c;
}
.cm-s-ipython span.cm-error {
  color: #f00;
}
.cm-s-ipython span.cm-tab {
  background: url(data:image/png;base64,iVBORw0KGgoAAAANSUhEUgAAADAAAAAMCAYAAAAkuj5RAAAAAXNSR0IArs4c6QAAAGFJREFUSMft1LsRQFAQheHPowAKoACx3IgEKtaEHujDjORSgWTH/ZOdnZOcM/sgk/kFFWY0qV8foQwS4MKBCS3qR6ixBJvElOobYAtivseIE120FaowJPN75GMu8j/LfMwNjh4HUpwg4LUAAAAASUVORK5CYII=);
  background-position: right;
  background-repeat: no-repeat;
}
div.output_wrapper {
  /* this position must be relative to enable descendents to be absolute within it */
  position: relative;
  /* Old browsers */
  display: -webkit-box;
  -webkit-box-orient: vertical;
  -webkit-box-align: stretch;
  display: -moz-box;
  -moz-box-orient: vertical;
  -moz-box-align: stretch;
  display: box;
  box-orient: vertical;
  box-align: stretch;
  /* Modern browsers */
  display: flex;
  flex-direction: column;
  align-items: stretch;
  z-index: 1;
}
/* class for the output area when it should be height-limited */
div.output_scroll {
  /* ideally, this would be max-height, but FF barfs all over that */
  height: 24em;
  /* FF needs this *and the wrapper* to specify full width, or it will shrinkwrap */
  width: 100%;
  overflow: auto;
  border-radius: 2px;
  -webkit-box-shadow: inset 0 2px 8px rgba(0, 0, 0, 0.8);
  box-shadow: inset 0 2px 8px rgba(0, 0, 0, 0.8);
  display: block;
}
/* output div while it is collapsed */
div.output_collapsed {
  margin: 0px;
  padding: 0px;
  /* Old browsers */
  display: -webkit-box;
  -webkit-box-orient: vertical;
  -webkit-box-align: stretch;
  display: -moz-box;
  -moz-box-orient: vertical;
  -moz-box-align: stretch;
  display: box;
  box-orient: vertical;
  box-align: stretch;
  /* Modern browsers */
  display: flex;
  flex-direction: column;
  align-items: stretch;
}
div.out_prompt_overlay {
  height: 100%;
  padding: 0px 0.4em;
  position: absolute;
  border-radius: 2px;
}
div.out_prompt_overlay:hover {
  /* use inner shadow to get border that is computed the same on WebKit/FF */
  -webkit-box-shadow: inset 0 0 1px #000;
  box-shadow: inset 0 0 1px #000;
  background: rgba(240, 240, 240, 0.5);
}
div.output_prompt {
  color: #D84315;
}
/* This class is the outer container of all output sections. */
div.output_area {
  padding: 0px;
  page-break-inside: avoid;
  /* Old browsers */
  display: -webkit-box;
  -webkit-box-orient: horizontal;
  -webkit-box-align: stretch;
  display: -moz-box;
  -moz-box-orient: horizontal;
  -moz-box-align: stretch;
  display: box;
  box-orient: horizontal;
  box-align: stretch;
  /* Modern browsers */
  display: flex;
  flex-direction: row;
  align-items: stretch;
}
div.output_area .MathJax_Display {
  text-align: left !important;
}
div.output_area 
div.output_area 
div.output_area img,
div.output_area svg {
  max-width: 100%;
  height: auto;
}
div.output_area img.unconfined,
div.output_area svg.unconfined {
  max-width: none;
}
/* This is needed to protect the pre formating from global settings such
   as that of bootstrap */
.output {
  /* Old browsers */
  display: -webkit-box;
  -webkit-box-orient: vertical;
  -webkit-box-align: stretch;
  display: -moz-box;
  -moz-box-orient: vertical;
  -moz-box-align: stretch;
  display: box;
  box-orient: vertical;
  box-align: stretch;
  /* Modern browsers */
  display: flex;
  flex-direction: column;
  align-items: stretch;
}
@media (max-width: 540px) {
  div.output_area {
    /* Old browsers */
    display: -webkit-box;
    -webkit-box-orient: vertical;
    -webkit-box-align: stretch;
    display: -moz-box;
    -moz-box-orient: vertical;
    -moz-box-align: stretch;
    display: box;
    box-orient: vertical;
    box-align: stretch;
    /* Modern browsers */
    display: flex;
    flex-direction: column;
    align-items: stretch;
  }
}
div.output_area pre {
  margin: 0;
  padding: 0;
  border: 0;
  vertical-align: baseline;
  color: black;
  background-color: transparent;
  border-radius: 0;
}
/* This class is for the output subarea inside the output_area and after
   the prompt div. */
div.output_subarea {
  overflow-x: auto;
  padding: 0.4em;
  /* Old browsers */
  -webkit-box-flex: 1;
  -moz-box-flex: 1;
  box-flex: 1;
  /* Modern browsers */
  flex: 1;
  max-width: calc(100% - 14ex);
}
div.output_scroll div.output_subarea {
  overflow-x: visible;
}
/* The rest of the output_* classes are for special styling of the different
   output types */
/* all text output has this class: */
div.output_text {
  text-align: left;
  color: #000;
  /* This has to match that of the the CodeMirror class line-height below */
  line-height: 1.21429em;
}
/* stdout/stderr are 'text' as well as 'stream', but execute_result/error are *not* streams */
div.output_stderr {
  background: #fdd;
  /* very light red background for stderr */
}
div.output_latex {
  text-align: left;
}
/* Empty output_javascript divs should have no height */
div.output_javascript:empty {
  padding: 0;
}
.js-error {
  color: darkred;
}
/* raw_input styles */
div.raw_input_container {
  line-height: 1.21429em;
  padding-top: 5px;
}
pre.raw_input_prompt {
  /* nothing needed here. */
}
input.raw_input {
  font-family: monospace;
  font-size: inherit;
  color: inherit;
  width: auto;
  /* make sure input baseline aligns with prompt */
  vertical-align: baseline;
  /* padding + margin = 0.5em between prompt and cursor */
  padding: 0em 0.25em;
  margin: 0em 0.25em;
}
input.raw_input:focus {
  box-shadow: none;
}
p.p-space {
  margin-bottom: 10px;
}
div.output_unrecognized {
  padding: 5px;
  font-weight: bold;
  color: red;
}
div.output_unrecognized a {
  color: inherit;
  text-decoration: none;
}
div.output_unrecognized a:hover {
  color: inherit;
  text-decoration: none;
}
.rendered_html {
  color: #000;
  /* any extras will just be numbers: */
}
.rendered_html :link {
  text-decoration: underline;
}
.rendered_html :visited {
  text-decoration: underline;
}
.rendered_html h1:first-child {
  margin-top: 0.538em;
}
.rendered_html h2:first-child {
  margin-top: 0.636em;
}
.rendered_html h3:first-child {
  margin-top: 0.777em;
}
.rendered_html h4:first-child {
  margin-top: 1em;
}
.rendered_html h5:first-child {
  margin-top: 1em;
}
.rendered_html h6:first-child {
  margin-top: 1em;
}
.rendered_html * + ul {
  margin-top: 1em;
}
.rendered_html * + ol {
  margin-top: 1em;
}
.rendered_html pre,
.rendered_html tr,
.rendered_html th,
.rendered_html td,
.rendered_html * + table {
  margin-top: 1em;
}
.rendered_html * + p {
  margin-top: 1em;
}
.rendered_html * + img {
  margin-top: 1em;
}
.rendered_html img,
.rendered_html img.unconfined,
div.text_cell {
  /* Old browsers */
  display: -webkit-box;
  -webkit-box-orient: horizontal;
  -webkit-box-align: stretch;
  display: -moz-box;
  -moz-box-orient: horizontal;
  -moz-box-align: stretch;
  display: box;
  box-orient: horizontal;
  box-align: stretch;
  /* Modern browsers */
  display: flex;
  flex-direction: row;
  align-items: stretch;
}
@media (max-width: 540px) {
  div.text_cell > div.prompt {
    display: none;
  }
}
div.text_cell_render {
  /*font-family: "Helvetica Neue", Arial, Helvetica, Geneva, sans-serif;*/
  outline: none;
  resize: none;
  width: inherit;
  border-style: none;
  padding: 0.5em 0.5em 0.5em 0.4em;
  color: #000;
  box-sizing: border-box;
  -moz-box-sizing: border-box;
  -webkit-box-sizing: border-box;
}
a.anchor-link:link {
  text-decoration: none;
  padding: 0px 20px;
  visibility: hidden;
}
h1:hover .anchor-link,
h2:hover .anchor-link,
h3:hover .anchor-link,
h4:hover .anchor-link,
h5:hover .anchor-link,
h6:hover .anchor-link {
  visibility: visible;
}
.text_cell.rendered .input_area {
  display: none;
}
.text_cell.rendered 
.text_cell.unrendered .text_cell_render {
  display: none;
}
.cm-header-1,
.cm-header-2,
.cm-header-3,
.cm-header-4,
.cm-header-5,
.cm-header-6 {
  font-weight: bold;
  font-family: "Helvetica Neue", Helvetica, Arial, sans-serif;
}
.cm-header-1 {
  font-size: 185.7%;
}
.cm-header-2 {
  font-size: 157.1%;
}
.cm-header-3 {
  font-size: 128.6%;
}
.cm-header-4 {
  font-size: 110%;
}
.cm-header-5 {
  font-size: 100%;
  font-style: italic;
}
.cm-header-6 {
  font-size: 100%;
  font-style: italic;
}
</style>
<style type="text/css">.highlight .hll { background-color: #ffffcc }
.highlight  { background: #f8f8f8; }
.highlight .c { color: #408080; font-style: italic } /* Comment */
.highlight .err { border: 1px solid #FF0000 } /* Error */
.highlight .k { color: #008000; font-weight: bold } /* Keyword */
.highlight .o { color: #666666 } /* Operator */
.highlight .ch { color: #408080; font-style: italic } /* Comment.Hashbang */
.highlight .cm { color: #408080; font-style: italic } /* Comment.Multiline */
.highlight .cp { color: #BC7A00 } /* Comment.Preproc */
.highlight .cpf { color: #408080; font-style: italic } /* Comment.PreprocFile */
.highlight .c1 { color: #408080; font-style: italic } /* Comment.Single */
.highlight .cs { color: #408080; font-style: italic } /* Comment.Special */
.highlight .gd { color: #A00000 } /* Generic.Deleted */
.highlight .ge { font-style: italic } /* Generic.Emph */
.highlight .gr { color: #FF0000 } /* Generic.Error */
.highlight .gh { color: #000080; font-weight: bold } /* Generic.Heading */
.highlight .gi { color: #00A000 } /* Generic.Inserted */
.highlight .go { color: #888888 } /* Generic.Output */
.highlight .gp { color: #000080; font-weight: bold } /* Generic.Prompt */
.highlight .gs { font-weight: bold } /* Generic.Strong */
.highlight .gu { color: #800080; font-weight: bold } /* Generic.Subheading */
.highlight .gt { color: #0044DD } /* Generic.Traceback */
.highlight .kc { color: #008000; font-weight: bold } /* Keyword.Constant */
.highlight .kd { color: #008000; font-weight: bold } /* Keyword.Declaration */
.highlight .kn { color: #008000; font-weight: bold } /* Keyword.Namespace */
.highlight .kp { color: #008000 } /* Keyword.Pseudo */
.highlight .kr { color: #008000; font-weight: bold } /* Keyword.Reserved */
.highlight .kt { color: #B00040 } /* Keyword.Type */
.highlight .m { color: #666666 } /* Literal.Number */
.highlight .s { color: #BA2121 } /* Literal.String */
.highlight .na { color: #7D9029 } /* Name.Attribute */
.highlight .nb { color: #008000 } /* Name.Builtin */
.highlight .nc { color: #0000FF; font-weight: bold } /* Name.Class */
.highlight .no { color: #880000 } /* Name.Constant */
.highlight .nd { color: #AA22FF } /* Name.Decorator */
.highlight .ni { color: #999999; font-weight: bold } /* Name.Entity */
.highlight .ne { color: #D2413A; font-weight: bold } /* Name.Exception */
.highlight .nf { color: #0000FF } /* Name.Function */
.highlight .nl { color: #A0A000 } /* Name.Label */
.highlight .nn { color: #0000FF; font-weight: bold } /* Name.Namespace */
.highlight .nt { color: #008000; font-weight: bold } /* Name.Tag */
.highlight .nv { color: #19177C } /* Name.Variable */
.highlight .ow { color: #AA22FF; font-weight: bold } /* Operator.Word */
.highlight .w { color: #bbbbbb } /* Text.Whitespace */
.highlight .mb { color: #666666 } /* Literal.Number.Bin */
.highlight .mf { color: #666666 } /* Literal.Number.Float */
.highlight .mh { color: #666666 } /* Literal.Number.Hex */
.highlight .mi { color: #666666 } /* Literal.Number.Integer */
.highlight .mo { color: #666666 } /* Literal.Number.Oct */
.highlight .sb { color: #BA2121 } /* Literal.String.Backtick */
.highlight .sc { color: #BA2121 } /* Literal.String.Char */
.highlight .sd { color: #BA2121; font-style: italic } /* Literal.String.Doc */
.highlight .s2 { color: #BA2121 } /* Literal.String.Double */
.highlight .se { color: #BB6622; font-weight: bold } /* Literal.String.Escape */
.highlight .sh { color: #BA2121 } /* Literal.String.Heredoc */
.highlight .si { color: #BB6688; font-weight: bold } /* Literal.String.Interpol */
.highlight .sx { color: #008000 } /* Literal.String.Other */
.highlight .sr { color: #BB6688 } /* Literal.String.Regex */
.highlight .s1 { color: #BA2121 } /* Literal.String.Single */
.highlight .ss { color: #19177C } /* Literal.String.Symbol */
.highlight .bp { color: #008000 } /* Name.Builtin.Pseudo */
.highlight .vc { color: #19177C } /* Name.Variable.Class */
.highlight .vg { color: #19177C } /* Name.Variable.Global */
.highlight .vi { color: #19177C } /* Name.Variable.Instance */
.highlight .il { color: #666666 } /* Literal.Number.Integer.Long */</style>
<style type="text/css">
/* Temporary definitions which will become obsolete with Notebook release 5.0 */
.ansi-black-fg { color: #3E424D; }
.ansi-black-bg { background-color: #3E424D; }
.ansi-black-intense-fg { color: #282C36; }
.ansi-black-intense-bg { background-color: #282C36; }
.ansi-red-fg { color: #E75C58; }
.ansi-red-bg { background-color: #E75C58; }
.ansi-red-intense-fg { color: #B22B31; }
.ansi-red-intense-bg { background-color: #B22B31; }
.ansi-green-fg { color: #00A250; }
.ansi-green-bg { background-color: #00A250; }
.ansi-green-intense-fg { color: #007427; }
.ansi-green-intense-bg { background-color: #007427; }
.ansi-yellow-fg { color: #DDB62B; }
.ansi-yellow-bg { background-color: #DDB62B; }
.ansi-yellow-intense-fg { color: #B27D12; }
.ansi-yellow-intense-bg { background-color: #B27D12; }
.ansi-blue-fg { color: #208FFB; }
.ansi-blue-bg { background-color: #208FFB; }
.ansi-blue-intense-fg { color: #0065CA; }
.ansi-blue-intense-bg { background-color: #0065CA; }
.ansi-magenta-fg { color: #D160C4; }
.ansi-magenta-bg { background-color: #D160C4; }
.ansi-magenta-intense-fg { color: #A03196; }
.ansi-magenta-intense-bg { background-color: #A03196; }
.ansi-cyan-fg { color: #60C6C8; }
.ansi-cyan-bg { background-color: #60C6C8; }
.ansi-cyan-intense-fg { color: #258F8F; }
.ansi-cyan-intense-bg { background-color: #258F8F; }
.ansi-white-fg { color: #C5C1B4; }
.ansi-white-bg { background-color: #C5C1B4; }
.ansi-white-intense-fg { color: #A1A6B2; }
.ansi-white-intense-bg { background-color: #A1A6B2; }
.ansi-bold { font-weight: bold; }
</style>
<div class="cell border-box-sizing text_cell rendered">
<div class="prompt input_prompt">
</div>
<div class="inner_cell">
<div class="text_cell_render border-box-sizing rendered_html">
<h1 id="Optimization-of-ML-Regression-Models">Optimization of ML Regression Models<a class="anchor-link" href="#Optimization-of-ML-Regression-Models">¶</a></h1><p>In this project, we will compare the performance of different machine learning regression models on the Auto-MPG data set. In addition, we will look into how to optimize each model for best performance.</p>
<p>The <code>PipeLine</code> and <code>GridSearch</code> tools from the Scikit-Learn library will be utilized.</p>
<p>The following regression models will be studied:</p>
<ul>
<li>Linear Models: <code>LinearRegression</code>, <code>Ridge</code>, <code>Lasso</code> and <code>ElasticNet</code></li>
<li>K-nearest Neighbor Regression: <code>KNeighborsRegressor</code></li>
<li>Support Vector Regression: <code>SVR</code> with <code>linear</code>, <code>poly</code>, <code>sigmoid</code> and <code>rbf</code> kernels</li>
<li>Decision Tree Regression: <code>DecisionTreeRegressor</code> and <code>ExtraTreeRegressor</code></li>
<li>Bagging Algorithms: <code>BaggingRegressor</code>, <code>RandomForestRegressor</code> and <code>ExtraTreesRegressor</code></li>
<li>Boosting Algorithms: <code>AdaBoostRegressor</code> and <code>GradientBoostingRegressor</code></li>
</ul>
<p>For this project we will use the <a href="https://archive.ics.uci.edu/ml/datasets/Auto+MPG"><code>Auto MPG</code></a> data set. Please follow the instructions in the post <a href="./autompg-data.html"><code>Working with the Auto MPG Data Set</code></a> to get yourself familiar with the dataset, prepare the data for analysis and generate the <code>auto-mpg.csv</code> that will be used in this project.</p>
</div>
</div>
</div>
<div class="cell border-box-sizing text_cell rendered">
<div class="prompt input_prompt">
</div>
<div class="inner_cell">
<div class="text_cell_render border-box-sizing rendered_html">
<hr>
<h2 id="1.-Loading-and-Preparing-the-Data">1. Loading and Preparing the Data<a class="anchor-link" href="#1.-Loading-and-Preparing-the-Data">¶</a></h2>
</hr></div>
</div>
</div>
<div class="cell border-box-sizing text_cell rendered">
<div class="prompt input_prompt">
</div>
<div class="inner_cell">
<div class="text_cell_render border-box-sizing rendered_html">
<p>Sections 1 in the previous post titled <a href="./scaling-ML"><code>Impact of Scaling on Machine Learning Algorithms</code></a> go over the scaling differences in the data in detail.</p>
<p>Below, the code that separates the data into inputs, <code>X</code> and output, <code>y</code> is provided.</p>
</div>
</div>
</div>
<div class="cell border-box-sizing code_cell rendered">
<div class="input">
<div class="prompt input_prompt">In [3]:</div>
<div class="inner_cell">
<div class="input_area">
<div class=" highlight hl-ipython2"><pre><span></span><span class="kn">import</span> <span class="nn">pandas</span> <span class="kn">as</span> <span class="nn">pd</span>
<span class="kn">import</span> <span class="nn">numpy</span> <span class="kn">as</span> <span class="nn">np</span>

<span class="n">filename</span> <span class="o">=</span> <span class="s2">"auto-mpg.csv"</span>
<span class="n">df</span> <span class="o">=</span> <span class="n">pd</span><span class="o">.</span><span class="n">read_csv</span><span class="p">(</span><span class="n">filename</span><span class="p">)</span>
<span class="n">output</span> <span class="o">=</span> <span class="n">df</span><span class="o">.</span><span class="n">iloc</span><span class="p">[:,</span><span class="mi">0</span><span class="p">]</span>
<span class="n">features</span> <span class="o">=</span> <span class="n">df</span><span class="o">.</span><span class="n">iloc</span><span class="p">[:,</span> <span class="mi">1</span><span class="p">:</span><span class="mi">8</span><span class="p">]</span>
<span class="n">X</span> <span class="o">=</span> <span class="n">features</span><span class="o">.</span><span class="n">values</span>
<span class="n">y</span> <span class="o">=</span> <span class="n">output</span><span class="o">.</span><span class="n">values</span>
<span class="n">df</span><span class="o">.</span><span class="n">head</span><span class="p">(</span><span class="mi">3</span><span class="p">)</span>
</pre></div>
</div>
</div>
</div>
<div class="output_wrapper">
<div class="output">
<div class="output_area"><div class="prompt output_prompt">Out[3]:</div>
<div class="output_html rendered_html output_subarea output_execute_result">
<div>
<table border="1" class="table table-hover table-striped dataframe">
<thead>
<tr style="text-align: right;">
<th></th>
<th>mpg</th>
<th>cylinders</th>
<th>displacement</th>
<th>horsepower</th>
<th>weight</th>
<th>acceleration</th>
<th>year</th>
<th>origin</th>
<th>name</th>
</tr>
</thead>
<tbody>
<tr>
<th>0</th>
<td>18.0</td>
<td>8</td>
<td>307.0</td>
<td>130.0</td>
<td>3504.0</td>
<td>12.0</td>
<td>70</td>
<td>1</td>
<td>chevrolet chevelle malibu</td>
</tr>
<tr>
<th>1</th>
<td>15.0</td>
<td>8</td>
<td>350.0</td>
<td>165.0</td>
<td>3693.0</td>
<td>11.5</td>
<td>70</td>
<td>1</td>
<td>buick skylark 320</td>
</tr>
<tr>
<th>2</th>
<td>18.0</td>
<td>8</td>
<td>318.0</td>
<td>150.0</td>
<td>3436.0</td>
<td>11.0</td>
<td>70</td>
<td>1</td>
<td>plymouth satellite</td>
</tr>
</tbody>
</table>
</div>
</div>
</div>
</div>
</div>
</div>
<div class="cell border-box-sizing text_cell rendered">
<div class="prompt input_prompt">
</div>
<div class="inner_cell">
<div class="text_cell_render border-box-sizing rendered_html">
<p>The y variable holds the mpg column data and the X variable holds the data in the cylinders, displacement, horsepower, weight, acceleration, year and origin columns (the name column is not used in this project).</p>
</div>
</div>
</div>
<div class="cell border-box-sizing text_cell rendered">
<div class="prompt input_prompt">
</div>
<div class="inner_cell">
<div class="text_cell_render border-box-sizing rendered_html">
<hr>
<h2 id="2.-Test-and-Display-Functions">2. Test and Display Functions<a class="anchor-link" href="#2.-Test-and-Display-Functions">¶</a></h2>
</hr></div>
</div>
</div>
<div class="cell border-box-sizing text_cell rendered">
<div class="prompt input_prompt">
</div>
<div class="inner_cell">
<div class="text_cell_render border-box-sizing rendered_html">
<p>The following funtions will be used in the remaining parts of this post.</p>
</div>
</div>
</div>
<div class="cell border-box-sizing code_cell rendered">
<div class="input">
<div class="prompt input_prompt">In [4]:</div>
<div class="inner_cell">
<div class="input_area">
<div class=" highlight hl-ipython2"><pre><span></span><span class="k">def</span> <span class="nf">get_modelname</span><span class="p">(</span><span class="n">model</span><span class="p">):</span>
    <span class="n">name</span> <span class="o">=</span> <span class="nb">str</span><span class="p">(</span><span class="n">model</span><span class="p">)</span><span class="o">.</span><span class="n">partition</span><span class="p">(</span><span class="s1">'('</span><span class="p">)[</span><span class="mi">0</span><span class="p">]</span>
    <span class="k">if</span> <span class="n">name</span><span class="o">==</span><span class="s1">'SVR'</span><span class="p">:</span>
        <span class="n">name</span> <span class="o">=</span> <span class="n">model</span><span class="o">.</span><span class="n">get_params</span><span class="p">()[</span><span class="s1">'kernel'</span><span class="p">]</span> <span class="o">+</span> <span class="n">name</span>
    <span class="k">return</span><span class="p">(</span><span class="n">name</span><span class="p">)</span>
</pre></div>
</div>
</div>
</div>
</div>
<div class="cell border-box-sizing text_cell rendered">
<div class="prompt input_prompt">
</div>
<div class="inner_cell">
<div class="text_cell_render border-box-sizing rendered_html">
<p><code>get_modelname</code> extracts the name of the model from the model function call. For support vector regression, the kernel name is also prepended to the model name.</p>
</div>
</div>
</div>
<div class="cell border-box-sizing code_cell rendered">
<div class="input">
<div class="prompt input_prompt">In [5]:</div>
<div class="inner_cell">
<div class="input_area">
<div class=" highlight hl-ipython2"><pre><span></span><span class="k">def</span> <span class="nf">evalModels</span><span class="p">(</span><span class="n">models</span><span class="p">,</span> <span class="n">Xw</span><span class="p">,</span> <span class="n">y</span><span class="p">,</span> <span class="n">boxPlotOn</span><span class="o">=</span><span class="bp">True</span><span class="p">):</span>
    <span class="kn">from</span> <span class="nn">sklearn.preprocessing</span> <span class="kn">import</span> <span class="n">StandardScaler</span> <span class="c1"># Standardize data (0 mean, 1 stdev)</span>
    <span class="kn">from</span> <span class="nn">sklearn.model_selection</span> <span class="kn">import</span> <span class="n">KFold</span>
    <span class="kn">from</span> <span class="nn">sklearn.model_selection</span> <span class="kn">import</span> <span class="n">cross_val_score</span>
    <span class="kn">from</span> <span class="nn">sklearn.pipeline</span> <span class="kn">import</span> <span class="n">Pipeline</span><span class="p">,</span> <span class="n">make_pipeline</span>

    <span class="n">scoring</span> <span class="o">=</span> <span class="s1">'r2'</span>  <span class="c1">#'neg_mean_squared_error'</span>
    <span class="n">modelnames</span> <span class="o">=</span> <span class="p">[]</span>
    <span class="n">results</span> <span class="o">=</span> <span class="p">[]</span>
    <span class="k">for</span> <span class="n">model</span> <span class="ow">in</span> <span class="n">models</span><span class="p">:</span>
        <span class="n">pipe</span> <span class="o">=</span> <span class="n">make_pipeline</span><span class="p">(</span> <span class="n">StandardScaler</span><span class="p">(),</span> <span class="n">model</span> <span class="p">)</span>
        <span class="n">kfold</span> <span class="o">=</span> <span class="n">KFold</span><span class="p">(</span><span class="n">n_splits</span><span class="o">=</span><span class="mi">8</span><span class="p">,</span> <span class="n">random_state</span><span class="o">=</span><span class="mi">6</span><span class="p">,</span> <span class="n">shuffle</span><span class="o">=</span><span class="bp">True</span><span class="p">)</span>
        <span class="n">cv_results</span> <span class="o">=</span> <span class="n">cross_val_score</span><span class="p">(</span><span class="n">pipe</span><span class="p">,</span> <span class="n">Xw</span><span class="p">,</span> <span class="n">y</span><span class="p">,</span> <span class="n">cv</span><span class="o">=</span><span class="n">kfold</span><span class="p">,</span> <span class="n">scoring</span><span class="o">=</span><span class="n">scoring</span><span class="p">)</span>
        <span class="n">modelname</span> <span class="o">=</span> <span class="n">get_modelname</span><span class="p">(</span><span class="n">model</span><span class="p">)</span>
        <span class="k">print</span> <span class="s2">"</span><span class="si">%s</span><span class="s2">: </span><span class="si">%.3f</span><span class="s2"> </span><span class="si">%.3f</span><span class="s2">"</span> <span class="o">%</span><span class="p">(</span><span class="n">modelname</span><span class="p">,</span> <span class="n">cv_results</span><span class="o">.</span><span class="n">mean</span><span class="p">(),</span> <span class="n">cv_results</span><span class="o">.</span><span class="n">std</span><span class="p">())</span>
        <span class="n">modelnames</span><span class="o">.</span><span class="n">append</span><span class="p">(</span><span class="n">modelname</span><span class="p">)</span>
        <span class="n">results</span><span class="o">.</span><span class="n">append</span><span class="p">(</span><span class="n">cv_results</span><span class="p">)</span>
    
    <span class="k">if</span> <span class="n">boxPlotOn</span><span class="p">:</span>
        <span class="kn">import</span> <span class="nn">matplotlib.pyplot</span> <span class="kn">as</span> <span class="nn">plt</span>
        <span class="c1"># boxplot algorithm comparison</span>
        <span class="n">fig</span> <span class="o">=</span> <span class="n">plt</span><span class="o">.</span><span class="n">figure</span><span class="p">()</span>
        <span class="n">fig</span><span class="o">.</span><span class="n">suptitle</span><span class="p">(</span><span class="s1">'Algorithm Comparison'</span><span class="p">)</span>
        <span class="n">ax</span> <span class="o">=</span> <span class="n">fig</span><span class="o">.</span><span class="n">add_subplot</span><span class="p">(</span><span class="mi">111</span><span class="p">)</span>
        <span class="n">plt</span><span class="o">.</span><span class="n">boxplot</span><span class="p">(</span><span class="n">results</span><span class="p">,</span> <span class="n">showmeans</span><span class="o">=</span><span class="bp">True</span><span class="p">)</span>
        <span class="n">ax</span><span class="o">.</span><span class="n">set_xticklabels</span><span class="p">(</span><span class="n">modelnames</span><span class="p">,</span> <span class="n">fontsize</span><span class="o">=</span><span class="mi">9</span><span class="p">)</span>
        <span class="n">plt</span><span class="o">.</span><span class="n">ylim</span><span class="p">(</span><span class="mf">0.7</span><span class="p">,</span> <span class="mf">0.95</span><span class="p">)</span>
        <span class="n">plt</span><span class="o">.</span><span class="n">show</span><span class="p">()</span>
    
    <span class="k">return</span><span class="p">(</span><span class="n">results</span><span class="p">)</span>
</pre></div>
</div>
</div>
</div>
</div>
<div class="cell border-box-sizing text_cell rendered">
<div class="prompt input_prompt">
</div>
<div class="inner_cell">
<div class="text_cell_render border-box-sizing rendered_html">
<p>The <code>evalModels</code> function includes the following:</p>
<ul>
<li>A <code>pipeline</code> that includes standardization of the input vectors (so that variance is 1 and mean is zero) and application of the ML model. </li>
<li>8-split, shuffled cross-validation</li>
<li>Box plotting all the performance results</li>
</ul>
</div>
</div>
</div>
<div class="cell border-box-sizing text_cell rendered">
<div class="prompt input_prompt">
</div>
<div class="inner_cell">
<div class="text_cell_render border-box-sizing rendered_html">
<hr>
<h2 id="3.-Pipelining-transformers-and-predictors">3. Pipelining transformers and predictors<a class="anchor-link" href="#3.-Pipelining-transformers-and-predictors">¶</a></h2>
</hr></div>
</div>
</div>
<div class="cell border-box-sizing text_cell rendered">
<div class="prompt input_prompt">
</div>
<div class="inner_cell">
<div class="text_cell_render border-box-sizing rendered_html">
<p>It is important to extract tranformation parameters (such as scaling) from only the training data and keep the testing data untouched in this regard. The most convenient way to accomplish this by using the pipelining feature in scikit-learn.</p>
<p>The following example from the scikit-learn website shows how to achieve this without pipelining:</p>
</div>
</div>
</div>
<div class="cell border-box-sizing code_cell rendered">
<div class="input">
<div class="prompt input_prompt">In [ ]:</div>
<div class="inner_cell">
<div class="input_area">
<div class=" highlight hl-ipython2"><pre><span></span><span class="kn">from</span> <span class="nn">sklearn</span> <span class="kn">import</span> <span class="n">preprocessing</span>

<span class="n">X_train</span><span class="p">,</span> <span class="n">X_test</span><span class="p">,</span> <span class="n">y_train</span><span class="p">,</span> <span class="n">y_test</span> <span class="o">=</span> <span class="n">train_test_split</span><span class="p">(</span>
    <span class="n">iris</span><span class="o">.</span><span class="n">data</span><span class="p">,</span> <span class="n">iris</span><span class="o">.</span><span class="n">target</span><span class="p">,</span> <span class="n">test_size</span><span class="o">=</span><span class="mf">0.4</span><span class="p">,</span> <span class="n">random_state</span><span class="o">=</span><span class="mi">0</span><span class="p">)</span>
<span class="n">scaler</span> <span class="o">=</span> <span class="n">preprocessing</span><span class="o">.</span><span class="n">StandardScaler</span><span class="p">()</span><span class="o">.</span><span class="n">fit</span><span class="p">(</span><span class="n">X_train</span><span class="p">)</span>
<span class="n">X_train_transformed</span> <span class="o">=</span> <span class="n">scaler</span><span class="o">.</span><span class="n">transform</span><span class="p">(</span><span class="n">X_train</span><span class="p">)</span>
<span class="n">clf</span> <span class="o">=</span> <span class="n">svm</span><span class="o">.</span><span class="n">SVC</span><span class="p">(</span><span class="n">C</span><span class="o">=</span><span class="mi">1</span><span class="p">)</span><span class="o">.</span><span class="n">fit</span><span class="p">(</span><span class="n">X_train_transformed</span><span class="p">,</span> <span class="n">y_train</span><span class="p">)</span>
<span class="n">X_test_transformed</span> <span class="o">=</span> <span class="n">scaler</span><span class="o">.</span><span class="n">transform</span><span class="p">(</span><span class="n">X_test</span><span class="p">)</span>
<span class="n">clf</span><span class="o">.</span><span class="n">score</span><span class="p">(</span><span class="n">X_test_transformed</span><span class="p">,</span> <span class="n">y_test</span><span class="p">)</span>  
</pre></div>
</div>
</div>
</div>
</div>
<div class="cell border-box-sizing text_cell rendered">
<div class="prompt input_prompt">
</div>
<div class="inner_cell">
<div class="text_cell_render border-box-sizing rendered_html">
<p>The following sample code using a pipeline, however, is much simpler, allows treating the pipeline as a model so that multi-split cross validation can be applied easily:</p>
</div>
</div>
</div>
<div class="cell border-box-sizing code_cell rendered">
<div class="input">
<div class="prompt input_prompt">In [ ]:</div>
<div class="inner_cell">
<div class="input_area">
<div class=" highlight hl-ipython2"><pre><span></span><span class="kn">from</span> <span class="nn">sklearn.pipeline</span> <span class="kn">import</span> <span class="n">make_pipeline</span>
<span class="n">clf</span> <span class="o">=</span> <span class="n">make_pipeline</span><span class="p">(</span><span class="n">preprocessing</span><span class="o">.</span><span class="n">StandardScaler</span><span class="p">(),</span> <span class="n">svm</span><span class="o">.</span><span class="n">SVC</span><span class="p">(</span><span class="n">C</span><span class="o">=</span><span class="mi">1</span><span class="p">))</span>
<span class="n">cross_val_score</span><span class="p">(</span><span class="n">clf</span><span class="p">,</span> <span class="n">iris</span><span class="o">.</span><span class="n">data</span><span class="p">,</span> <span class="n">iris</span><span class="o">.</span><span class="n">target</span><span class="p">,</span> <span class="n">cv</span><span class="o">=</span><span class="n">cv</span><span class="p">)</span>               
</pre></div>
</div>
</div>
</div>
</div>
<div class="cell border-box-sizing text_cell rendered">
<div class="prompt input_prompt">
</div>
<div class="inner_cell">
<div class="text_cell_render border-box-sizing rendered_html">
<p>In this project, all performance simulations are run using a pipeline formed by calling the function <code>evalModels</code> above.</p>
</div>
</div>
</div>
<div class="cell border-box-sizing text_cell rendered">
<div class="prompt input_prompt">
</div>
<div class="inner_cell">
<div class="text_cell_render border-box-sizing rendered_html">
<hr>
<h2 id="4.-Comparison-of-ML-regression-models">4. Comparison of ML regression models<a class="anchor-link" href="#4.-Comparison-of-ML-regression-models">¶</a></h2>
</hr></div>
</div>
</div>
<div class="cell border-box-sizing text_cell rendered">
<div class="prompt input_prompt">
</div>
<div class="inner_cell">
<div class="text_cell_render border-box-sizing rendered_html">
<p>In this section we run all regression models using 8-split cross-validation and compare the R² results.</p>
<p>All regressors have been manually optimized. In other words, a manual search has been conducted in the parameter space of each regressor for the best performing parameter set which was then used to call each model. The default setting is kept for those parameters that did not make any noticeable difference.</p>
<p>All input data has been standardized on the training data set.</p>
</div>
</div>
</div>
<div class="cell border-box-sizing text_cell rendered">
<div class="prompt input_prompt">
</div>
<div class="inner_cell">
<div class="text_cell_render border-box-sizing rendered_html">
<h3 id="4.1-Linear-Regression">4.1 Linear Regression<a class="anchor-link" href="#4.1-Linear-Regression">¶</a></h3>
</div>
</div>
</div>
<div class="cell border-box-sizing code_cell rendered">
<div class="input">
<div class="prompt input_prompt">In [6]:</div>
<div class="inner_cell">
<div class="input_area">
<div class=" highlight hl-ipython2"><pre><span></span><span class="kn">from</span> <span class="nn">sklearn.linear_model</span> <span class="kn">import</span> <span class="n">LinearRegression</span><span class="p">,</span> <span class="n">Ridge</span><span class="p">,</span> <span class="n">Lasso</span><span class="p">,</span> <span class="n">ElasticNet</span>

<span class="c1"># create and evaluate pipeline</span>
<span class="n">models</span> <span class="o">=</span> <span class="p">[]</span>
<span class="n">models</span><span class="o">.</span><span class="n">append</span><span class="p">(</span> <span class="n">LinearRegression</span><span class="p">()</span> <span class="p">)</span>
<span class="n">models</span><span class="o">.</span><span class="n">append</span><span class="p">(</span> <span class="n">Ridge</span><span class="p">(</span><span class="n">alpha</span><span class="o">=</span><span class="mf">1.0</span><span class="p">)</span> <span class="p">)</span>
<span class="n">models</span><span class="o">.</span><span class="n">append</span><span class="p">(</span> <span class="n">Lasso</span><span class="p">(</span><span class="n">alpha</span><span class="o">=</span><span class="mf">0.5</span><span class="p">)</span> <span class="p">)</span>
<span class="n">models</span><span class="o">.</span><span class="n">append</span><span class="p">(</span> <span class="n">ElasticNet</span><span class="p">(</span><span class="n">alpha</span><span class="o">=</span><span class="mf">0.1</span><span class="p">,</span> <span class="n">l1_ratio</span><span class="o">=</span><span class="mf">0.5</span><span class="p">)</span> <span class="p">)</span>

<span class="n">Xw</span> <span class="o">=</span> <span class="n">X</span>
<span class="n">results</span> <span class="o">=</span> <span class="n">evalModels</span><span class="p">(</span><span class="n">models</span><span class="p">,</span> <span class="n">Xw</span><span class="p">,</span> <span class="n">y</span><span class="p">,</span> <span class="n">boxPlotOn</span><span class="o">=</span><span class="bp">True</span><span class="p">)</span>
</pre></div>
</div>
</div>
</div>
<div class="output_wrapper">
<div class="output">
<div class="output_area"><div class="prompt"></div>
<div class="output_subarea output_stream output_stdout output_text">
<pre>LinearRegression: 0.809 0.036
Ridge: 0.809 0.037
Lasso: 0.804 0.042
ElasticNet: 0.805 0.038
</pre>
</div>
</div>
<div class="output_area"><div class="prompt"></div>
<div class="output_png output_subarea ">
<img class="img-fluid" src="data:image/png;base64,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
">
</img></div>
</div>
</div>
</div>
</div>
<div class="cell border-box-sizing text_cell rendered">
<div class="prompt input_prompt">
</div>
<div class="inner_cell">
<div class="text_cell_render border-box-sizing rendered_html">
<p>All linear regression models perform similarly. The linear models with regularization most likely act like a standard linear regressor since the data is standardized. Top performing score is <code>R²=0.81</code> with std <code>0.36</code> achieved by standard linear regression.</p>
</div>
</div>
</div>
<div class="cell border-box-sizing text_cell rendered">
<div class="prompt input_prompt">
</div>
<div class="inner_cell">
<div class="text_cell_render border-box-sizing rendered_html">
<h3 id="4.2-K-Neigbors--and-Support-Vector-Regression">4.2 K-Neigbors  and Support Vector Regression<a class="anchor-link" href="#4.2-K-Neigbors--and-Support-Vector-Regression">¶</a></h3>
</div>
</div>
</div>
<div class="cell border-box-sizing code_cell rendered">
<div class="input">
<div class="prompt input_prompt">In [52]:</div>
<div class="inner_cell">
<div class="input_area">
<div class=" highlight hl-ipython2"><pre><span></span><span class="kn">from</span> <span class="nn">sklearn.svm</span> <span class="kn">import</span> <span class="n">SVR</span>
<span class="kn">from</span> <span class="nn">sklearn.neighbors</span> <span class="kn">import</span> <span class="n">KNeighborsRegressor</span>

<span class="c1"># create and evaluate pipeline</span>
<span class="n">models</span> <span class="o">=</span> <span class="p">[]</span>
<span class="n">models</span><span class="o">.</span><span class="n">append</span><span class="p">(</span> <span class="n">SVR</span><span class="p">(</span><span class="n">kernel</span><span class="o">=</span><span class="s1">'linear'</span><span class="p">,</span> <span class="n">C</span><span class="o">=</span><span class="mi">10</span><span class="p">,</span> <span class="n">epsilon</span><span class="o">=</span><span class="mf">0.3</span><span class="p">,</span> <span class="n">shrinking</span><span class="o">=</span><span class="bp">False</span><span class="p">)</span> <span class="p">)</span>
<span class="n">models</span><span class="o">.</span><span class="n">append</span><span class="p">(</span> <span class="n">SVR</span><span class="p">(</span><span class="n">kernel</span><span class="o">=</span><span class="s1">'poly'</span><span class="p">,</span> <span class="n">C</span><span class="o">=</span><span class="mi">4</span><span class="p">,</span> <span class="n">epsilon</span><span class="o">=</span><span class="mf">0.1</span><span class="p">,</span> <span class="n">degree</span><span class="o">=</span><span class="mi">1</span><span class="p">)</span> <span class="p">)</span>
<span class="n">models</span><span class="o">.</span><span class="n">append</span><span class="p">(</span> <span class="n">SVR</span><span class="p">(</span><span class="n">kernel</span><span class="o">=</span><span class="s1">'sigmoid'</span><span class="p">,</span> <span class="n">C</span><span class="o">=</span><span class="mf">0.2</span><span class="p">)</span> <span class="p">)</span>
<span class="n">models</span><span class="o">.</span><span class="n">append</span><span class="p">(</span> <span class="n">SVR</span><span class="p">(</span><span class="n">kernel</span><span class="o">=</span><span class="s1">'rbf'</span><span class="p">,</span> <span class="n">C</span><span class="o">=</span><span class="mi">20</span><span class="p">,</span> <span class="n">epsilon</span><span class="o">=</span><span class="mf">1.5</span><span class="p">)</span> <span class="p">)</span>
<span class="n">models</span><span class="o">.</span><span class="n">append</span><span class="p">(</span> <span class="n">KNeighborsRegressor</span><span class="p">(</span><span class="n">weights</span><span class="o">=</span><span class="s1">'distance'</span><span class="p">,</span> <span class="n">p</span><span class="o">=</span><span class="mi">2</span><span class="p">)</span> <span class="p">)</span>

<span class="n">Xw</span> <span class="o">=</span> <span class="n">X</span>
<span class="n">results</span> <span class="o">=</span> <span class="n">evalModels</span><span class="p">(</span><span class="n">models</span><span class="p">,</span> <span class="n">Xw</span><span class="p">,</span> <span class="n">y</span><span class="p">,</span> <span class="n">boxPlotOn</span><span class="o">=</span><span class="bp">True</span><span class="p">)</span>
</pre></div>
</div>
</div>
</div>
<div class="output_wrapper">
<div class="output">
<div class="output_area"><div class="prompt"></div>
<div class="output_subarea output_stream output_stdout output_text">
<pre>linearSVR: 0.802 0.044
polySVR: 0.798 0.044
sigmoidSVR: 0.768 0.052
rbfSVR: 0.882 0.034
KNeighborsRegressor: 0.856 0.037
</pre>
</div>
</div>
<div class="output_area"><div class="prompt"></div>
<div class="output_png output_subarea ">
<img class="img-fluid" src="data:image/png;base64,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
2AD3PBQrBPwAAAAASUVORK5CYII=
">
</img></div>
</div>
</div>
</div>
</div>
<div class="cell border-box-sizing text_cell rendered">
<div class="prompt input_prompt">
</div>
<div class="inner_cell">
<div class="text_cell_render border-box-sizing rendered_html">
<p>Both K-nearest neighbor and support vector machine regressors are distance-based predictors.</p>
<p>The support vector regressor with a linear kernel, <code>linearSVR</code>, somewhat mimics the linear regression results above. <code>SVR</code> with a polynomial kernel, <code>polySVR</code>, converges to <code>linearSVR</code> in performance as degree of the polynomial kernel is reduced to 1. The <code>sigmoidSVR</code> using a sigmoid kernel is the most inferior of the <code>SVR</code> models.</p>
<p>The <code>SVR</code> model with a radial-basis-function, <code>rbfSVR</code>, produces the best performance with <code>R²=0.88</code> and std <code>0.34</code>. This is the best result achieved in this study.</p>
<p>The K-neighbors regressor performance is also very strong.</p>
</div>
</div>
</div>
<div class="cell border-box-sizing text_cell rendered">
<div class="prompt input_prompt">
</div>
<div class="inner_cell">
<div class="text_cell_render border-box-sizing rendered_html">
<h3 id="4.3-Decision-Tree-and-Bagging-regression-algorithms">4.3 Decision Tree and Bagging regression algorithms<a class="anchor-link" href="#4.3-Decision-Tree-and-Bagging-regression-algorithms">¶</a></h3>
</div>
</div>
</div>
<div class="cell border-box-sizing code_cell rendered">
<div class="input">
<div class="prompt input_prompt">In [53]:</div>
<div class="inner_cell">
<div class="input_area">
<div class=" highlight hl-ipython2"><pre><span></span><span class="kn">from</span> <span class="nn">sklearn.tree</span> <span class="kn">import</span> <span class="n">DecisionTreeRegressor</span>
<span class="kn">from</span> <span class="nn">sklearn.tree</span> <span class="kn">import</span> <span class="n">ExtraTreeRegressor</span>
<span class="kn">from</span> <span class="nn">sklearn.ensemble</span> <span class="kn">import</span> <span class="n">BaggingRegressor</span>
<span class="kn">from</span> <span class="nn">sklearn.ensemble</span> <span class="kn">import</span> <span class="n">RandomForestRegressor</span>
<span class="kn">from</span> <span class="nn">sklearn.ensemble</span> <span class="kn">import</span> <span class="n">ExtraTreesRegressor</span>

<span class="c1"># create and evaluate pipeline</span>
<span class="n">models</span> <span class="o">=</span> <span class="p">[]</span>
<span class="n">models</span><span class="o">.</span><span class="n">append</span><span class="p">(</span> <span class="n">DecisionTreeRegressor</span><span class="p">(</span><span class="n">max_leaf_nodes</span><span class="o">=</span><span class="mi">9</span><span class="p">,</span> <span class="n">min_samples_leaf</span><span class="o">=</span><span class="mi">18</span><span class="p">)</span> <span class="p">)</span>
<span class="n">models</span><span class="o">.</span><span class="n">append</span><span class="p">(</span> <span class="n">ExtraTreeRegressor</span><span class="p">(</span><span class="n">criterion</span><span class="o">=</span><span class="s1">'mae'</span><span class="p">,</span> <span class="n">max_leaf_nodes</span><span class="o">=</span><span class="mi">50</span><span class="p">,</span> <span class="n">min_samples_leaf</span><span class="o">=</span><span class="mi">4</span><span class="p">,</span> <span class="n">min_samples_split</span><span class="o">=</span><span class="mi">6</span><span class="p">)</span> <span class="p">)</span>
<span class="n">cart</span> <span class="o">=</span> <span class="n">DecisionTreeRegressor</span><span class="p">()</span>
<span class="n">models</span><span class="o">.</span><span class="n">append</span><span class="p">(</span> <span class="n">BaggingRegressor</span><span class="p">(</span><span class="n">base_estimator</span><span class="o">=</span><span class="n">cart</span><span class="p">,</span> <span class="n">random_state</span><span class="o">=</span><span class="mi">7</span><span class="p">,</span> <span class="n">n_estimators</span><span class="o">=</span><span class="mi">300</span><span class="p">,</span> <span class="n">max_features</span><span class="o">=</span><span class="mi">6</span><span class="p">)</span> <span class="p">)</span>
<span class="n">models</span><span class="o">.</span><span class="n">append</span><span class="p">(</span> <span class="n">RandomForestRegressor</span><span class="p">(</span><span class="n">n_estimators</span><span class="o">=</span><span class="mi">100</span><span class="p">,</span> <span class="n">max_features</span><span class="o">=</span><span class="mi">4</span><span class="p">,</span> <span class="n">criterion</span><span class="o">=</span><span class="s1">'mae'</span><span class="p">,</span> <span class="n">max_leaf_nodes</span><span class="o">=</span><span class="mi">50</span><span class="p">,</span> <span class="n">min_samples_split</span><span class="o">=</span><span class="mi">4</span><span class="p">)</span> <span class="p">)</span>
<span class="n">models</span><span class="o">.</span><span class="n">append</span><span class="p">(</span> <span class="n">ExtraTreesRegressor</span><span class="p">(</span><span class="n">n_estimators</span><span class="o">=</span><span class="mi">100</span><span class="p">,</span> <span class="n">max_features</span><span class="o">=</span><span class="mi">4</span><span class="p">,</span> <span class="n">max_depth</span><span class="o">=</span><span class="mi">1000</span><span class="p">,</span> <span class="n">min_samples_split</span><span class="o">=</span><span class="mi">6</span><span class="p">)</span> <span class="p">)</span>

<span class="n">Xw</span> <span class="o">=</span> <span class="n">X</span>
<span class="n">plt</span><span class="o">.</span><span class="n">rcParams</span><span class="p">[</span><span class="s2">"figure.figsize"</span><span class="p">]</span> <span class="o">=</span> <span class="p">[</span><span class="mi">10</span><span class="p">,</span> <span class="mi">4</span><span class="p">]</span>
<span class="n">results</span> <span class="o">=</span> <span class="n">evalModels</span><span class="p">(</span><span class="n">models</span><span class="p">,</span> <span class="n">Xw</span><span class="p">,</span> <span class="n">y</span><span class="p">,</span> <span class="n">boxPlotOn</span><span class="o">=</span><span class="bp">True</span><span class="p">)</span>
<span class="n">plt</span><span class="o">.</span><span class="n">rcParams</span><span class="p">[</span><span class="s2">"figure.figsize"</span><span class="p">]</span> <span class="o">=</span> <span class="p">[</span><span class="mi">6</span><span class="p">,</span> <span class="mi">4</span><span class="p">]</span>
</pre></div>
</div>
</div>
</div>
<div class="output_wrapper">
<div class="output">
<div class="output_area"><div class="prompt"></div>
<div class="output_subarea output_stream output_stdout output_text">
<pre>DecisionTreeRegressor: 0.816 0.052
ExtraTreeRegressor: 0.803 0.051
BaggingRegressor: 0.867 0.035
RandomForestRegressor: 0.867 0.030
ExtraTreesRegressor: 0.878 0.033
</pre>
</div>
</div>
<div class="output_area"><div class="prompt"></div>
<div class="output_png output_subarea ">
<img class="img-fluid" src="data:image/png;base64,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
3L8AAAAASUVORK5CYII=
">
</img></div>
</div>
</div>
</div>
</div>
<div class="cell border-box-sizing text_cell rendered">
<div class="prompt input_prompt">
</div>
<div class="inner_cell">
<div class="text_cell_render border-box-sizing rendered_html">
<p>In this plot we are looking at the perfomance of decision tree variants of regression models. Albeit with a higher std, the basic decision tree regressor, <code>DecisionTreeRegressor</code>, performs on average slightly better than linear regression models and its sibling, the <code>ExtraTreeRegressor</code>.</p>
<p>The three bagging algorithms on the right employ 100-300 trees and show a strong performance with the <code>ExtraTrees</code> bagging algorithm almost matching the top performance of <code>rbfSVR</code> arriving at <code>R²=0.88</code> and std <code>0.33</code>.</p>
</div>
</div>
</div>
<div class="cell border-box-sizing text_cell rendered">
<div class="prompt input_prompt">
</div>
<div class="inner_cell">
<div class="text_cell_render border-box-sizing rendered_html">
<h3 id="4.4-Boosting-methods">4.4 Boosting methods<a class="anchor-link" href="#4.4-Boosting-methods">¶</a></h3>
</div>
</div>
</div>
<div class="cell border-box-sizing code_cell rendered">
<div class="input">
<div class="prompt input_prompt">In [54]:</div>
<div class="inner_cell">
<div class="input_area">
<div class=" highlight hl-ipython2"><pre><span></span><span class="kn">from</span> <span class="nn">sklearn.ensemble</span> <span class="kn">import</span> <span class="n">AdaBoostRegressor</span>
<span class="kn">from</span> <span class="nn">sklearn.ensemble</span> <span class="kn">import</span> <span class="n">GradientBoostingRegressor</span>

<span class="c1"># create and evaluate pipeline</span>
<span class="n">models</span> <span class="o">=</span> <span class="p">[]</span>
<span class="n">models</span><span class="o">.</span><span class="n">append</span><span class="p">(</span> <span class="n">AdaBoostRegressor</span><span class="p">(</span><span class="n">n_estimators</span><span class="o">=</span><span class="mi">10</span><span class="p">,</span> <span class="n">random_state</span><span class="o">=</span><span class="mi">7</span><span class="p">)</span> <span class="p">)</span>
<span class="n">models</span><span class="o">.</span><span class="n">append</span><span class="p">(</span> <span class="n">GradientBoostingRegressor</span><span class="p">(</span><span class="n">n_estimators</span><span class="o">=</span><span class="mi">80</span><span class="p">,</span> <span class="n">criterion</span><span class="o">=</span><span class="s1">'mae'</span><span class="p">,</span> <span class="n">max_features</span><span class="o">=</span><span class="mi">5</span><span class="p">,</span> <span class="n">min_samples_split</span><span class="o">=</span><span class="mi">15</span><span class="p">,</span> <span class="n">random_state</span><span class="o">=</span><span class="mi">7</span><span class="p">)</span> <span class="p">)</span>

<span class="n">Xw</span> <span class="o">=</span> <span class="n">X</span>
<span class="n">results</span> <span class="o">=</span> <span class="n">evalModels</span><span class="p">(</span><span class="n">models</span><span class="p">,</span> <span class="n">Xw</span><span class="p">,</span> <span class="n">y</span><span class="p">,</span> <span class="n">boxPlotOn</span><span class="o">=</span><span class="bp">True</span><span class="p">)</span>
</pre></div>
</div>
</div>
</div>
<div class="output_wrapper">
<div class="output">
<div class="output_area"><div class="prompt"></div>
<div class="output_subarea output_stream output_stdout output_text">
<pre>AdaBoostRegressor: 0.820 0.026
GradientBoostingRegressor: 0.851 0.027
</pre>
</div>
</div>
<div class="output_area"><div class="prompt"></div>
<div class="output_png output_subarea ">
<img class="img-fluid" src="data:image/png;base64,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
W4mYAAAAAElFTkSuQmCC
">
</img></div>
</div>
</div>
</div>
</div>
<div class="cell border-box-sizing text_cell rendered">
<div class="prompt input_prompt">
</div>
<div class="inner_cell">
<div class="text_cell_render border-box-sizing rendered_html">
<p>The boosting methods are also decision-tree based as the models covered in the previous section although the optimum number of trees were found to be much lower than that of the bagging methods: <code>10</code> for <code>AdaBoost</code> and <code>80</code> for <code>GradientBoosting</code>. Although their average peformance is somewhat lower than the bagging methods, the boosting methods has the lowest std in performance so far: <code>0.26</code> for <code>AdaBoost</code>.</p>
</div>
</div>
</div>
<div class="cell border-box-sizing text_cell rendered">
<div class="prompt input_prompt">
</div>
<div class="inner_cell">
<div class="text_cell_render border-box-sizing rendered_html">
<h3 id="4.5-Comparison-Summary">4.5 Comparison Summary<a class="anchor-link" href="#4.5-Comparison-Summary">¶</a></h3><p>Below is the list of ML methods producing an average R² value larger than 0.85 starting with the highest score:</p>
<ul>
<li><code>SVR</code> with <code>rbf</code> kernel    : 0.882 with std of 0.034</li>
<li><code>ExtraTreesRegressor</code>      : 0.878 with std of 0.033</li>
<li><code>RandomForestRegressor</code>    : 0.867 with std of 0.030</li>
<li><code>BaggingRegressor</code>         : 0.867 with std of 0.035</li>
<li><code>KNeighborsRegressor</code>      : 0.856 with std of 0.037</li>
<li><code>GradientBoostingRegressor</code>: 0.851 with std of 0.027</li>
</ul>
</div>
</div>
</div>
<div class="cell border-box-sizing text_cell rendered">
<div class="prompt input_prompt">
</div>
<div class="inner_cell">
<div class="text_cell_render border-box-sizing rendered_html">
<hr>
<h2 id="5.-Algorithm-Tuning">5. Algorithm Tuning<a class="anchor-link" href="#5.-Algorithm-Tuning">¶</a></h2>
</hr></div>
</div>
</div>
<div class="cell border-box-sizing text_cell rendered">
<div class="prompt input_prompt">
</div>
<div class="inner_cell">
<div class="text_cell_render border-box-sizing rendered_html">
<h3 id="5.1-Grid-Search-Parameter-Tuning">5.1 Grid Search Parameter Tuning<a class="anchor-link" href="#5.1-Grid-Search-Parameter-Tuning">¶</a></h3>
</div>
</div>
</div>
<div class="cell border-box-sizing code_cell rendered">
<div class="input">
<div class="prompt input_prompt">In [8]:</div>
<div class="inner_cell">
<div class="input_area">
<div class=" highlight hl-ipython2"><pre><span></span><span class="c1"># Standardize data (0 mean, 1 stdev)</span>
<span class="kn">from</span> <span class="nn">sklearn.preprocessing</span> <span class="kn">import</span> <span class="n">StandardScaler</span>
<span class="n">scaler</span> <span class="o">=</span> <span class="n">StandardScaler</span><span class="p">()</span><span class="o">.</span><span class="n">fit</span><span class="p">(</span><span class="n">X</span><span class="p">)</span>
<span class="n">standardizedX</span> <span class="o">=</span> <span class="n">scaler</span><span class="o">.</span><span class="n">transform</span><span class="p">(</span><span class="n">X</span><span class="p">)</span>
<span class="n">Xw</span> <span class="o">=</span> <span class="n">standardizedX</span>
<span class="kn">from</span> <span class="nn">sklearn.model_selection</span> <span class="kn">import</span> <span class="n">KFold</span>

<span class="c1"># Grid Search for Algorithm Tuning</span>
<span class="kn">from</span> <span class="nn">sklearn.linear_model</span> <span class="kn">import</span> <span class="n">Ridge</span>
<span class="kn">from</span> <span class="nn">sklearn.model_selection</span> <span class="kn">import</span> <span class="n">GridSearchCV</span>

<span class="n">alphas</span> <span class="o">=</span> <span class="n">np</span><span class="o">.</span><span class="n">array</span><span class="p">([</span><span class="mi">1</span><span class="p">,</span><span class="mf">0.5</span><span class="p">,</span><span class="mf">0.2</span><span class="p">,</span><span class="mf">0.1</span><span class="p">,</span><span class="mf">0.01</span><span class="p">,</span><span class="mf">0.001</span><span class="p">,</span><span class="mf">0.0001</span><span class="p">,</span><span class="mi">0</span><span class="p">])</span>
<span class="n">param_grid</span> <span class="o">=</span> <span class="nb">dict</span><span class="p">(</span><span class="n">alpha</span><span class="o">=</span><span class="n">alphas</span><span class="p">)</span>
<span class="n">model</span> <span class="o">=</span> <span class="n">Ridge</span><span class="p">()</span>
<span class="n">kfold</span> <span class="o">=</span> <span class="n">KFold</span><span class="p">(</span><span class="n">n_splits</span><span class="o">=</span><span class="mi">8</span><span class="p">,</span> <span class="n">random_state</span><span class="o">=</span><span class="mi">6</span><span class="p">,</span> <span class="n">shuffle</span><span class="o">=</span><span class="bp">True</span><span class="p">)</span>

<span class="n">grid</span> <span class="o">=</span> <span class="n">GridSearchCV</span><span class="p">(</span><span class="n">estimator</span><span class="o">=</span><span class="n">model</span><span class="p">,</span> <span class="n">param_grid</span><span class="o">=</span><span class="n">param_grid</span><span class="p">,</span> <span class="n">cv</span><span class="o">=</span><span class="n">kfold</span><span class="p">)</span>
<span class="n">grid</span><span class="o">.</span><span class="n">fit</span><span class="p">(</span><span class="n">Xw</span><span class="p">,</span> <span class="n">y</span><span class="p">)</span>
<span class="k">print</span><span class="p">(</span><span class="n">grid</span><span class="o">.</span><span class="n">best_score_</span><span class="p">)</span>
<span class="k">print</span><span class="p">(</span><span class="n">grid</span><span class="o">.</span><span class="n">best_estimator_</span><span class="o">.</span><span class="n">alpha</span><span class="p">)</span>
<span class="c1">#print grid.cv_results_</span>
</pre></div>
</div>
</div>
</div>
<div class="output_wrapper">
<div class="output">
<div class="output_area"><div class="prompt"></div>
<div class="output_subarea output_stream output_stdout output_text">
<pre>0.809570605568
1.0
</pre>
</div>
</div>
</div>
</div>
</div>
<div class="cell border-box-sizing text_cell rendered">
<div class="prompt input_prompt">
</div>
<div class="inner_cell">
<div class="text_cell_render border-box-sizing rendered_html">
<h3 id="5.2-Random-Search-Parameter-Tuning">5.2 Random Search Parameter Tuning<a class="anchor-link" href="#5.2-Random-Search-Parameter-Tuning">¶</a></h3>
</div>
</div>
</div>
<div class="cell border-box-sizing code_cell rendered">
<div class="input">
<div class="prompt input_prompt">In [9]:</div>
<div class="inner_cell">
<div class="input_area">
<div class=" highlight hl-ipython2"><pre><span></span><span class="n">Xw</span> <span class="o">=</span> <span class="n">standardizedX</span>

<span class="c1"># Randomized for Algorithm Tuning</span>
<span class="kn">from</span> <span class="nn">scipy.stats</span> <span class="kn">import</span> <span class="n">uniform</span>
<span class="kn">from</span> <span class="nn">sklearn.linear_model</span> <span class="kn">import</span> <span class="n">Ridge</span>
<span class="kn">from</span> <span class="nn">sklearn.model_selection</span> <span class="kn">import</span> <span class="n">RandomizedSearchCV</span>

<span class="n">param_grid</span> <span class="o">=</span> <span class="p">{</span><span class="s1">'alpha'</span><span class="p">:</span> <span class="n">uniform</span><span class="p">()}</span>
<span class="n">seed</span><span class="o">=</span><span class="mi">6</span>
<span class="n">model</span> <span class="o">=</span> <span class="n">Ridge</span><span class="p">()</span>
<span class="n">kfold</span> <span class="o">=</span> <span class="n">KFold</span><span class="p">(</span><span class="n">n_splits</span><span class="o">=</span><span class="mi">8</span><span class="p">,</span> <span class="n">random_state</span><span class="o">=</span><span class="n">seed</span><span class="p">,</span> <span class="n">shuffle</span><span class="o">=</span><span class="bp">True</span><span class="p">)</span>

<span class="n">rsearch</span> <span class="o">=</span> <span class="n">RandomizedSearchCV</span><span class="p">(</span><span class="n">estimator</span><span class="o">=</span><span class="n">model</span><span class="p">,</span> <span class="n">param_distributions</span><span class="o">=</span><span class="n">param_grid</span><span class="p">,</span> <span class="n">n_iter</span><span class="o">=</span><span class="mi">100</span><span class="p">,</span> <span class="n">cv</span><span class="o">=</span><span class="n">kfold</span><span class="p">,</span> <span class="n">random_state</span><span class="o">=</span><span class="n">seed</span><span class="p">)</span>
<span class="n">rsearch</span><span class="o">.</span><span class="n">fit</span><span class="p">(</span><span class="n">Xw</span><span class="p">,</span> <span class="n">y</span><span class="p">)</span>
<span class="k">print</span><span class="p">(</span><span class="n">rsearch</span><span class="o">.</span><span class="n">best_score_</span><span class="p">)</span>
<span class="k">print</span><span class="p">(</span><span class="n">rsearch</span><span class="o">.</span><span class="n">best_estimator_</span><span class="o">.</span><span class="n">alpha</span><span class="p">)</span>
</pre></div>
</div>
</div>
</div>
<div class="output_wrapper">
<div class="output">
<div class="output_area"><div class="prompt"></div>
<div class="output_subarea output_stream output_stdout output_text">
<pre>0.809570412842
0.994207438422
</pre>
</div>
</div>
</div>
</div>
</div>
<div class="cell border-box-sizing code_cell rendered">
<div class="input">
<div class="prompt input_prompt">In [ ]:</div>
<div class="inner_cell">
<div class="input_area">
<div class=" highlight hl-ipython2"><pre><span></span> 
</pre></div>
</div>
</div>
</div>
</div>
<script type="text/javascript">if (!document.getElementById('mathjaxscript_pelican_#%@#$@#')) {
    var mathjaxscript = document.createElement('script');
    mathjaxscript.id = 'mathjaxscript_pelican_#%@#$@#';
    mathjaxscript.type = 'text/javascript';
    mathjaxscript.src = '//cdn.mathjax.org/mathjax/latest/MathJax.js?config=TeX-AMS-MML_HTMLorMML';
    mathjaxscript[(window.opera ? "innerHTML" : "text")] =
        "MathJax.Hub.Config({" +
        "    config: ['MMLorHTML.js']," +
        "    TeX: { extensions: ['AMSmath.js','AMSsymbols.js','noErrors.js','noUndefined.js'], equationNumbers: { autoNumber: 'AMS' } }," +
        "    jax: ['input/TeX','input/MathML','output/HTML-CSS']," +
        "    extensions: ['tex2jax.js','mml2jax.js','MathMenu.js','MathZoom.js']," +
        "    displayAlign: 'center'," +
        "    displayIndent: '0em'," +
        "    showMathMenu: true," +
        "    tex2jax: { " +
        "        inlineMath: [ ['$','$'] ], " +
        "        displayMath: [ ['$$','$$'] ]," +
        "        processEscapes: true," +
        "        preview: 'TeX'," +
        "    }, " +
        "    'HTML-CSS': { " +
        "        styles: { '.MathJax_Display, .MathJax .mo, .MathJax .mi, .MathJax .mn': {color: 'black ! important'} }" +
        "    } " +
        "}); ";
    (document.body || document.getElementsByTagName('head')[0]).appendChild(mathjaxscript);
}
</script>
                </article>
            </aside><!-- /#featured -->
                <section id="content" class="body">
                    <h1>Other articles</h1>
                    <hr />
                    <ol id="posts-list" class="hfeed">

            <li><article class="hentry">
                <header>
                    <h1><a href="http://fatihsarigoz.com/scaling-rfe.html" rel="bookmark"
                           title="Permalink to Impact of Scaling on Feature Selection with RFE">Impact of Scaling on Feature Selection with RFE</a></h1>
                </header>

                <div class="entry-content">
<footer class="post-info">
        <abbr class="published" title="2017-01-03T14:30:00-08:00">
                Published: Tue 03 January 2017
        </abbr>

        <address class="vcard author">
                By                         <a class="url fn" href="http://fatihsarigoz.com/author/fatih-sarigoz.html">Fatih Sarigoz</a>
        </address>
<p>In <a href="http://fatihsarigoz.com/category/posts.html">Posts</a>.</p>
<p>tags: <a href="http://fatihsarigoz.com/tag/machine_learning-feature_selection-rfe.html">machine_learning feature_selection RFE</a> </p>
</footer><!-- /.post-info -->                
<div class="cell border-box-sizing text_cell rendered">
<div class="prompt input_prompt">
</div>
<div class="inner_cell">
<div class="text_cell_render border-box-sizing rendered_html">
<h1 id="Impact-of-Scaling-on-Feature-Elimination-with-RFE">Impact of Scaling on Feature Elimination with RFE<a class="anchor-link" href="#Impact-of-Scaling-on-Feature-Elimination-with-RFE">¶</a></h1><p>In this project, we will investigate how scaling the data impacts the output of a number of feature selection tools in scikit-learn.</p>
<p>In particular we will look into</p>
<ul>
<li>Linear Regression</li>
<li>Decisition Tree Regression</li>
<li>Support Vector Regression</li>
</ul>
<p>For this project we will use the <a href="https://archive.ics.uci.edu/ml/datasets/Auto+MPG"><code>Auto MPG</code></a> data set. Please follow the instructions in the post <a href="./autompg-data.html"><code>Working with the Auto MPG Data Set</code>
                <a class="readmore" href="http://fatihsarigoz.com/scaling-rfe.html">read more</a>
                </div><!-- /.entry-content -->
            </article></li>

            <li><article class="hentry">
                <header>
                    <h1><a href="http://fatihsarigoz.com/about-me.html" rel="bookmark"
                           title="Permalink to About me">About me</a></h1>
                </header>

                <div class="entry-content">
<footer class="post-info">
        <abbr class="published" title="2017-01-01T00:50:00-08:00">
                Published: Sun 01 January 2017
        </abbr>

        <address class="vcard author">
                By                         <a class="url fn" href="http://fatihsarigoz.com/author/fatih-sarigoz.html">Fatih Sarigoz</a>
        </address>
<p>In <a href="http://fatihsarigoz.com/category/about.html">About</a>.</p>
<p>tags: <a href="http://fatihsarigoz.com/tag/about-me.html">about me</a> </p>
</footer><!-- /.post-info -->                
<div class="cell border-box-sizing text_cell rendered">
<div class="prompt input_prompt">
</div>
<div class="inner_cell">
<div class="text_cell_render border-box-sizing rendered_html">
<h1 id="About-Me">About Me<a class="anchor-link" href="#About-Me">¶</a></h1><p>My journey started with Signal Processing and Communications, fields very much intertwined with Machine Learning. In fact, my first serious signal processing project was the use of K-means clustering on images (aka Vector Quantization) and later using Neural Networks for binary classification of signals from a data storage channel.</p>
                <a class="readmore" href="http://fatihsarigoz.com/about-me.html">read more</a>
                </div><!-- /.entry-content -->
            </article></li>

            <li><article class="hentry">
                <header>
                    <h1><a href="http://fatihsarigoz.com/scaling-ml.html" rel="bookmark"
                           title="Permalink to Impact of Scaling on Machine Learning Regression Algorithms">Impact of Scaling on Machine Learning Regression Algorithms</a></h1>
                </header>

                <div class="entry-content">
<footer class="post-info">
        <abbr class="published" title="2016-12-20T15:00:00-08:00">
                Published: Tue 20 December 2016
        </abbr>

        <address class="vcard author">
                By                         <a class="url fn" href="http://fatihsarigoz.com/author/fatih-sarigoz.html">Fatih Sarigoz</a>
        </address>
<p>In <a href="http://fatihsarigoz.com/category/posts.html">Posts</a>.</p>
<p>tags: <a href="http://fatihsarigoz.com/tag/python-machine_learning-scaling-regression.html">python machine_learning scaling regression</a> </p>
</footer><!-- /.post-info -->                
<div class="cell border-box-sizing text_cell rendered">
<div class="prompt input_prompt">
</div>
<div class="inner_cell">
<div class="text_cell_render border-box-sizing rendered_html">
<h1 id="Impact-of-Scaling-on-Machine-Learning-Regression-Algorithms">Impact of Scaling on Machine Learning Regression Algorithms<a class="anchor-link" href="#Impact-of-Scaling-on-Machine-Learning-Regression-Algorithms">¶</a></h1><p>In this project, we will investigate how scaling the data impacts the performance of a variety of machine learning algorithms for prediction.</p>
<p>In particular we will look into</p>
<ul>
<li>Linear Regression and other linear models</li>
<li>K-nearest Regression</li>
<li>Decisition Tree Regression</li>
<li>Support Vector Regression</li>
<li>Bagging algorithms</li>
<li>Boosting algorithms</li>
</ul>
<p>For this project we will use the <a href="https://archive.ics.uci.edu/ml/datasets/Auto+MPG"><code>Auto MPG</code>
                <a class="readmore" href="http://fatihsarigoz.com/scaling-ml.html">read more</a>
                </div><!-- /.entry-content -->
            </article></li>

            <li><article class="hentry">
                <header>
                    <h1><a href="http://fatihsarigoz.com/autompg-data.html" rel="bookmark"
                           title="Permalink to Working with the Auto MPG Data Set">Working with the Auto MPG Data Set</a></h1>
                </header>

                <div class="entry-content">
<footer class="post-info">
        <abbr class="published" title="2016-12-19T18:30:00-08:00">
                Published: Mon 19 December 2016
        </abbr>

        <address class="vcard author">
                By                         <a class="url fn" href="http://fatihsarigoz.com/author/fatih-sarigoz.html">Fatih Sarigoz</a>
        </address>
<p>In <a href="http://fatihsarigoz.com/category/posts.html">Posts</a>.</p>
<p>tags: <a href="http://fatihsarigoz.com/tag/python-machine_learning-auto-mpg-dataset.html">python machine_learning auto mpg dataset</a> </p>
</footer><!-- /.post-info -->                
<div class="cell border-box-sizing text_cell rendered">
<div class="prompt input_prompt">
</div>
<div class="inner_cell">
<div class="text_cell_render border-box-sizing rendered_html">
<h1 id="Working-with-the-Auto-MPG-Data-Set">Working with the Auto MPG Data Set<a class="anchor-link" href="#Working-with-the-Auto-MPG-Data-Set">¶</a></h1><p>In this post we will look into the <a href="https://archive.ics.uci.edu/ml/datasets/Auto+MPG"><code>Auto MPG</code></a> data set and clean it so that it is ready for further use.</p>
<p>This data set shows the <code>mpg</code> of a group of car models produced in the 1970s and the 1980s along with some characteristic information associated with each model. More information about the data set can be found <a href="https://archive.ics.uci.edu/ml/machine-learning-databases/auto-mpg/auto-mpg.names">here</a>
                <a class="readmore" href="http://fatihsarigoz.com/autompg-data.html">read more</a>
                </div><!-- /.entry-content -->
            </article></li>

            <li><article class="hentry">
                <header>
                    <h1><a href="http://fatihsarigoz.com/resume-bio.html" rel="bookmark"
                           title="Permalink to Resume">Resume</a></h1>
                </header>

                <div class="entry-content">
<footer class="post-info">
        <abbr class="published" title="2016-12-15T12:00:00-08:00">
                Published: Thu 15 December 2016
        </abbr>

        <address class="vcard author">
                By                         <a class="url fn" href="http://fatihsarigoz.com/author/fatih-sarigoz.html">Fatih Sarigoz</a>
        </address>
<p>In <a href="http://fatihsarigoz.com/category/resume.html">Resume</a>.</p>
<p>tags: <a href="http://fatihsarigoz.com/tag/resume-bio.html">resume bio</a> </p>
</footer><!-- /.post-info -->                
<div class="cell border-box-sizing text_cell rendered">
<div class="prompt input_prompt">
</div>
<div class="inner_cell">
<div class="text_cell_render border-box-sizing rendered_html">
<h1 id="Fatih-Sarigoz">Fatih Sarigoz<a class="anchor-link" href="#Fatih-Sarigoz">¶</a></h1><p>E-mail: fsarigoz@gmail.com
<br />Blog: <a href="www.fatihsarigoz.com">www.fatihsarigoz.com</a>
<br />LinkedIn: <a href="https://www.linkedin.com/in/fatihsarigoz">https://www.linkedin.com/in/fatihsarigoz</a></p>
</div>
</div>
</div>
<div class="cell border-box-sizing text_cell rendered">
<div class="prompt input_prompt">
</div>
<div class="inner_cell">
<div class="text_cell_render border-box-sizing rendered_html">
<h2 id="Summary">Summary<a class="anchor-link" href="#Summary">¶</a></h2><p>Looking for a challenging position as a Data Scientist. Strong background in data science, machine learning, probability and statistics theory. Experienced practitioner of detection, estimation and classification techniques.</p>
<ul>
<li>Avid self-learner. Please see my blog for personal data science projects.</li>
<li>Extensive programming in Matlab and Python. </li>
<li>Strong team player and team building skills. Strong communicator.</li>
                <a class="readmore" href="http://fatihsarigoz.com/resume-bio.html">read more</a>
                </div><!-- /.entry-content -->
            </article></li>

            <li><article class="hentry">
                <header>
                    <h1><a href="http://fatihsarigoz.com/first-post.html" rel="bookmark"
                           title="Permalink to First Post">First Post</a></h1>
                </header>

                <div class="entry-content">
<footer class="post-info">
        <abbr class="published" title="2016-12-06T18:00:00-08:00">
                Published: Tue 06 December 2016
        </abbr>

        <address class="vcard author">
                By                         <a class="url fn" href="http://fatihsarigoz.com/author/fatih-sarigoz.html">Fatih Sarigoz</a>
        </address>
<p>In <a href="http://fatihsarigoz.com/category/posts.html">posts</a>.</p>
<p>tags: <a href="http://fatihsarigoz.com/tag/first-python-pelican-jupyter-notebook.html">first python pelican Jupyter notebook</a> </p>
</footer><!-- /.post-info -->                None
                <a class="readmore" href="http://fatihsarigoz.com/first-post.html">read more</a>
                </div><!-- /.entry-content -->
            </article></li>
                </ol><!-- /#posts-list -->
                </section><!-- /#content -->
        <section id="extras" class="body">
                <div class="blogroll">
                        <h2>blogroll</h2>
                        <ul>
                            <li><a href="http://getpelican.com/">Pelican</a></li>
                            <li><a href="http://python.org/">Python.org</a></li>
                            <li><a href="http://jinja.pocoo.org/">Jinja2</a></li>
                            <li><a href="#">You can modify those links in your config file</a></li>
                        </ul>
                </div><!-- /.blogroll -->
                <div class="social">
                        <h2>social</h2>
                        <ul>
                            <li><a href="http://fatihsarigoz.com/feeds/all.atom.xml" type="application/atom+xml" rel="alternate">atom feed</a></li>

                            <li><a href="https://twitter.com/fatihsarigoz">twitter</a></li>
                            <li><a href="http://www.linkedin.com/in/fatihsarigoz">linkedin</a></li>
                            <li><a href="https://github.com/fsarigoz">github</a></li>
                        </ul>
                </div><!-- /.social -->
        </section><!-- /#extras -->

        <footer id="contentinfo" class="body">
                <address id="about" class="vcard body">
                Proudly powered by <a href="http://getpelican.com/">Pelican</a>, which takes great advantage of <a href="http://python.org">Python</a>.
                </address><!-- /#about -->

                <p>The theme is by <a href="http://coding.smashingmagazine.com/2009/08/04/designing-a-html-5-layout-from-scratch/">Smashing Magazine</a>, thanks!</p>
        </footer><!-- /#contentinfo -->

</body>
</html>
© 2018 GitHub, Inc.
Terms
Privacy
Security
Status
Help
Contact GitHub
Pricing
API
Training
Blog
About
Press h to open a hovercard with more details.
