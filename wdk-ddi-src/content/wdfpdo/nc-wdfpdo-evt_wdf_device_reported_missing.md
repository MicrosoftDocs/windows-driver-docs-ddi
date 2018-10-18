---
UID: NC:wdfpdo.EVT_WDF_DEVICE_REPORTED_MISSING
title: EVT_WDF_DEVICE_REPORTED_MISSING
author: windows-driver-content
description: A bus driver's EvtDeviceReportedMissing event callback function informs the driver that the framework has reported the physical device object (PDO) missing to the Plug and Play manager.
old-location: wdf\evtdevicereportedmissing.htm
tech.root: wdf
ms.assetid: F64E2FFD-229F-4447-94C2-A5403E7893B7
ms.date: 2/26/2018
ms.keywords: EVT_WDF_DEVICE_REPORTED_MISSING, EVT_WDF_DEVICE_REPORTED_MISSING callback, EvtDeviceReportedMissing, EvtDeviceReportedMissing callback function, kmdf.evtdevicereportedmissing, wdf.evtdevicereportedmissing, wdfpdo/EvtDeviceReportedMissing
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
product:
- Windows
targetos: Windows
req.typenames: 
---

# EVT_WDF_DEVICE_REPORTED_MISSING callback function


## -description


<p class="CCE_Message">[Applies to KMDF only]</p>


   A bus driver's <i>EvtDeviceReportedMissing</i> event callback function informs the driver that the framework has reported the physical device object (PDO) missing to the Plug and Play manager.


## -parameters




### -param Device [in]

A handle to a framework device object.


## -returns



This callback function does not return a value.




## -remarks



Framework-based bus drivers can provide an <i>EvtDeviceReportedMissing</i> callback function. To register this callback function, the bus driver must call <a href="https://msdn.microsoft.com/library/windows/hardware/ff548805">WdfPdoInitSetEventCallbacks</a>.

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
The <b>EVT_WDF_DEVICE_REPORTED_MISSING</b> function type is defined in the Wdfpdo.h header file. To more accurately identify errors when you run the code analysis tools, be sure to add the _Use_decl_annotations_ annotation to your function definition. The _Use_decl_annotations_ annotation ensures that the annotations that are applied to the <b>EVT_WDF_DEVICE_REPORTED_MISSING</b> function type in the header file are used. For more information about the requirements for function declarations, see <a href="https://msdn.microsoft.com/73a408ba-0219-4fde-8dad-ca330e4e67c3">Declaring Functions by Using Function Role Types for KMDF Drivers</a>. For information about _Use_decl_annotations_, see <a href="https://msdn.microsoft.com/library/c0aa268d-6fa3-4ced-a8c6-f7652b152e61">Annotating Function Behavior</a>.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff548805">WdfPdoInitSetEventCallbacks</a>
 

 

