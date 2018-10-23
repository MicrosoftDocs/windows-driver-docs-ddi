---
UID: NC:wdfcontrol.EVT_WDF_DEVICE_SHUTDOWN_NOTIFICATION
title: EVT_WDF_DEVICE_SHUTDOWN_NOTIFICATION
author: windows-driver-content
description: A driver's EvtDeviceShutdownNotification event callback function notifies the driver that the system is about to lose its power.
old-location: wdf\evtdeviceshutdownnotification.htm
tech.root: wdf
ms.assetid: 365e669b-b4a1-432a-ab0c-9292a910256e
ms.date: 02/26/2018
ms.keywords: DFDeviceObjectControllerDevObjRef_d7dab025-aa6d-4f66-a0cb-3784b3bc7b1c.xml, EVT_WDF_DEVICE_SHUTDOWN_NOTIFICATION, EVT_WDF_DEVICE_SHUTDOWN_NOTIFICATION callback, EvtDeviceShutdownNotification, EvtDeviceShutdownNotification callback function, kmdf.evtdeviceshutdownnotification, wdf.evtdeviceshutdownnotification, wdfcontrol/EvtDeviceShutdownNotification
ms.topic: callback
req.header: wdfcontrol.h
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
-	WdfControl.h
api_name:
-	EvtDeviceShutdownNotification
product:
- Windows
targetos: Windows
req.typenames: 
---

# EVT_WDF_DEVICE_SHUTDOWN_NOTIFICATION callback function


## -description


<p class="CCE_Message">[Applies to KMDF only]</p>

A driver's <i>EvtDeviceShutdownNotification</i> event callback function notifies the driver that the system is about to lose its power.


## -parameters




### -param Device [in]

A handle to a framework device object that the driver initialized by calling <a href="https://msdn.microsoft.com/library/windows/hardware/ff545841">WdfControlDeviceInitAllocate</a>.


## -returns



None




## -remarks



To register an <i>EvtDeviceShutdownNotification</i> event callback function, a driver must call <a href="https://msdn.microsoft.com/library/windows/hardware/ff545847">WdfControlDeviceInitSetShutdownNotification</a>. Only drivers that create control device objects can register this callback function.

The framework calls a driver's <i>EvtDeviceShutdownNotification</i> event callback function if the user is about to turn off the computer, or if the computer suddenly loses its power and an emergency power supply, such as an uninterruptible power supply (UPS), is available to safely turn off the computer.

For more information about control device objects and the <i>EvtDeviceShutdownNotification</i> callback function see <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/using-control-device-objects">Using Control Device Objects</a>.


#### Examples

To define an <i>EvtDeviceShutdownNotification</i> callback function, you must first provide a function declaration that identifies the type of callback function you’re defining. Windows provides a set of callback function types for drivers. Declaring a function using the callback function types helps <a href="https://msdn.microsoft.com/2F3549EF-B50F-455A-BDC7-1F67782B8DCA">Code Analysis for Drivers</a>, <a href="https://msdn.microsoft.com/74feeb16-387c-4796-987a-aff3fb79b556">Static Driver Verifier</a> (SDV), and other verification tools find errors, and it’s a requirement for writing drivers for the Windows operating system.

For example, to define an <i>EvtDeviceShutdownNotification</i> callback function that is named <i>MyDeviceShutdownNotification</i>, use the <b>EVT_WDF_DEVICE_SHUTDOWN_NOTIFICATION</b> type as shown in this code example:

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>EVT_WDF_DEVICE_SHUTDOWN_NOTIFICATION  MyDeviceShutdownNotification;</pre>
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
 MyDeviceShutdownNotification (
 WDFDEVICE  Device
    )
  {...}</pre>
</td>
</tr>
</table></span></div>
The <b>EVT_WDF_DEVICE_SHUTDOWN_NOTIFICATION</b> function type is defined in the WdfControl.h header file. To more accurately identify errors when you run the code analysis tools, be sure to add the _Use_decl_annotations_ annotation to your function definition. The _Use_decl_annotations_ annotation ensures that the annotations that are applied to the <b>EVT_WDF_DEVICE_SHUTDOWN_NOTIFICATION</b> function type in the header file are used. For more information about the requirements for function declarations, see <a href="https://msdn.microsoft.com/73a408ba-0219-4fde-8dad-ca330e4e67c3">Declaring Functions by Using Function Role Types for KMDF Drivers</a>. For information about _Use_decl_annotations_, see <a href="https://msdn.microsoft.com/library/c0aa268d-6fa3-4ced-a8c6-f7652b152e61">Annotating Function Behavior</a>.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff545841">WdfControlDeviceInitAllocate</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff545847">WdfControlDeviceInitSetShutdownNotification</a>
 

 

