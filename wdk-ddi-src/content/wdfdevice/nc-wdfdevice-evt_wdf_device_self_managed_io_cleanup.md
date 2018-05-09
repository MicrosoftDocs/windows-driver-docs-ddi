---
UID: NC:wdfdevice.EVT_WDF_DEVICE_SELF_MANAGED_IO_CLEANUP
title: EVT_WDF_DEVICE_SELF_MANAGED_IO_CLEANUP
author: windows-driver-content
description: A driver's EvtDeviceSelfManagedIoCleanup event callback function handles deallocation activity for the device's self-managed I/O operations, after a device has been removed.
old-location: wdf\evtdeviceselfmanagediocleanup.htm
old-project: wdf
ms.assetid: 639ff3fd-ce38-417e-8fc4-a03ad259a5c8
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: DFDeviceObjectGeneralRef_73e3f47e-1f3d-4dee-9fb2-62acbb5aaea2.xml, EVT_WDF_DEVICE_SELF_MANAGED_IO_CLEANUP, EVT_WDF_DEVICE_SELF_MANAGED_IO_CLEANUP callback, EvtDeviceSelfManagedIoCleanup, EvtDeviceSelfManagedIoCleanup callback function, kmdf.evtdeviceselfmanagediocleanup, wdf.evtdeviceselfmanagediocleanup, wdfdevice/EvtDeviceSelfManagedIoCleanup
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: wdfdevice.h
req.include-header: Wdf.h
req.target-type: Universal
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 1.0
req.umdf-ver: 2.0
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
-	Wdfdevice.h
api_name:
-	EvtDeviceSelfManagedIoCleanup
product:
- Windows
targetos: Windows
req.typenames: 
---

# EVT_WDF_DEVICE_SELF_MANAGED_IO_CLEANUP callback function


## -description


<p class="CCE_Message">[Applies to KMDF and UMDF]

A driver's <i>EvtDeviceSelfManagedIoCleanup</i> event callback function handles deallocation activity for the device's self-managed I/O operations, after a device has been removed.


## -parameters




### -param Device [in]

A handle to a framework device object.


## -returns



None




## -remarks



To register an <i>EvtDeviceSelfManagedIoCleanup</i> callback function, a driver must call <a href="https://msdn.microsoft.com/library/windows/hardware/ff546135">WdfDeviceInitSetPnpPowerEventCallbacks</a>. 

If the driver has registered an <i>EvtDeviceSelfManagedIoCleanup</i> callback function, the framework calls it after the specified device has been removed from the system. For more information about when the framework calls this callback function, see <a href="https://msdn.microsoft.com/9175ce95-196d-44bd-b31c-88386fa0d3d3">PnP and Power Management Scenarios</a>.

The framework calls the driver's <i>EvtDeviceSelfManagedIoCleanup</i> callback function after it has called the driver's <a href="https://msdn.microsoft.com/85a569ea-eb14-4453-9591-fc44afbd3a59">EvtDeviceSelfManagedIoSuspend</a> callback function. The <i>EvtDeviceSelfManagedIoCleanup</i> callback function must release any system resources that the driver allocated and associated with the device's self-managed I/O operations. 

For more information about when the framework calls this callback function, see <a href="https://msdn.microsoft.com/9175ce95-196d-44bd-b31c-88386fa0d3d3">PnP and Power Management Scenarios</a>.

For more information about drivers that provide this callback function, see <a href="https://msdn.microsoft.com/539b3618-44bb-41fd-a9f2-ed6a377c94e2">Using Self-Managed I/O</a>.


#### Examples

To define an <i>EvtDeviceSelfManagedIoCleanup</i> callback function, you must first provide a function declaration that identifies the type of callback function you’re defining. Windows provides a set of callback function types for drivers. Declaring a function using the callback function types helps <a href="https://msdn.microsoft.com/2F3549EF-B50F-455A-BDC7-1F67782B8DCA">Code Analysis for Drivers</a>, <a href="https://msdn.microsoft.com/74feeb16-387c-4796-987a-aff3fb79b556">Static Driver Verifier</a> (SDV), and other verification tools find errors, and it’s a requirement for writing drivers for the Windows operating system.

For example, to define an <i>EvtDeviceSelfManagedIoCleanup</i> callback function that is named <i>MyDeviceSelfManagedIoCleanup</i>, use the <b>EVT_WDF_DEVICE_SELF_MANAGED_IO_CLEANUP</b> type as shown in this code example:

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>EVT_WDF_DEVICE_SELF_MANAGED_IO_CLEANUP  MyDeviceSelfManagedIoCleanup;</pre>
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
VOID
 MyDeviceSelfManagedIoCleanup (
    WDFDEVICE  Device
    )
  {...}</pre>
</td>
</tr>
</table></span></div>
The <b>EVT_WDF_DEVICE_SELF_MANAGED_IO_CLEANUP</b> function type is defined in the Wdfdevice.h header file. To more accurately identify errors when you run the code analysis tools, be sure to add the _Use_decl_annotations_ annotation to your function definition. The _Use_decl_annotations_ annotation ensures that the annotations that are applied to the <b>EVT_WDF_DEVICE_SELF_MANAGED_IO_CLEANUP</b> function type in the header file are used. For more information about the requirements for function declarations, see <a href="https://msdn.microsoft.com/73a408ba-0219-4fde-8dad-ca330e4e67c3">Declaring Functions by Using Function Role Types for KMDF Drivers</a>. For information about _Use_decl_annotations_, see <a href="https://msdn.microsoft.com/en-US/library/c0aa268d-6fa3-4ced-a8c6-f7652b152e61">Annotating Function Behavior</a>.




## -see-also




<a href="https://msdn.microsoft.com/ad4ace83-c6c1-4b5f-b998-f46f3e721165">EvtDeviceSelfManagedIoFlush</a>



<a href="https://msdn.microsoft.com/9dbc66db-ea94-4e6a-9618-00999a9dd641">EvtDeviceSelfManagedIoInit</a>



<a href="https://msdn.microsoft.com/13d7fbc6-6f93-4ef9-abd4-f2adc4e8e23a">EvtDeviceSelfManagedIoRestart</a>



<a href="https://msdn.microsoft.com/85a569ea-eb14-4453-9591-fc44afbd3a59">EvtDeviceSelfManagedIoSuspend</a>
 

 

