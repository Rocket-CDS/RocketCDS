---
layout: page
title: SimplisityJS
menubar: simplisityjs_menu
show_sidebar: false
---

# Class Events

<link href="https://www.w3schools.com/w3css/4/w3.css" rel="stylesheet" /><!-- Header -->
<div class="w3-container w3-margin-top">
<div class="w3-row-padding">
<p>Most operations for Simplisity are setup by applying a class or id onto a html element. Simplisity uses these class or id as instructions on what needs to be done.</p>

<table class="w3-table w3-bordered">
	<tbody>
		<tr class="">
			<th>Element ID</th>
			<th>&nbsp;</th>
		</tr>
		<tr>
			<td>simplisity_startpanel</td>
			<td>
			<p>Identifies a html START container to use as a simplisity panel. This will be the default panel and activated when &quot;simplisityStartUp&quot; is called. This must be the ID of the element.</p>

			<p>This element is the default return element if no &quot;s-return&quot; attribute is specified.</p>

			<p><strong>NOTE: The element MUST also have a &quot;simplisity_panel&quot; class specified, if you want it to activate on page load.</strong></p>
			</td>
		</tr>
	</tbody>
</table>

<table class="w3-table w3-bordered">
	<tbody>
		<tr class="">
			<th>Class Name</th>
			<th>&nbsp;</th>
		</tr>
		<tr>
			<td>simplisity_panel</td>
			<td>Identifies a html container to use as a simplisity panel. This will be activated when &quot;simplisityStartUp&quot; is called.</td>
		</tr>
		<tr>
			<td>simplisity_click</td>
			<td>Apply a Simplisity click event onto an element. If a &quot;href&quot; attribute exists, with the same domain, the browser url history will be updated.</td>
		</tr>
		<tr>
			<td>simplisity_confirmclick</td>
			<td>Apply a Simplisity click event onto an element, but ask for a confirmation popup. use &quot;s-confirm&quot; attribute to specify a message.</td>
		</tr>
		<tr>
			<td>simplisity_change</td>
			<td>Apply a Simplisity change event onto an element. This is usually used for dropdownlist, so something can be populated on selection.</td>
		</tr>		
		<tr>
			<td>simplisity_removegriditem</td>
			<td>Remove item from html div list element</td>
		</tr>
		<tr>
			<td>simplisity_removelistitem</td>
			<td>Remove item from html li list</td>
		</tr>
		<tr>
			<td>simplisity_removetablerow</td>
			<td>Remove row from html table</td>
		</tr>
		<tr>
			<td>simplisity_itemundo</td>
			<td>Undo Remove item from html li list</td>
		</tr>
		<tr>
			<td>simplisity_fileupload</td>
			<td>Identifies a file upload. This class should be on the input field with type=&#39;file&#39;</td>
		</tr>
		<tr>
			<td>simplisity_filedownload</td>
			<td>Identifies a download file link. This class should be on the <a> element and should have the &quot;s-fields&quot; and &quot;s-cmd&quot; attributes.</a></td>
		</tr>
		<tr>
			<td>simplisity_fadeout</td>
			<td>Any element with this event will fade out in 2 seconds, after the return from the server. Often used to display messages after a save and then fade them out.</td>
		</tr>
		<tr>
			<td>simplisity_sessionfield</td>
			<td>Specifies that the input element value should be taken from the browser sessionStorage to persist across page refresh. In is used with &quot;s-sessionfield&quot;, which identifies which fields should be saved to sessionStorage.</td>
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

<div id="documentationanchor43">&nbsp;</div>

