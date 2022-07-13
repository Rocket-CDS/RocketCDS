---
layout: page
title: SimplisityJS
menubar: simplisityjs_menu
show_sidebar: false
---

# Utility Functions

<div class="w3-container w3-margin-top">
<p>Simplisity has some general functions which can be used.</p>

<div class="w3-row-padding">
<table class="w3-table w3-bordered">
	<tbody>
		<tr class="w3-teal">
			<th>Function Name</th>
			<th>&nbsp;</th>
		</tr>
		<tr>
			<td>simplisity_encode(value)</td>
			<td>Encode data into decimal format, this is used if you need to ensure special chars do not effect operation. &quot;decimalchar.decimalchar.decimalchar....&quot;</td>
		</tr>
		<tr>
			<td>simplisity_decode(value)</td>
			<td>Decode value from decimal encode format back to normal string.</td>
		</tr>
		<tr>
			<td>simplisity_getCookieValue(cookiename)</td>
			<td>Get Cookie</td>
		</tr>
		<tr>
			<td>simplisity_setCookieValue(cookiename,cookievalue)</td>
			<td>Set Cookie</td>
		</tr>
		<tr>
			<td>simplisity_setParamField(fieldkey, fieldvalue)</td>
			<td>Sets a value to the &quot;#simplisity_params&quot; field, to be passed to the server.</td>
		</tr>
		<tr>
			<td>simplisity_getParamField(fieldkey)</td>
			<td>Gets a value from the &quot;#simplisity_params&quot; field</td>
		</tr>
		<tr>
			<td>simplisity_getField(sfields, fieldkey)</td>
			<td>Gets a value from the sfield json passed to it.</td>
		</tr>
		<tr>
			<td>simplisity_lastmenuindex()</td>
			<td>Get the index of the last menu item clicked.</td>
		</tr>
		<tr>
			<td>simplisity_emptyrecyclebin(recyclebin)</td>
			<td>Removes ALL elements from a recycle bin.</td>
		</tr>
		<tr>
			<td>simplisity_getpostjson(elementselector)</td>
			<td>returns a json string of all child inputs.</td>
		</tr>
		<tr>
			<td>simplisity_getlistjson(elementselector)</td>
			<td>returns a json string of all child inputs for a list.</td>
		</tr>
		<tr>
			<td>simplisity_injectlink(uri)</td>
			<td>Used to inject a CSS file at runtime, this is sometimes usefull when the base page does not contain a link or you need a specialized CSS.</td>
		</tr>
		<tr>
			<td>simplisity_injectscript(uri)</td>
			<td>Used to inject a JS file at runtime. You may need to use setTimeout if you required the JS instantly after load. There is a delay between load and the browser registering it. <i>This also applies to dependent JS files, so the order of inject is important.</i>
			<div class="w3-code">$(document).ready(function () { simplisity_injectlink( &#39;https://cdnjs.cloudflare.com/ajax/libs/leaflet/1.3.3/leaflet.css&#39; ); simplisity_injectscript( &#39;https://cdnjs.cloudflare.com/ajax/libs/leaflet/1.3.3/leaflet.js&#39; );<br />
			setTimeout(() =&gt; { simplisity_injectscript( &#39;https://cdnjs.cloudflare.com/ajax/libs/leaflet-ajax/2.1.0/leaflet.ajax.min.js&#39; ); }, 1000);<br />
			setTimeout(() =&gt; { initmap(); }, 1000);<br />
			});</div>
			</td>
		</tr>
		<tr>
			<td>simplisity_systemkey()</td>
			<td>Returns the SystemKey which is stored by simplisity on the page. (In the &#39;#simplisity_systemkey&#39; field.)</td>
		</tr>
		<tr>
			<td>simplisity_sessionjson()</td>
			<td>Returns the SessionParams which have been loaded into localStorage by &quot;simplisity_setSessionField(fieldkey, fieldvalue)&quot;.</td>
		</tr>
		<tr>
			<td>simplisity_sessionremove()</td>
			<td>Clears the SessionParams from localStorage.</td>
		</tr>
		<tr>
			<td>simplisity_sessionpost()</td>
			<td>This will post ALL session fields in the sessionParams back to the server in the param fields.</td>
		</tr>
		<tr>
			<td>simplisity_setSessionField(fieldkey, fieldvalue)</td>
			<td>Set session field param to localStorage.</td>
		</tr>
		<tr>
			<td>simplisity_getSessionField(fieldkey)</td>
			<td>Gets session field param from localStorage.</td>
		</tr>
		<tr>
			<td>simplisity_parsejson(jsonString)</td>
			<td>Converts a json string to a json object. If the parameter is already a json object no conversion is done and the json object is returned.</td>
		</tr>
		<tr>
			<td>simplisity_removepagefields()</td>
			<td>Simplisity uses temporary fields on the page to track data. This method can be used to clear those fields. (&quot;simplisity_fileuploadlist&quot;,&quot;simplisity_params&quot;)</td>
		</tr>
	</tbody>
</table>
</div>
</div>
