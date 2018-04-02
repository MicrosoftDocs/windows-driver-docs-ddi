---
UID: NC:wdfdevice.EVT_WDF_DEVICE_SELF_MANAGED_IO_INIT
title: EVT_WDF_DEVICE_SELF_MANAGED_IO_INIT
author: windows-driver-content
description: A driver's EvtDeviceSelfManagedIoInit event callback function initializes and starts the device's self-managed I/O operations.
old-location: wdf\evtdeviceselfmanagedioinit.htm
old-project: wdf
ms.assetid: 9dbc66db-ea94-4e6a-9618-00999a9dd641
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: DFDeviceObjectGeneralRef_7c67b851-b6d0-450d-bdc9-2a32aa384a36.xml, EVT_WDF_DEVICE_SELF_MANAGED_IO_INIT, EvtDeviceSelfManagedIoInit, EvtDeviceSelfManagedIoInit callback function, kmdf.evtdeviceselfmanagedioinit, wdf.evtdeviceselfmanagedioinit, wdfdevice/EvtDeviceSelfManagedIoInit
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
-	EvtDeviceSelfManagedIoInit
product:
- Windows
targetos: Windows
req.typenames: WDF_DEVICE_SHUTDOWN_FLAGS
req.product: Windows 10 or later.
---

# EVT_WDF_DEVICE_SELF_MANAGED_IO_INIT callback


## -description


<p class="CCE_Message">[Applies to KMDF and UMDF]

A driver's <i>EvtDeviceSelfManagedIoInit</i> event callback function initializes and starts the device's self-managed I/O operations.


## -parameters




### -param Device [in]

A handle to a framework device object.


## -returns



If the <i>EvtDeviceSelfManagedIoInit</i> callback function encounters no errors, it must return STATUS_SUCCESS, or another status value for which <a href="https://msdn.microsoft.com/fe823930-e3ff-4c95-a640-bb6470c95d1d">NT_SUCCESS</a>(<i>status</i>) equals <b>TRUE</b>. Otherwise, it must return a status value for which NT_SUCCESS(<i>status</i>) equals <b>FALSE</b>. If NT_SUCCESS(<i>status</i>) equals <b>FALSE</b>, the framework does not start the device.

If NT_SUCCESS(status) equals <b>FALSE</b>, the framework calls the driver's <a href="https://msdn.microsoft.com/ad4ace83-c6c1-4b5f-b998-f46f3e721165">EvtDeviceSelfManagedIoFlush</a> and <a href="https://msdn.microsoft.com/639ff3fd-ce38-417e-8fc4-a03ad259a5c8">EvtDeviceSelfManagedIoCleanup</a> callback functions.

For more information about this callback function's return values, see <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/reporting-device-failures">Reporting Device Failures</a>.




## -remarks



To register an <i>EvtDeviceSelfManagedIoInit</i> callback function, a driver must call <a href="https://msdn.microsoft.com/library/windows/hardware/ff546135">WdfDeviceInitSetPnpPowerEventCallbacks</a>. 

If the driver has registered an <i>EvtDeviceSelfManagedIoInit</i> callback function, the framework calls it once for each device, after the framework has called the driver's <a href="https://msdn.microsoft.com/0cfabb0f-2d5e-4445-8683-d2916de5b549">EvtDeviceD0Entry</a> callback function for the first time. The framework does not call the <i>EvtDeviceSelfManagedIoInit</i> callback function again for that device, unless the device is removed and reconnected, or the drivers are reloaded.

The <i>EvtDeviceSelfManagedIoInit</i> callback function must initialize and start the self-managed I/O operations that the driver will handle for the device.

For more information about when the framework calls this callback function, see <a href="https://msdn.microsoft.com/9175ce95-196d-44bd-b31c-88386fa0d3d3">PnP and Power Management Scenarios</a>.

For more information about drivers that provide this callback function, see <a href="https://msdn.microsoft.com/539b3618-44bb-41fd-a9f2-ed6a377c94e2">Using Self-Managed I/O</a>.


#### Examples

To define an <i>EvtDeviceSelfManagedIoInit</i> callback function, you must first provide a function declaration that identifies the type of callback function you’re defining. Windows provides a set of callback function types for drivers. Declaring a function using the callback function types helps <a href="https://msdn.microsoft.com/2F3549EF-B50F-455A-BDC7-1F67782B8DCA">Code Analysis for Drivers</a>, <a href="https://msdn.microsoft.com/74feeb16-387c-4796-987a-aff3fb79b556">Static Driver Verifier</a> (SDV), and other verification tools find errors, and it’s a requirement for writing drivers for the Windows operating system.

For example, to define an <i>EvtDeviceSelfManagedIoInit</i> callback function that is named <i>MyDeviceSelfManagedIoInit</i>, use the <b>EVT_WDF_DEVICE_SELF_MANAGED_IO_INIT</b> type as shown in this code example:

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>EVT_WDF_DEVICE_SELF_MANAGED_IO_INIT  MyDeviceSelfManagedIoInit;</pre>
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
 MyDeviceSelfManagedIoInit (
    WDFDEVICE  Device
    )
  {...}</pre>
</td>
</tr>
</table></span></div>
The <b>EVT_WDF_DEVICE_SELF_MANAGED_IO_INIT</b> function type is defined in the Wdfdevice.h header file. To more accurately identify errors when you run the code analysis tools, be sure to add the _Use_decl_annotations_ annotation to your function definition. The _Use_decl_annotations_ annotation ensures that the annotations that are applied to the <b>EVT_WDF_DEVICE_SELF_MANAGED_IO_INIT</b> function type in the header file are used. For more information about the requirements for function declarations, see <a href="https://msdn.microsoft.com/73a408ba-0219-4fde-8dad-ca330e4e67c3">Declaring Functions by Using Function Role Types for KMDF Drivers</a>. For information about _Use_decl_annotations_, see <a href="https://msdn.microsoft.com/en-US/library/c0aa268d-6fa3-4ced-a8c6-f7652b152e61">Annotating Function Behavior</a>.




## -see-also




<a href="https://msdn.microsoft.com/639ff3fd-ce38-417e-8fc4-a03ad259a5c8">EvtDeviceSelfManagedIoCleanup</a>



<a href="https://msdn.microsoft.com/ad4ace83-c6c1-4b5f-b998-f46f3e721165">EvtDeviceSelfManagedIoFlush</a>



<a href="https://msdn.microsoft.com/13d7fbc6-6f93-4ef9-abd4-f2adc4e8e23a">EvtDeviceSelfManagedIoRestart</a>



<a href="https://msdn.microsoft.com/85a569ea-eb14-4453-9591-fc44afbd3a59">EvtDeviceSelfManagedIoSuspend</a>
 

 

