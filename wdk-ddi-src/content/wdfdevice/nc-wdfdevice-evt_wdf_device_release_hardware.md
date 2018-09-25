---
UID: NC:wdfdevice.EVT_WDF_DEVICE_RELEASE_HARDWARE
title: EVT_WDF_DEVICE_RELEASE_HARDWARE
author: windows-driver-content
description: A driver's EvtDeviceReleaseHardware event callback function performs operations that are needed when a device is no longer accessible.
old-location: wdf\evtdevicereleasehardware.htm
tech.root: wdf
ms.assetid: b4c17e57-688c-4c76-892c-5c8abbf83f20
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: DFDeviceObjectGeneralRef_aaaf477b-f2be-4b26-a607-cb057d976dc1.xml, EVT_WDF_DEVICE_RELEASE_HARDWARE, EVT_WDF_DEVICE_RELEASE_HARDWARE callback, EvtDeviceReleaseHardware, EvtDeviceReleaseHardware callback function, kmdf.evtdevicereleasehardware, wdf.evtdevicereleasehardware, wdfdevice/EvtDeviceReleaseHardware
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
-	EvtDeviceReleaseHardware
product:
- Windows
targetos: Windows
req.typenames: 
---

# EVT_WDF_DEVICE_RELEASE_HARDWARE callback function


## -description


<p class="CCE_Message">[Applies to KMDF and UMDF]</p>

A driver's <i>EvtDeviceReleaseHardware</i> event callback function performs operations that are needed when a device is no longer accessible.


## -parameters




### -param Device [in]

A handle to a framework device object.


### -param ResourcesTranslated [in]

A handle to a resource list object that identifies the translated hardware resources that the Plug and Play manager has assigned to the device.


## -returns



If the <i>EvtDeviceReleaseHardware</i> callback function encounters no errors, it must return STATUS_SUCCESS or another status value for which <a href="https://msdn.microsoft.com/fe823930-e3ff-4c95-a640-bb6470c95d1d">NT_SUCCESS</a>(<i>status</i>) equals <b>TRUE</b>. Otherwise, it must return a status value for which NT_SUCCESS(<i>status</i>) equals <b>FALSE</b>. Do not return STATUS_NOT_SUPPORTED.




## -remarks



To register an <i>EvtDeviceReleaseHardware</i> callback function, your driver must call  <a href="https://msdn.microsoft.com/library/windows/hardware/ff546135">WdfDeviceInitSetPnpPowerEventCallbacks</a>. 

If a driver has registered an <i>EvtDeviceReleaseHardware</i> callback function, the framework calls it during the following transitions: <ul>
<li>Resource rebalancing</li>
<li>Orderly removal</li>
<li>Surprise removal</li>
</ul>


The framework calls the <i>EvtDeviceReleaseHardware</i> callback function after the framework has stopped sending I/O requests to the device, any interrupts assigned to the device have been disabled and disconnected, and the device has been turned off.  

 When the framework calls the <i>EvtDeviceReleaseHardware</i>, the PDO for the device still exists and can be queried for device information that is available in the powered off state, for example PCI configuration state.

In addition, the translated hardware resources that the framework supplies to <i>EvtDeviceReleaseHardware</i> are still assigned to the device.  The primary purpose of this callback function is to release those resources, and in particular to unmap any memory resources that the driver's <a href="https://msdn.microsoft.com/a3d4a983-8a75-44be-bd72-8673d89f9f87">EvtDevicePrepareHardware</a> callback function mapped.  The driver can also use this callback to perform any other driver or device management activity that might be required in the powered down state. Usually, all other hardware shutdown operations should take place in the driver's <a href="https://msdn.microsoft.com/bc3af732-f9ab-43a4-bc6f-7fa0b4c05a66">EvtDeviceD0Exit</a> callback function.

The framework always calls the driver's <i>EvtDeviceReleaseHardware</i> callback function if the driver's <a href="https://msdn.microsoft.com/a3d4a983-8a75-44be-bd72-8673d89f9f87">EvtDevicePrepareHardware</a> callback function has been called, even if <i>EvtDevicePrepareHardware</i> returned a failure code.

A driver for a device that has child devices can control the order in which the framework calls the <i>EvtDeviceReleaseHardware</i> callback functions for the parent device and its children by calling <a href="https://msdn.microsoft.com/library/windows/hardware/hh706196">WdfDeviceInitSetReleaseHardwareOrderOnFailure</a> from within its <a href="https://msdn.microsoft.com/b20db029-ee2c-4fb1-bd69-ccd2e37fdc9a">EvtDriverDeviceAdd</a> callback function.

For more information about when the framework calls this callback function, see <a href="https://msdn.microsoft.com/9175ce95-196d-44bd-b31c-88386fa0d3d3">PnP and Power Management Scenarios</a>.

For more information about hardware resources, see <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/hardware-resources-for-kmdf-drivers">Hardware Resources for Framework-Based Drivers</a>.

For more information about drivers that provide this callback function, see <a href="https://msdn.microsoft.com/487d4a69-a8a8-406c-8572-688388deabe3">Supporting PnP and Power Management in Function Drivers</a>.


#### Examples

To define an <i>EvtDeviceReleaseHardware</i> callback function, you must first provide a function declaration that identifies the type of callback function you’re defining. Windows provides a set of callback function types for drivers. Declaring a function using the callback function types helps <a href="https://msdn.microsoft.com/2F3549EF-B50F-455A-BDC7-1F67782B8DCA">Code Analysis for Drivers</a>, <a href="https://msdn.microsoft.com/74feeb16-387c-4796-987a-aff3fb79b556">Static Driver Verifier</a> (SDV), and other verification tools find errors, and it’s a requirement for writing drivers for the Windows operating system.

For example, to define an <i>EvtDeviceReleaseHardware</i> callback function that is named <i>MyDeviceReleaseHardware</i>, use the <b>EVT_WDF_DEVICE_RELEASE_HARDWARE</b> type as shown in this code example:

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>EVT_WDF_DEVICE_RELEASE_HARDWARE  MyDeviceReleaseHardware;</pre>
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
 MyDeviceReleaseHardware (
    WDFDEVICE  Device,
    WDFCMRESLIST  ResourcesTranslated
    )
  {...}</pre>
</td>
</tr>
</table></span></div>
The <b>EVT_WDF_DEVICE_RELEASE_HARDWARE</b> function type is defined in the Wdfdevice.h header file. To more accurately identify errors when you run the code analysis tools, be sure to add the _Use_decl_annotations_ annotation to your function definition. The _Use_decl_annotations_ annotation ensures that the annotations that are applied to the <b>EVT_WDF_DEVICE_RELEASE_HARDWARE</b> function type in the header file are used. For more information about the requirements for function declarations, see <a href="https://msdn.microsoft.com/73a408ba-0219-4fde-8dad-ca330e4e67c3">Declaring Functions by Using Function Role Types for KMDF Drivers</a>. For information about _Use_decl_annotations_, see <a href="https://msdn.microsoft.com/en-US/library/c0aa268d-6fa3-4ced-a8c6-f7652b152e61">Annotating Function Behavior</a>.




## -see-also




<a href="https://msdn.microsoft.com/a3d4a983-8a75-44be-bd72-8673d89f9f87">EvtDevicePrepareHardware</a>
 

 

