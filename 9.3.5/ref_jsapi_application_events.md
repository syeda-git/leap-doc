# Application Events 

This topic describes the Application Events, and their parameters when using JavaScript™ API in HCL Leap.

There is one event at the application level in **Settings** \> **Events** that is called from the context of the application, regardless of what form is going to be displayed.

Table 1. JavaScript™ objects available in application events

|Variable|Full name|Description|Example|Type|
|--------|---------|-----------|-------|----|
|app|Application object|Contains functions for accessing global general information|`app.getCurrentUser();`|GUI|


Table 2. Application Events
<table class="table-wrap">
<thead>
<tr>
<th width="100">Event</th><th>Description</th><th>Example</th>
</tr>
</thead>
<tbody>
<tr>
<td>onStart</td>
<td>Called once when the browser is first loaded with your application. You can access the form’s interface model for attaching programmatic events. However, nothing else on the form is modified because the forms have not been displayed to the user, nor have they had any data attached.
<td>Create a global function for later use:<br>

```JavaScript
app.getSharedData().messageBox = function(
{
   alert("Warning: " + message);
};
```
<br>
Register a function to be called that shows a section when a Service finishes:<br>

```JavaScript
var form = app.getForm('F_Form1');
var serviceConfig = form.getServiceConfiguration('SC_ServiceConfig0');
serviceConfig.connectEvent('onCallFinished', function(success)
{
   form.getPage('P_Page1').F_Section1.setVisible(true);
}); 
```
</td>
</table>


**Parent topic: **[Running Custom JavaScript – Events](ref_jsapi_running_custom_js_events.md)

