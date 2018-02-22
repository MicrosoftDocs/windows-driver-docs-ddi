---
UID: NC:gpioclx.GPIO_CLIENT_QUERY_SET_CONTROLLER_INFORMATION
title: GPIO_CLIENT_QUERY_SET_CONTROLLER_INFORMATION
author: windows-driver-content
description: The CLIENT_QuerySetControllerInformation event callback function queries the general-purpose I/O (GPIO) controller driver for the specified set of attributes of the GPIO controller.
old-location: gpio\client_querysetcontrollerinformation.htm
old-project: GPIO
ms.assetid: 898AE09B-2C92-4229-9A86-901CDA98CFAA
ms.author: windowsdriverdev
ms.date: 2/15/2018
ms.keywords: GPIO.client_querysetcontrollerinformation, CLIENT_QuerySetControllerInformation callback function [Parallel Ports], CLIENT_QuerySetControllerInformation, GPIO_CLIENT_QUERY_SET_CONTROLLER_INFORMATION, GPIO_CLIENT_QUERY_SET_CONTROLLER_INFORMATION, gpioclx/CLIENT_QuerySetControllerInformation
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: gpioclx.h
req.include-header: 
req.target-type: Desktop
req.target-min-winverclnt: Supported starting with Windows 8.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: Called at PASSIVE_LEVEL.
topictype:
-	APIRef
-	kbSyntax
apitype:
-	UserDefined
apilocation:
-	Gpioclx.h
apiname:
-	CLIENT_QuerySetControllerInformation
product: Windows
targetos: Windows
req.typenames: "*PGNSS_V2UPL_NI_INFO, GNSS_V2UPL_NI_INFO"
---

# GPIO_CLIENT_QUERY_SET_CONTROLLER_INFORMATION callback


## -description


The <i>CLIENT_QuerySetControllerInformation</i> event callback function queries the general-purpose I/O (GPIO) controller driver for the specified set of attributes of the GPIO controller.


## -prototype


````
GPIO_CLIENT_QUERY_SET_CONTROLLER_INFORMATION CLIENT_QuerySetControllerInformation;

NTSTATUS CLIENT_QuerySetControllerInformation(
  _In_      PVOID                                           Context,
  _In_      PCLIENT_CONTROLLER_QUERY_SET_INFORMATION_INPUT  InputBuffer,
  _Out_opt_ PCLIENT_CONTROLLER_QUERY_SET_INFORMATION_OUTPUT OutputBuffer
)
{ ... }
````


## -parameters




### -param Context [in]

A pointer to the GPIO controller driver's <a href="https://msdn.microsoft.com/4BE99C71-9BA6-44E3-A54F-DE8C3440A474">device context</a>.


### -param InputBuffer [in]

A pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/hh698238">CLIENT_CONTROLLER_QUERY_SET_INFORMATION_INPUT</a> structure that describes the type of attributes that the caller is requesting.


### -param OutputBuffer [out, optional]

An optional pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/hh698239">CLIENT_CONTROLLER_QUERY_SET_INFORMATION_OUTPUT</a> structure into which the function writes the values of the requested attributes.


## -returns



The <i>CLIENT_QuerySetControllerInformation</i> function returns <b>STATUS_SUCCESS</b> if the call is successful. Possible return values include the following error code.

<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_NOT_SUPPORTED</b></dt>
</dl>
</td>
<td width="60%">
The function does not support the type of attributes that are being requested.

</td>
</tr>
</table>
 




## -remarks



The <b>RequestType</b> member of the <b>CLIENT_CONTROLLER_QUERY_SET_INFORMATION_INPUT</b> structure pointed to by <i>InputBuffer</i> specifies the type of attributes that are being requested. For a list of the types of attributes that can be requested, see <a href="https://msdn.microsoft.com/library/windows/hardware/hh698240">CLIENT_CONTROLLER_QUERY_SET_REQUEST_TYPE</a>.

Implementing a <i>CLIENT_QuerySetControllerInformation</i> function is optional. If a GPIO controller driver implements a <i>CLIENT_QuerySetControllerInformation</i> function, this function might support some types of attribute requests, but not support others. If the caller requests an attribute type that the function does not support, the function returns <b>STATUS_NOT_SUPPORTED</b>.


#### Examples

To define a <i>CLIENT_QuerySetControllerInformation</i> callback function, you must first provide a function declaration that identifies the type of callback function you're defining. Windows provides a set of callback function types for drivers. Declaring a function using the callback function types helps <a href="https://msdn.microsoft.com/2F3549EF-B50F-455A-BDC7-1F67782B8DCA">Code Analysis for Drivers</a>, <a href="https://msdn.microsoft.com/74feeb16-387c-4796-987a-aff3fb79b556">Static Driver Verifier</a> (SDV), and other verification tools find errors, and it's a requirement for writing drivers for the Windows operating system.

For example, to define a <i>CLIENT_QuerySetControllerInformation</i> callback function that is named <code>MyEvtGpioQuerySetControllerInformation</code>, use the GPIO_CLIENT_QUERY_SET_CONTROLLER_INFORMATION function type, as shown in this code example:

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>GPIO_CLIENT_QUERY_SET_CONTROLLER_INFORMATION MyEvtGpioQuerySetControllerInformation;</pre>
</td>
</tr>
</table></span></div>
Then, implement your callback function as follows:

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>_Use_decl_annotations_
NTSTATUS
  MyEvtGpioQuerySetControllerInformation(
    PVOID Context,
    PCLIENT_CONTROLLER_QUERY_SET_INFORMATION_INPUT InputBuffer,
    PCLIENT_CONTROLLER_QUERY_SET_INFORMATION_OUTPUT OutputBuffer
    )
{ ... }</pre>
</td>
</tr>
</table></span></div>
The GPIO_CLIENT_QUERY_SET_CONTROLLER_INFORMATION function type is defined in the Gpioclx.h header file. To more accurately identify errors when you run the code analysis tools, be sure to add the _Use_decl_annotations_ annotation to your function definition. The _Use_decl_annotations_ annotation ensures that the annotations that are applied to the GPIO_CLIENT_QUERY_SET_CONTROLLER_INFORMATION function type in the header file are used. For more information about the requirements for function declarations, see <a href="https://msdn.microsoft.com/73a408ba-0219-4fde-8dad-ca330e4e67c3">Declaring Functions by Using Function Role Types for KMDF Drivers</a>. For more information about _Use_decl_annotations_, see <a href="http://go.microsoft.com/fwlink/p/?LinkId=286697">Annotating Function Behavior</a>.

<div class="code"></div>



## -see-also

<a href="https://msdn.microsoft.com/library/windows/hardware/hh698240">CLIENT_CONTROLLER_QUERY_SET_REQUEST_TYPE</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh698238">CLIENT_CONTROLLER_QUERY_SET_INFORMATION_INPUT</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh698239">CLIENT_CONTROLLER_QUERY_SET_INFORMATION_OUTPUT</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [GPIO\parports]:%20CLIENT_QuerySetControllerInformation callback function%20 RELEASE:%20(2/15/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

