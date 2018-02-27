---
UID: NC:wdfpdo.EVT_WDF_DEVICE_REPORTED_MISSING
title: EVT_WDF_DEVICE_REPORTED_MISSING
author: windows-driver-content
description: A bus driver's EvtDeviceReportedMissing event callback function informs the driver that the framework has reported the physical device object (PDO) missing to the Plug and Play manager.
old-location: wdf\evtdevicereportedmissing.htm
old-project: wdf
ms.assetid: F64E2FFD-229F-4447-94C2-A5403E7893B7
ms.author: windowsdriverdev
ms.date: 2/20/2018
ms.keywords: EVT_WDF_DEVICE_REPORTED_MISSING, EvtDeviceReportedMissing, EvtDeviceReportedMissing callback function, kmdf.evtdevicereportedmissing, wdf.evtdevicereportedmissing, wdfpdo/EvtDeviceReportedMissing
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: wdfpdo.h
req.include-header: Wdf.h
req.target-type: Universal
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 1.11
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
-	Wdfpdo.h
api_name:
-	EvtDeviceReportedMissing
product: Windows
targetos: Windows
req.typenames: WDF_OBJECT_CONTEXT_TYPE_INFO, *PWDF_OBJECT_CONTEXT_TYPE_INFO
req.product: Windows 10 or later.
---

# EVT_WDF_DEVICE_REPORTED_MISSING callback


## -description


<p class="CCE_Message">[Applies to KMDF only]


   A bus driver's <i>EvtDeviceReportedMissing</i> event callback function informs the driver that the framework has reported the physical device object (PDO) missing to the Plug and Play manager.


## -prototype


````
EVT_WDF_DEVICE_REPORTED_MISSING EvtDeviceReportedMissing;

void EvtDeviceReportedMissing(
  _In_ WDFDEVICE Device
)
{ ... }
````


## -parameters




### -param Device [in]

A handle to a framework device object.


## -returns



This callback function does not return a value.




## -remarks



Framework-based bus drivers can provide an <i>EvtDeviceReportedMissing</i> callback function. To register this callback function, the bus driver must call <a href="..\wdfpdo\nf-wdfpdo-wdfpdoinitseteventcallbacks.md">WdfPdoInitSetEventCallbacks</a>.

The framework calls <i>EvtDeviceReportedMissing</i> when processing a <a href="https://msdn.microsoft.com/library/windows/hardware/ff551670">IRP_MN_QUERY_DEVICE_RELATIONS</a> request for <b>BusRelations</b> from the PnP manager.

Most framework-based bus drivers do not need to provide this callback function.


#### Examples

To define an <i>EvtDeviceReportedMissing</i> callback function, you must first provide a function declaration that identifies the type of callback function you’re defining. Windows provides a set of callback function types for drivers. Declaring a function using the callback function types helps <a href="https://msdn.microsoft.com/2F3549EF-B50F-455A-BDC7-1F67782B8DCA">Code Analysis for Drivers</a>, <a href="https://msdn.microsoft.com/74feeb16-387c-4796-987a-aff3fb79b556">Static Driver Verifier</a> (SDV), and other verification tools find errors, and it’s a requirement for writing drivers for the Windows operating system.

For example, to define an <i>EvtDeviceReportedMissing</i> callback function that is named <i>MyDeviceReportedMissing</i>, use the <b>EVT_WDF_DEVICE_REPORTED_MISSING</b> type as shown in this code example:

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>EVT_WDF_DEVICE_REPORTED_MISSING  MyDeviceReportedMissing;</pre>
</td>
</tr>
</table></span></div>
Then, implement your callback function:

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>_Use_decl_annotations_
VOID
 MyDeviceReportedMissing (
    WDFDEVICE  Device,
    )
  {...}</pre>
</td>
</tr>
</table></span></div>
The <b>EVT_WDF_DEVICE_REPORTED_MISSING</b> function type is defined in the Wdfpdo.h header file. To more accurately identify errors when you run the code analysis tools, be sure to add the _Use_decl_annotations_ annotation to your function definition. The _Use_decl_annotations_ annotation ensures that the annotations that are applied to the <b>EVT_WDF_DEVICE_REPORTED_MISSING</b> function type in the header file are used. For more information about the requirements for function declarations, see <a href="https://msdn.microsoft.com/73a408ba-0219-4fde-8dad-ca330e4e67c3">Declaring Functions by Using Function Role Types for KMDF Drivers</a>. For information about _Use_decl_annotations_, see <a href="https://msdn.microsoft.com/en-US/library/c0aa268d-6fa3-4ced-a8c6-f7652b152e61">Annotating Function Behavior</a>.




## -see-also

<a href="..\wdfpdo\nf-wdfpdo-wdfpdoinitseteventcallbacks.md">WdfPdoInitSetEventCallbacks</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [wdf\wdf]:%20EVT_WDF_DEVICE_REPORTED_MISSING callback function%20 RELEASE:%20(2/20/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

