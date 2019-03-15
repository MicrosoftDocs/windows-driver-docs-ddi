---
UID: NC:wdfdevice.EVT_WDF_DEVICE_ARM_WAKE_FROM_SX
title: EVT_WDF_DEVICE_ARM_WAKE_FROM_SX (wdfdevice.h)
description: A driver's EvtDeviceArmWakeFromSx event callback function arms (that is, enables) a device so that it can trigger a wake signal while in a low-power device state.
old-location: wdf\evtdevicearmwakefromsx.htm
tech.root: wdf
ms.assetid: 4954a278-8470-402c-a8ba-5e46ca56ddf7
ms.date: 02/26/2018
ms.keywords: DFDeviceObjectGeneralRef_7d373786-c5fd-41fe-a5b8-341fdb703984.xml, EVT_WDF_DEVICE_ARM_WAKE_FROM_SX, EVT_WDF_DEVICE_ARM_WAKE_FROM_SX callback, EvtDeviceArmWakeFromSx, EvtDeviceArmWakeFromSx callback function, kmdf.evtdevicearmwakefromsx, wdf.evtdevicearmwakefromsx, wdfdevice/EvtDeviceArmWakeFromSx
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
- APIRef
- kbSyntax
api_type:
- UserDefined
api_location:
- Wdfdevice.h
api_name:
- EvtDeviceArmWakeFromSx
product:
- Windows
targetos: Windows
req.typenames: 
---

# EVT_WDF_DEVICE_ARM_WAKE_FROM_SX callback function


## -description


<p class="CCE_Message">[Applies to KMDF and UMDF]</p>

A driver's <i>EvtDeviceArmWakeFromSx</i> event callback function arms (that is, enables) a device so that it can trigger a wake signal while in a low-power device state. The wake signal causes the device to enter its working state (D0) and causes the system to enter its working state (S0). 


## -parameters




### -param Device [in]

A handle to a framework device object.


## -returns



If the <i>EvtDeviceArmWakeFromSx</i> callback function encounters no error, it must return STATUS_SUCCESS or another status value for which <a href="https://msdn.microsoft.com/fe823930-e3ff-4c95-a640-bb6470c95d1d">NT_SUCCESS</a>(<i>status</i>) equals <b>TRUE</b>. Otherwise it must return a status value for which NT_SUCCESS(<i>status</i>) equals <b>FALSE</b>.

If NT_SUCCESS(status) equals <b>FALSE</b>, the framework calls the driver's <a href="https://msdn.microsoft.com/79bf7a42-5053-428a-a78b-dd8bdff93a69">EvtDeviceDisarmWakeFromSx</a> callback function. (The framework does not report a device failure to the PnP manager.)




## -remarks



To register an <i>EvtDeviceArmWakeFromSx</i> callback function, a driver must call <a href="https://msdn.microsoft.com/library/windows/hardware/ff546774">WdfDeviceInitSetPowerPolicyEventCallbacks</a>. Drivers can register either an <i>EvtDeviceArmWakeFromSx</i> callback function or an <a href="https://msdn.microsoft.com/8966ea8f-9760-4a09-b9d3-8fd1ac278b12">EvtDeviceArmWakeFromSxWithReason</a> callback function, but not both.

This callback function handles device-specific operations that are needed to enable the device to detect an external event that triggers a wake signal on the bus. The bus driver's <a href="https://msdn.microsoft.com/902c9bdc-d83a-4bc2-802c-1aaba43c9e2e">EvtDeviceEnableWakeAtBus</a> callback function handles bus-specific operations, such as enabling the PCI bus's Power Management Event (PME) signal.

If a driver has registered an <i>EvtDeviceArmWakeFromSx</i> or <a href="https://msdn.microsoft.com/8966ea8f-9760-4a09-b9d3-8fd1ac278b12">EvtDeviceArmWakeFromSxWithReason</a> callback function, the framework calls it while the device is still in the D0 device power state, before the bus driver lowers the device's power state but after the framework has sent a <a href="https://msdn.microsoft.com/ed582644-af51-4841-be59-6a3deb6d9de5">wait/wake IRP</a> on behalf of the driver. 

