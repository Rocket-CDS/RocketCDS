---
layout: page
title: SimplisityJS
menubar: simplisityjs_menu
show_sidebar: false
---

# Field Data

<div class="w3-container">Hidden fields are created by simplisity on page load, these are to keep track of data that often needs passing to the server.</div>

<div class="w3-container w3-margin-top">
<div class="w3-row-padding">
<table class="w3-table w3-bordered">
	<tbody>
		<tr class="w3-teal">
			<th>Field ID</th>
			<th>&nbsp;</th>
		</tr>
		<tr>
			<td>simplisity_systemkey</td>
			<td>This is set by the &quot;simplisity_startup&quot; function (see below). It keeps track of the default systemkey being used by the page.
			<hr />
			<div class="w3-code ">$(document).ready(function () {<br />
			$(document).simplisityStartUp(&#39;/<i>My API call url</i>&#39;, { systemkey: &#39;amylisbusiness&#39;});<br />
			});</div>
			</td>
		</tr>
		<tr>
			<td>simplisity_loader</td>
			<td>This is a an element with a class which will be displayed when a call to the server is made. By default this is &quot;overlayclass: &#39;w3-overlay&#39;&quot; but this call can be overwritten on the &quot;simplisity_startup&quot; function. If required it can be used with JQuery or JS. $(&#39;#simplisity_loader&#39;).show();</td>
		</tr>
		<tr>
			<td>simplisity_fileuploadlist</td>
			<td>This field keeps a list of the files which need to be uploaded. They are then passed and processed server side.</td>
		</tr>
		<tr>
			<td>simplisity_params</td>
			<td>List of the params that need to be passed to server side (use &#39;simplisity_setParamField&#39; function). These are found on the server in the &quot;paramjson&quot; form fields.
			<p>This field will also save the &quot;activevalue&quot; paramater. The &quot;activevalue&quot; is the current element value. It can be used by server side code: <b>paramInfo.GetXmlProperty(&quot;genxml/hidden/activevalue&quot;)</b></p>
			</td>
		</tr>
		<tr>
			<td>simplisity_searchfields</td>
			<td>List of the search fields and data that needs to be passed to server side for a search operation. These are passed in the &quot;paramjson&quot; form fields.</td>
		</tr>
		<tr>
			<td>simplisity_cmdurl</td>
			<td>The current page API url endpoint. All commands that do not have a &#39;cmdurl&#39; (API endpoint) specified will use this as the API endpoint. This is set by the &quot;$(document).simplisityStartUp(string apiurl)&quot; method, which will be on the starting page.</td>
		</tr>
	</tbody>
</table>
</div>

<div class="w3-row-padding">
<div>&nbsp;</div>
</div>

<div class="w3-row-padding">
<div>&nbsp;</div>
</div>
</div>
