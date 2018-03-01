---
UID: NC:wdfwmi.EVT_WDF_WMI_PROVIDER_FUNCTION_CONTROL
title: EVT_WDF_WMI_PROVIDER_FUNCTION_CONTROL
author: windows-driver-content
description: A driver's EvtWmiProviderFunctionControl callback function enables and disables the driver's support for collecting data and sending events for a specified WMI data provider.
old-location: wdf\evtwmiproviderfunctioncontrol.htm
old-project: wdf
ms.assetid: 89b48747-d3aa-48c7-825c-94545f378f07
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: DFWMIRef_2beaafe2-cb59-49cb-85dc-6ea2beff1b1e.xml, EVT_WDF_WMI_PROVIDER_FUNCTION_CONTROL, EvtWmiProviderFunctionControl, EvtWmiProviderFunctionControl callback function, kmdf.evtwmiproviderfunctioncontrol, wdf.evtwmiproviderfunctioncontrol, wdfwmi/EvtWmiProviderFunctionControl
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: wdfwmi.h
req.include-header: Wdf.h
req.target-type: Universal
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 1.0
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
req.irql: PASSIVE_LEVEL
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	UserDefined
api_location:
-	WdfWMI.h
api_name:
-	EvtWmiProviderFunctionControl
product: Windows
targetos: Windows
req.typenames: WDF_USB_REQUEST_COMPLETION_PARAMS, *PWDF_USB_REQUEST_COMPLETION_PARAMS
req.product: Windows 10 or later.
---

# EVT_WDF_WMI_PROVIDER_FUNCTION_CONTROL callback


## -description


<p class="CCE_Message">[Applies to KMDF only]

A driver's <i>EvtWmiProviderFunctionControl</i> callback function enables and disables the driver's support for collecting data and sending events for a specified WMI data provider.


## -prototype


````
EVT_WDF_WMI_PROVIDER_FUNCTION_CONTROL EvtWmiProviderFunctionControl;

NTSTATUS EvtWmiProviderFunctionControl(
  _In_ WDFWMIPROVIDER           WmiProvider,
  _In_ WDF_WMI_PROVIDER_CONTROL Control,
  _In_ BOOLEAN                  Enable
)
{ ... }
````


## -parameters




### -param WmiProvider [in]

A handle to a WMI provider object.


### -param Control [in]

A <a href="..\wdfwmi\ne-wdfwmi-_wdf_wmi_provider_control.md">WDF_WMI_PROVIDER_CONTROL</a>-typed value that identifies a capability that the driver must enable or disable.


### -param Enable [in]

A Boolean value that, if <b>TRUE</b>, indicates that the driver must enable the capability that <i>Control</i> specifies. If <b>FALSE</b>, the driver must disable the capability.


## -returns



The <i>EvtWmiProviderFunctionControl</i> callback function must return STATUS_SUCCESS if the operation succeeds. Otherwise, it must return a status value for which <a href="https://msdn.microsoft.com/fe823930-e3ff-4c95-a640-bb6470c95d1d">NT_SUCCESS</a>(<i>status</i>) equals <b>FALSE</b>. 




## -remarks



To register an <i>EvtWmiProviderFunctionControl</i> callback function, your driver must place the function's address in a <a href="..\wdfwmi\ns-wdfwmi-_wdf_wmi_provider_config.md">WDF_WMI_PROVIDER_CONFIG</a> structure before it calls <a href="..\wdfwmi\nf-wdfwmi-wdfwmiprovidercreate.md">WdfWmiProviderCreate</a>. 

If your driver sets the <b>WdfWmiProviderExpensive</b> flag in the <b>Flags</b> member of a WMI data provider's <a href="..\wdfwmi\ns-wdfwmi-_wdf_wmi_provider_config.md">WDF_WMI_PROVIDER_CONFIG</a> structure, and if the driver provides an <i>EvtWmiProviderFunctionControl</i> callback function, the framework calls the callback function when the driver should enable or disable its ability to collect WMI data. 