The process occurs in the following sequence:

<ol>
<li>
The framework determines that the system is about to enter a low-power system state.

</li>
<li>
The framework calls the driver's <i>EvtDeviceArmWakeFromSx</i> or <a href="https://msdn.microsoft.com/8966ea8f-9760-4a09-b9d3-8fd1ac278b12">EvtDeviceArmWakeFromSxWithReason</a> callback function.

</li>
<li>
The framework asks the driver for the device's bus to lower the device's power.

</li>
</ol>
Immediately before a device enters a low-power state, the framework calls the driver's <a href="https://msdn.microsoft.com/bc3af732-f9ab-43a4-bc6f-7fa0b4c05a66">EvtDeviceD0Exit</a> callback function.

For more information about when the framework calls this callback function, see <a href="https://msdn.microsoft.com/9175ce95-196d-44bd-b31c-88386fa0d3d3">PnP and Power Management Scenarios</a>.

You do not need to provide an <i>EvtDeviceArmWakeFromSx</i> or <a href="https://msdn.microsoft.com/8966ea8f-9760-4a09-b9d3-8fd1ac278b12">EvtDeviceArmWakeFromSxWithReason</a> callback function if your device does not require special hardware operations that enable the device to trigger a wake signal.

For more information about this callback function, see <a href="https://msdn.microsoft.com/519dcd1a-9975-48b1-a032-04348b903ac5">Supporting System Wake-Up</a>.


#### Examples

To define an <i>EvtDeviceArmWakeFromSx</i> callback function, you must first provide a function declaration that identifies the type of callback function you’re defining. Windows provides a set of callback function types for drivers. Declaring a function using the callback function types helps <a href="https://msdn.microsoft.com/2F3549EF-B50F-455A-BDC7-1F67782B8DCA">Code Analysis for Drivers</a>, <a href="https://msdn.microsoft.com/74feeb16-387c-4796-987a-aff3fb79b556">Static Driver Verifier</a> (SDV), and other verification tools find errors, and it’s a requirement for writing drivers for the Windows operating system.

For example, to define an <i>EvtDeviceArmWakeFromSx</i> callback function that is named <i>MyDeviceArmWakeFromSx</i>, use the <b>EVT_WDF_DEVICE_ARM_WAKE_FROM_SX</b> type as shown in this code example:

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>EVT_WDF_DEVICE_ARM_WAKE_FROM_SX MyDeviceArmWakeFromSx;</pre>
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
<pre>
_Use_decl_annotations_
NTSTATUS
 MyDeviceArmWakeFromSx (
    WDFDEVICE  Device
    )
  {...}</pre>
</td>
</tr>
</table></span></div>
The <b>EVT_WDF_DEVICE_ARM_WAKE_FROM_SX</b> function type is defined in the <i>Wdfdevice.h</i> header file. To more accurately identify errors when you run the code analysis tools, be sure to add the _Use_decl_annotations_ annotation to your function definition. The _Use_decl_annotations_ annotation ensures that the annotations that are applied to the <b>EVT_WDF_DEVICE_ARM_WAKE_FROM_SX</b> function type in the header file are used. For more information about the requirements for function declarations, see <a href="https://msdn.microsoft.com/73a408ba-0219-4fde-8dad-ca330e4e67c3">Declaring Functions by Using Function Role Types for KMDF Drivers</a>. For information about _Use_decl_annotations_, see <a href="https://msdn.microsoft.com/library/c0aa268d-6fa3-4ced-a8c6-f7652b152e61">Annotating Function Behavior</a>.




## -see-also




<a href="https://msdn.microsoft.com/a3579239-517f-4df0-a632-31e1176c6552">EvtDeviceArmWakeFromS0</a>



<a href="https://msdn.microsoft.com/8966ea8f-9760-4a09-b9d3-8fd1ac278b12">EvtDeviceArmWakeFromSxWithReason</a>



<a href="https://msdn.microsoft.com/79bf7a42-5053-428a-a78b-dd8bdff93a69">EvtDeviceDisarmWakeFromSx</a>
 

 

