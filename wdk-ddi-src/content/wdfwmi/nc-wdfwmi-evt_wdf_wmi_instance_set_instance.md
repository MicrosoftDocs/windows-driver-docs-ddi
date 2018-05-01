---
UID: NC:wdfwmi.EVT_WDF_WMI_INSTANCE_SET_INSTANCE
title: EVT_WDF_WMI_INSTANCE_SET_INSTANCE
author: windows-driver-content
description: A driver's EvtWmiInstanceSetInstance callback function sets all of a WMI data provider's instance data to values that a WMI client supplies.
old-location: wdf\evtwmiinstancesetinstance.htm
old-project: wdf
ms.assetid: defd33c5-90ae-40c9-9123-7c3de2c77f35
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: DFWMIRef_28837d36-7a7e-4468-adbc-826bf4c75ef0.xml, EVT_WDF_WMI_INSTANCE_SET_INSTANCE, EVT_WDF_WMI_INSTANCE_SET_INSTANCE callback, EvtWmiInstanceSetInstance, EvtWmiInstanceSetInstance callback function, kmdf.evtwmiinstancesetinstance, wdf.evtwmiinstancesetinstance, wdfwmi/EvtWmiInstanceSetInstance
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
-	EvtWmiInstanceSetInstance
product: Windows
targetos: Windows
req.typenames: 
---

# EVT_WDF_WMI_INSTANCE_SET_INSTANCE callback function


## -description


<p class="CCE_Message">[Applies to KMDF only]

A driver's <i>EvtWmiInstanceSetInstance</i> callback function sets all of a WMI data provider's instance data to values that a WMI client supplies.


## -parameters




### -param WmiInstance [in]

A handle to a WMI instance object.


### -param InBufferSize [in]

The size, in bytes, of the input buffer that <i>InBuffer</i> points to.


### -param InBuffer [in]

A pointer to the input buffer.


## -returns



The <i>EvtWmiInstanceSetInstance</i> callback function must return STATUS_SUCCESS if the operation succeeds. Otherwise, this function must return a status value for which <a href="https://msdn.microsoft.com/fe823930-e3ff-4c95-a640-bb6470c95d1d">NT_SUCCESS</a>(<i>status</i>) equals <b>FALSE</b>. If the input buffer that the <i>InBuffer</i> parameter points to is too small to contain all of the data that the driver expects, the callback function must return STATUS_WMI_SET_FAILURE.




## -remarks



To register an <i>EvtWmiInstanceSetInstance</i> callback function, your driver must place the function's address in a <a href="https://msdn.microsoft.com/library/windows/hardware/ff553058">WDF_WMI_INSTANCE_CONFIG</a> structure before calling <a href="https://msdn.microsoft.com/library/windows/hardware/ff551178">WdfWmiInstanceCreate</a>. 

The framework does not synchronize calls to a driver's WMI event callback functions with each other or with any of the driver's other event callback functions. If an <i>EvtWmiInstanceSetInstance</i> callback function's data is dynamic and shared with other callback functions, your driver can use the framework's <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/using-framework-locks">wait locks or spin locks</a> to synchronize access to the data.

For more information about the <i>EvtWmiInstanceSetInstance</i> callback function, see <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/supporting-wmi-in-kmdf-drivers">Supporting WMI in Framework-Based Drivers</a>.


#### Examples

To define an <i>EvtWmiInstanceSetInstance</i> callback function, you must first provide a function declaration that identifies the type of callback function you’re defining. Windows provides a set of callback function types for drivers. Declaring a function using the callback function types helps <a href="https://msdn.microsoft.com/2F3549EF-B50F-455A-BDC7-1F67782B8DCA">Code Analysis for Drivers</a>, <a href="https://msdn.microsoft.com/74feeb16-387c-4796-987a-aff3fb79b556">Static Driver Verifier</a> (SDV), and other verification tools find errors, and it’s a requirement for writing drivers for the Windows operating system.

For example, to define an <i>EvtWmiInstanceSetInstance</i> callback function that is named <i>MyWmiInstanceSetInstance</i>, use the <b>EVT_WDF_WMI_INSTANCE_SET_INSTANCE</b> type as shown in this code example:

To define an <i>EvtWmiInstanceSetInstance</i> callback function that is named <b>MyWmiInstanceSetInstance</b>, you must first provide a function declaration that SDV and other verification tools require, as follows:

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>EVT_WDF_WMI_INSTANCE_SET_INSTANCE  MyWmiInstanceSetInstance;</pre>
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
 MyWmiInstanceSetInstance (
    WDFWMIINSTANCE  WmiInstance,
    ULONG  InBufferSize,
    PVOID  InBuffer
    )
  {...}</pre>
</td>
</tr>
</table></span></div>
The <b>EVT_WDF_WMI_INSTANCE_SET_INSTANCE</b> function type is defined in the WdfWMI.h header file. To more accurately identify errors when you run the code analysis tools, be sure to add the _Use_decl_annotations_ annotation to your function definition. The _Use_decl_annotations_ annotation ensures that the annotations that are applied to the <b>EVT_WDF_WMI_INSTANCE_SET_INSTANCE</b> function type in the header file are used. For more information about the requirements for function declarations, see <a href="https://msdn.microsoft.com/73a408ba-0219-4fde-8dad-ca330e4e67c3">Declaring Functions by Using Function Role Types for KMDF Drivers</a>. For information about _Use_decl_annotations_, see <a href="https://msdn.microsoft.com/en-US/library/c0aa268d-6fa3-4ced-a8c6-f7652b152e61">Annotating Function Behavior</a>.




## -see-also




<a href="https://msdn.microsoft.com/b14de1d7-0df2-46d1-a3bd-c23f33d3ed75">EvtWmiInstanceExecuteMethod</a>



<a href="https://msdn.microsoft.com/13eed838-2943-4bb4-915f-6a84f0f95851">EvtWmiInstanceQueryInstance</a>



<a href="https://msdn.microsoft.com/3011d92c-b12b-4240-8a4e-aa039ab8e053">EvtWmiInstanceSetItem</a>



<a href="https://msdn.microsoft.com/89b48747-d3aa-48c7-825c-94545f378f07">EvtWmiProviderFunctionControl</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff553058">WDF_WMI_INSTANCE_CONFIG</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff551178">WdfWmiInstanceCreate</a>
 

 

