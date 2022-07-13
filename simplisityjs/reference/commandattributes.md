---
layout: page
title: SimplisityJS
menubar: simplisityjs_menu
show_sidebar: false
---

# Command Attributes

<div class="w3-container w3-margin">Simplisty uses element attributes to do the required processing and to pass/return data to the server side API.</div>

<div class="w3-container w3-margin-top">
<div class="w3-row-padding">
<table class="w3-table w3-bordered">
	<tbody>
		<tr class="w3-teal">
			<th style="width:200px;">Attribute Name</th>
			<th>&nbsp;</th>
		</tr>
		<tr>
			<td>s-cmdurl</td>
			<td>Server side API url. This is saved to a cookie when used. If you are using &quot;simplisityStartUp&quot; then this should be defined in there, however from a module which is not using simplisity panels you may need to define this on the element. It MUST be defined or any ajax calls will not work and may simply result is a reload of the page.</td>
		</tr>
		<tr>
			<td>s-uploadcmdurl</td>
			<td>Server side API url for uploading files. In some cases a different API is preferred for uploading files, due to the different nature of the post you can use a different API endpoint. This attribute is only valid on the &quot;simplisity_fileupload&quot; class method. If it is not defined then the normal &quot;s-cmdurl&quot; is used.</td>
		</tr>
		<tr>
			<td>s-cmd</td>
			<td>API command.</td>
		</tr>
		<tr>
			<td>s-fields</td>
			<td>Paramater fields that can be passed to the API. This is a json string in the format of &#39;{&quot;name&quot;:&quot;value&quot;,&quot;name&quot;:&quot;value&quot;,&quot;name&quot;:&quot;value&quot;}&#39;. Any number of parameters can be passed.</td>
		</tr>
		<tr>
			<td>s-itemid</td>
			<td>Identify records in list. Used for sorting and selecting.</td>
		</tr>
		<tr>
			<td>s-post</td>
			<td>The JQuery selector of an element that will be passed to the server. Simplisity takes ALL input fields in the selected html element and posts to the server, which can then process the data. If s-fields and s-post are defined both sets of data are passed to the server.</td>
		</tr>
		<tr>
			<td>s-list</td>
			<td>The JQuery selector of repeating data which will be past to server as a list. The value can be a csv of list classes used on the page, each row should have the class assigned to the parent/enclosing element. If you want to save a list to the DB then this should be on the save button, it will then be passed to the server along with the s-post element. It can be read by using <simplisityinfo>.GetList(<i>list name</i>) and is returned as a List<simplisityinfo>.</simplisityinfo></simplisityinfo></td>
		</tr>
		<tr>
			<td>s-return</td>
			<td>The JQuery selector of the return element. Any data returned from the server will be added/replace to this html element content. If not specified, this will default to &quot;#simplisity_startpanel&quot;. If &quot;document&quot; is used, the entire page is replace. (s-return=&quot;document&quot;)</td>
		</tr>
		<tr>
			<td>s-append</td>
			<td>Specifies that any return data will be added to the s-return element. (&#39;true&#39; or &#39;false&#39;)</td>
		</tr>
		<tr>
			<td>s-before</td>
			<td>The name of a js function to be activated before the API call is made.</td>
		</tr>
		<tr>
			<td>s-after</td>
			<td>The name of a js function to be activated after the API call is made.</td>
		</tr>
		<tr>
			<td>s-hideloader</td>
			<td>Hide the client side loader after the server API call. Default = &#39;true&#39;. This is used when you need to stop flicker because of multiple calls before processing is completed.</td>
		</tr>
		<tr>
			<td>s-showloader</td>
			<td>Shows or hides the client side loader before the server API call. Default = &#39;true&#39;.</td>
		</tr>
		<tr>
			<td>s-recylebin</td>
			<td>Specify the recycle bin when a list element or table row is removed. This must be on both the remove button and the undo button.</td>
		</tr>
		<tr>
			<td>s-removelist</td>
			<td>The JQuery selector of the removed element. This is used to move the list element into and out of the recycle bin. It should be placed on the removeitem button and the undo button. This is the li[s-index] or tr[s-index] parent of the removed button.</td>
		</tr>
		<tr>
			<td>s-confirm</td>
			<td>Confirm message of &quot;simplisity_confirmclick&quot;</td>
		</tr>
		<tr>
			<td>s-regexpr</td>
			<td>Regular Expression used to limit file type upload. This is used only on the &quot;simplisity_fileupload&quot; class element. If not specified the default is used. &#39;/(\.|\/)(gif|jpe?g|png|pdf)$/i&#39;</td>
		</tr>
		<tr>
			<td>s-maxfilesize</td>
			<td>Used to limit file size on upload. This is used only on the &quot;simplisity_fileupload&quot; class element. If not specified the default is used. 5000000000 [5GB]</td>
		</tr>
		<tr>
			<td>s-maxchuncksize</td>
			<td>Used to define the upload chuck size, for uploading large files. This is used only on the &quot;simplisity_fileupload&quot; class element. If not specified the default is used. 10000000 [10MB]</td>
		</tr>
		<tr>
			<td>s-dropdownlist</td>
			<td>Used to link a dropdown to another field. If used the server will return a JSON object. This can be used to populated the dropdownlist when an element changes. The JSON return format shoud be {listkey:[&#39;1&#39;,&#39;2&#39;,&#39;3&#39;],listvalue:[&#39;1&#39;,&#39;2&#39;,&#39;3&#39;]}</td>
		</tr>
		<tr>
			<td><i>s-index</i></td>
			<td>This is an attribute which is automatically added to elements in a list, so Simplisity can identify them.</td>
		</tr>
		<tr>
			<td><i>s-update</i></td>
			<td>INPUT FIELD: This attribute is optional for all input fields. There are 3 possible values: <b>s-update=&quot;save&quot;</b> the server will deal with the value as a normal non-localized value. This is the same as if no s-update attribute was added. <b>s-update=&quot;lang&quot;</b> the server will deal with the value as a localized value. <b>s-update=&quot;ignore&quot;</b> the value will be ignored.</td>
		</tr>
		<tr>
			<td><i>s-datatype</i></td>
			<td>INPUT FIELD: Datatype of the field data. &quot;email&quot;,&quot;date&quot;,&quot;double&quot;,&quot;html&quot;,&quot;coded&quot;,&quot;int&quot;. All other data type are dealt with as string.</td>
		</tr>
		<tr>
			<td><i>s-reload</i></td>
			<td>&#39;true&#39; or &#39;false&#39;. By default an image or document upload will trigger a reload of the page. In some situations this is not required (when ajax return updates the page), so the reload can be stopped by using s-reload=&#39;false&#39;. Default is &#39;false&#39;.</td>
		</tr>
		<tr>
			<td><i>s-stop</i></td>
			<td>Stop Call. If you want to stop the call to the server you can create an attribute with a value of &#39;stop&#39; on the call element, using jQuery or JS. This is usually used for validation, where the s-before function has found a problem and wants to stop the call to the server. Simplisity will clear the s-stop when the call is cancelled.
			<div class="w3-code">$(&#39;.myselectionclass&#39;).attr(&#39;s-stop&#39;,&#39;stop&#39;)</div>
			</td>
		</tr>
		<tr>
			<td><i>s-xpath</i></td>
			<td>Sets the xpath for data in the XML. This is usually only used if you have a html input which saves data back to the server.</td>
		</tr>
		<tr>
			<td><i>s-returntype</i></td>
			<td>If the server is returning a json object we can tell simplisity to convert it to a string. Usually this is used with the &quot;s-after&quot; command attribute class so a JS action can be performed on the json string. The data is still returned to the &quot;s-return&quot; location as a json string.
			<div class="w3-code">s-returntype=&#39;json&#39;</div>
			</td>
		</tr>
		<tr>
			<td><i>s-sessionfield</i></td>
			<td>This is a CSV list of jQuery selectors that should be placed into sessionStorage.
			<div class="w3-code">s-sessionfield=&#39;#searchtext,#pagesize,#orderbyref&#39;</div>
			</td>
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

<div class="w3-row-padding">
<div>&nbsp;</div>
</div>
</div>
