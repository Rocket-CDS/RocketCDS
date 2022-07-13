---
layout: page
title: SimplisityJS
menubar: simplisityjs_menu
show_sidebar: false
---

# Methods

<div class="w3-container w3-margin-top">
<div class="w3-row-padding">
<p>Simplisty has a few methods which are called to make things happen.</p>

<p><b>$(document).simplisityStartUp(<i>string</i> apiurl)</b></p>

<p>This is the main activation for Simplisity. It searches the webpage for any html elements with &quot;simplisity_panel&quot; class. Simplisity will then process the command attributes attached to the html element.</p>

<p>Options can also be passed. {systemkey: &#39;dnnrocket&#39;,activatepanel: true, overlayclass: &#39;w3-overlay&#39;}.<br />
<br />
<b>systemkey:</b> You can pass a default systemkey to use if non are specifiecd on the simplisity_panel. This stops the need to specify the systemkey on each simplisity_panel.<br />
<b>activatepanel:</b> Activate the simplsity_panels. Default:true<br />
<b>overlayclass:</b> Defines a overlayclass to use, for when the server is called. Default: w3-overlay<br />
<b>debug:</b> Puts the JS in debug mode. The browser console log will contain data to help debuging.</p>

<p><i>Example:</i><br />
$(document).simplisityStartUp(&#39;/DesktopModules/DNNrocket/api/api.ashx&#39;, { systemkey: &#39;rocketexample&#39;, overlayclass:&#39;w3-overlay w3-theme&#39; });;</p>

<p><b>$(&#39;#mycontainer&#39;).activateSimplisityPanel()</b></p>

<p>Each &quot;simplisity_panel&quot; can be called individually.</p>

<p><b>$(&#39;#mycontainer&#39;).getSimplisity(<i>string</i> s-cmdurl, <i>string</i> s-cmd, <i>string</i> s-fields,<i>string</i> s-after) </b></p>

<p>This method will do an individual post to the server API and a return of data to the selected element. <strong>Use a valid element ID (no underscores)</strong>.</p>

<p><b>simplisity_callserver(element, cmdurl, returncontainer, reload)</b></p>

<p>The JavaScript function to post to the server can also be called directly. This works by passing the html element and the command attributes on the element tell the simplisity code what to do.</p>

<p>If we have already called simplisity server then the last command url used will be activate. Therefore we can call this function with the minimum of parameters. i.e. only the html element.</p>

<p>WARNING!! When used with simplisity_panel on the same page, multiple calls may be made to the server. This can lead to unexpected results and race conditions.</p>

<h4>Examples</h4>

<p>simplisity_callserver(this, &#39;/DesktopModules/DNNrocket/API/api.ashx&#39;, &#39;#myreturn&#39;, false)<br />
<br />
<i>Minimum call parameters</i><br />
simplisity_callserver(this)</p>
</div>
</div>
