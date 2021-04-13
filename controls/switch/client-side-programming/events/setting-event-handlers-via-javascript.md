---
title: Setting Event Handlers via JavaScript
page_title: Setting Event Handlers via JavaScript - RadSwitch
description: Check our Web Forms article about Setting Event Handlers via JavaScript.
slug: switch/client-side-programming/events/setting-event-handlers-via-javascript
tags: setting,event,handlers,via,javascript
published: True
position: 1
---

# Setting Event Handlers via JavaScript

**RadSwitch** API exposes client-side methods to attach and detach functions to its event. They can be used as an alternative to the server-side properties for handling events. 

To handle the desired event, you can use the respective **add_<eventName>(handlerFunction)** to attach the desired handler (i.e., **add_clicked** for the clicked event), where the parameter *handlerFunction* should be of type **function**. To remove the handler that has been added previously, the respective **remove_<eventName>(handlerFunction)** should be used.

The next three examples show how to add and remove handlers on the client:

>caption Example 1: Adding a named (non-anonymous) JavaScript click handler to RadSwitch.

````ASP.NET
<script type="text/javascript">
	function Click(switchObj, args)
	{
		alert("switch was clicked");
	}
	function addHandler()
	{
		var switchObj = $find("<%=RadSwitch1.ClientID %>");
		switchObj.add_clicked(Click);
	}
</script>
````

>caption Example 2: Adding an anonymous JavaScript click handler to RadSwitch.

````ASP.NET
<script type="text/javascript">
	function Click(switchObj, args, arg1)
	{
		alert("switch was clicked. arg1: " + arg1);
	}
	function addHandler()
	{
		var switchObj = $find("<%=RadSwitch1.ClientID %>");
		switchObj.add_clicked(function (switchObj, args) { Click(switchObj, args, "Value1") });
	}
</script>
````

>caption Example 3: Removing the JavaScript click handler of a RadSwitch.

````JavaScript
function removeEvents()
{
    var switchObj = $find("<%= RadSwitch1.ClientID %>");
    switchObj.remove_click(Click);
}
````

>caption Table 1: Available add/remove methods for handling client-side events.

| Name | Description |
| ------ | ------ |
| **add_load** |The name of the JavaScript function called when the control loads.|
| **remove_load** |Removes a handler for the load event.|
| **add_clicking** |The name of the JavaScript function called when the RadSwitch control is clicked.|
| **remove_clicking** |Removes a handler for the clicking event.|
| **add_checkedChanging** |The name of the JavaScript function called before the checked state of the switch is changed.|
| **remove_checkedChanging** |Removes a handler for the checkedChanging event.|
| **add_checkedChanged** |The name of the JavaScript function called when the checked state of the switch is changed.|
| **remove_checkedChanged** |Removes a handler for the checkedChanged event.|
| **add_clicked** |The name of the JavaScript function called when the RadSwitch control is clicked.|
| **remove_clicked** |Removes a handler for the clicked event.|
| **add_mouseOver** |The name of the JavaScript function called when the mouse hovers over the control.|
| **remove_mouseOver** |Removes a handler for the mouseOver event.|
| **add_mouseOut** |The name of the JavaScript function when the mouse leaves the control.|
| **remove_mouseOut** |Removes a handler for the mouseOut event.|

## See Also

 * [Switch Object]({%slug switch/client-side-programming/switch-object%})
 
 * [Events Overview]({%slug switch/client-side-programming/events/overview%})
 
 * [Switch Object]({%slug switch/client-side-programming/switch-object%})
 
 * [OnClientLoad]({%slug switch/client-side-programming/events/onclientload%})
 
 * [OnClientClicking]({%slug switch/client-side-programming/events/onclientclicking%})
 
 * [OnClientClicked]({%slug switch/client-side-programming/events/onclientclicked%})
 
 * [OnClientCheckedChanging]({%slug switch/client-side-programming/events/onclientcheckedchanging%})

 * [OnClientCheckedChanged]({%slug switch/client-side-programming/events/onclientcheckedchanged%})
 
 * [OnClientMouseOver]({%slug switch/client-side-programming/events/onclientmouseover%})
 
 * [OnClientMouseOut]({%slug switch/client-side-programming/events/onclientmouseout%})



