---
UID: NC:wdfwmi.EVT_WDF_WMI_INSTANCE_SET_ITEM
title: EVT_WDF_WMI_INSTANCE_SET_ITEM
author: windows-driver-content
description: A driver's EvtWmiInstanceSetItem callback function sets a single item of a WMI data provider's instance data to a value that a WMI client supplies.
old-location: wdf\evtwmiinstancesetitem.htm
old-project: wdf
ms.assetid: 3011d92c-b12b-4240-8a4e-aa039ab8e053
ms.author: windowsdriverdev
ms.date: 2/20/2018
ms.keywords: wdf.evtwmiinstancesetitem, EvtWmiInstanceSetItem callback function, EvtWmiInstanceSetItem, EVT_WDF_WMI_INSTANCE_SET_ITEM, EVT_WDF_WMI_INSTANCE_SET_ITEM, wdfwmi/EvtWmiInstanceSetItem, DFWMIRef_edfeada6-2e85-42a5-9a28-6a6fb99a1c46.xml, kmdf.evtwmiinstancesetitem
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	UserDefined
apilocation:
-	WdfWMI.h
apiname:
-	EvtWmiInstanceSetItem
product: Windows
targetos: Windows
req.typenames: WDF_USB_REQUEST_COMPLETION_PARAMS, *PWDF_USB_REQUEST_COMPLETION_PARAMS
req.product: Windows 10 or later.
---

# EVT_WDF_WMI_INSTANCE_SET_ITEM callback


## -description


<p class="CCE_Message">[Applies to KMDF only]

A driver's <i>EvtWmiInstanceSetItem</i> callback function sets a single item of a WMI data provider's instance data to a value that a WMI client supplies.


## -prototype


````
EVT_WDF_WMI_INSTANCE_SET_ITEM EvtWmiInstanceSetItem;

NTSTATUS EvtWmiInstanceSetItem(
  _In_ WDFWMIINSTANCE WmiInstance,
  _In_ ULONG          DataItemId,
  _In_ ULONG          InBufferSize,
  _In_ PVOID          InBuffer
)
{ ... }
````


## -parameters




### -param WmiInstance [in]

A handle to a WMI instance object.


### -param DataItemId [in]

A value that identifies an item of data for a provider instance. This value corresponds to the <a href="https://msdn.microsoft.com/e2d281b3-913c-43ad-921c-80dc8be09aa0">WmiDataId</a> value that is specified in the provider's MOF file.


### -param InBufferSize [in]

The size, in bytes, of the input buffer that <i>InBuffer</i> points to.


### -param InBuffer [in]

A pointer to the input buffer.


## -returns



The <i>EvtWmiInstanceSetItem</i> callback function must return STATUS_SUCCESS if the operation succeeds. Otherwise, this function must return a status value for which <a href="https://msdn.microsoft.com/fe823930-e3ff-4c95-a640-bb6470c95d1d">NT_SUCCESS</a>(<i>status</i>) equals <b>FALSE</b>. If the input buffer that the <i>InBuffer</i> parameter points to is too small to contain all of the data that the driver expects, the callback function must return STATUS_WMI_SET_FAILURE.




## -remarks



To register an <i>EvtWmiInstanceSetItem</i> callback function, your driver must place the function's address in a <a href="..\wdfwmi\ns-wdfwmi-_wdf_wmi_instance_config.md">WDF_WMI_INSTANCE_CONFIG</a> structure before calling <a href="..\wdfwmi\nf-wdfwmi-wdfwmiinstancecreate.md">WdfWmiInstanceCreate</a>. 

The framework does not synchronize calls to a driver's WMI event callback functions with each other or with any of the driver's other event callback functions. If an <i>EvtWmiInstanceSetItem</i> callback function's data is dynamic and shared with other callback functions, your driver can use the framework's <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/using-framework-locks">wait locks or spin locks</a> to synchronize access to the data.

For more information about the <i>EvtWmiInstanceSetItem</i> callback function, see <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/supporting-wmi-in-kmdf-drivers">Supporting WMI in Framework-Based Drivers</a>.


#### Examples

To define an <i>EvtWmiInstanceSetItem</i> callback function, you must first provide a function declaration that identifies the type of callback function you’re defining. Windows provides a set of callback function types for drivers. Declaring a function using the callback function types helps <a href="https://msdn.microsoft.com/2F3549EF-B50F-455A-BDC7-1F67782B8DCA">Code Analysis for Drivers</a>, <a href="https://msdn.microsoft.com/74feeb16-387c-4796-987a-aff3fb79b556">Static Driver Verifier</a> (SDV), and other verification tools find errors, and it’s a requirement for writing drivers for the Windows operating system.

For example, to define an <i>EvtWmiInstanceSetItem</i> callback function that is named <i>MyWmiInstanceSetItem</i>, use the <b>EVT_WDF_WMI_INSTANCE_SET_ITEM</b> type as shown in this code example:

To define an <i>EvtWmiInstanceSetItem</i> callback function that is named <b>MyWmiInstanceSetItem</b>, you must first provide a function declaration that SDV and other verification tools require, as follows:

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>EVT_WDF_WMI_INSTANCE_SET_ITEM  MyWmiInstanceSetItem;</pre>
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
 MyWmiInstanceSetItem (
    WDFWMIINSTANCE  WmiInstance,
    ULONG  DataItemId,
    ULONG  InBufferSize,
    PVOID  InBuffer
    )
  {...}</pre>
</td>
</tr>
</table></span></div>
The <b>EVT_WDF_WMI_INSTANCE_SET_ITEM</b> function type is defined in the WdfWMI.h header file. To more accurately identify errors when you run the code analysis tools, be sure to add the _Use_decl_annotations_ annotation to your function definition. The _Use_decl_annotations_ annotation ensures that the annotations that are applied to the <b>EVT_WDF_WMI_INSTANCE_SET_ITEM</b> function type in the header file are used. For more information about the requirements for function declarations, see <a href="https://msdn.microsoft.com/73a408ba-0219-4fde-8dad-ca330e4e67c3">Declaring Functions by Using Function Role Types for KMDF Drivers</a>. For information about _Use_decl_annotations_, see <a href="https://msdn.microsoft.com/en-US/library/c0aa268d-6fa3-4ced-a8c6-f7652b152e61">Annotating Function Behavior</a>.




## -see-also

<a href="..\wdfwmi\nc-wdfwmi-evt_wdf_wmi_provider_function_control.md">EvtWmiProviderFunctionControl</a>



<a href="..\wdfwmi\nf-wdfwmi-wdfwmiinstancecreate.md">WdfWmiInstanceCreate</a>



<a href="..\wdfwmi\ns-wdfwmi-_wdf_wmi_instance_config.md">WDF_WMI_INSTANCE_CONFIG</a>



<a href="..\wdfwmi\nc-wdfwmi-evt_wdf_wmi_instance_query_instance.md">EvtWmiInstanceQueryInstance</a>



<a href="..\wdfwmi\nc-wdfwmi-evt_wdf_wmi_instance_execute_method.md">EvtWmiInstanceExecuteMethod</a>



<a href="..\wdfwmi\nc-wdfwmi-evt_wdf_wmi_instance_set_instance.md">EvtWmiInstanceSetInstance</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [wdf\wdf]:%20EVT_WDF_WMI_INSTANCE_SET_ITEM callback function%20 RELEASE:%20(2/20/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