Instead of providing an <i>EvtWmiProviderFunctionControl</i> callback function, the driver can call <a href="..\wdfwmi\nf-wdfwmi-wdfwmiproviderisenabled.md">WdfWmiProviderIsEnabled</a> to find out if it should enable or disable collecting data.

For more information about the <i>EvtWmiProviderFunctionControl</i> callback function, see <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/supporting-wmi-in-kmdf-drivers">Supporting WMI in Framework-Based Drivers</a>.


#### Examples

To define an <i>EvtWmiProviderFunctionControl</i> callback function, you must first provide a function declaration that identifies the type of callback function you’re defining. Windows provides a set of callback function types for drivers. Declaring a function using the callback function types helps <a href="https://msdn.microsoft.com/2F3549EF-B50F-455A-BDC7-1F67782B8DCA">Code Analysis for Drivers</a>, <a href="https://msdn.microsoft.com/74feeb16-387c-4796-987a-aff3fb79b556">Static Driver Verifier</a> (SDV), and other verification tools find errors, and it’s a requirement for writing drivers for the Windows operating system.

For example, to define an <i>EvtWmiProviderFunctionControl</i> callback function that is named <i>MyWmiProviderFunctionControl</i>, use the <b>EVT_WDF_WMI_PROVIDER_FUNCTION_CONTROL</b> type as shown in this code example:

To define an <i>EvtWmiProviderFunctionControl</i> callback function that is named <b>MyWmiProviderFunctionControl</b>, you must first provide a function declaration that SDV and other verification tools require, as follows:

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>EVT_WDF_WMI_PROVIDER_FUNCTION_CONTROL  MyWmiProviderFunctionControl;</pre>
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
 MyWmiProviderFunctionControl (
    WDFWMIPROVIDER  WmiProvider,
    WDF_WMI_PROVIDER_CONTROL  Control,
    BOOLEAN  Enable
    )
  {...}</pre>
</td>
</tr>
</table></span></div>
The <b>EVT_WDF_WMI_PROVIDER_FUNCTION_CONTROL</b> function type is defined in the WdfWMI.h header file. To more accurately identify errors when you run the code analysis tools, be sure to add the _Use_decl_annotations_ annotation to your function definition. The _Use_decl_annotations_ annotation ensures that the annotations that are applied to the <b>EVT_WDF_WMI_PROVIDER_FUNCTION_CONTROL</b> function type in the header file are used. For more information about the requirements for function declarations, see <a href="https://msdn.microsoft.com/73a408ba-0219-4fde-8dad-ca330e4e67c3">Declaring Functions by Using Function Role Types for KMDF Drivers</a>. For information about _Use_decl_annotations_, see <a href="https://msdn.microsoft.com/en-US/library/c0aa268d-6fa3-4ced-a8c6-f7652b152e61">Annotating Function Behavior</a>.




## -see-also

<a href="..\wdfwmi\nc-wdfwmi-evt_wdf_wmi_instance_query_instance.md">EvtWmiInstanceQueryInstance</a>



<a href="..\wdfwmi\nf-wdfwmi-wdfwmiprovidercreate.md">WdfWmiProviderCreate</a>



<a href="..\wdfwmi\ne-wdfwmi-_wdf_wmi_provider_control.md">WDF_WMI_PROVIDER_CONTROL</a>



<a href="..\wdfwmi\nc-wdfwmi-evt_wdf_wmi_instance_set_instance.md">EvtWmiInstanceSetInstance</a>



<a href="..\wdfwmi\nc-wdfwmi-evt_wdf_wmi_instance_execute_method.md">EvtWmiInstanceExecuteMethod</a>



<a href="..\wdfwmi\nc-wdfwmi-evt_wdf_wmi_instance_set_item.md">EvtWmiInstanceSetItem</a>



<a href="..\wdfwmi\ns-wdfwmi-_wdf_wmi_provider_config.md">WDF_WMI_PROVIDER_CONFIG</a>



<a href="..\wdfwmi\nf-wdfwmi-wdfwmiproviderisenabled.md">WdfWmiProviderIsEnabled</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [wdf\wdf]:%20EVT_WDF_WMI_PROVIDER_FUNCTION_CONTROL callback function%20 RELEASE:%20(2/26/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

