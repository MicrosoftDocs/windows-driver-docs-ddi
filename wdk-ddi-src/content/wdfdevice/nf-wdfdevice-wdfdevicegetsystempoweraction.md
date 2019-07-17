---
UID: NF:wdfdevice.WdfDeviceGetSystemPowerAction
title: WdfDeviceGetSystemPowerAction function (wdfdevice.h)
description: The WdfDeviceGetSystemPowerAction method returns the system power action, if any, that is currently occurring for the computer.
old-location: wdf\wdfdevicegetsystempoweraction.htm
tech.root: wdf
ms.assetid: 5c4e44cd-94a3-4265-b195-7a5711d8035d
ms.date: 02/26/2018
ms.keywords: DFDeviceObjectGeneralRef_605cddb8-470b-4d71-8a6e-295e060ea3e3.xml, WdfDeviceGetSystemPowerAction, WdfDeviceGetSystemPowerAction method, kmdf.wdfdevicegetsystempoweraction, wdf.wdfdevicegetsystempoweraction, wdfdevice/WdfDeviceGetSystemPowerAction
ms.topic: function
f1_keywords:
 - "wdfdevice/WdfDeviceGetSystemPowerAction"
req.header: wdfdevice.h
req.include-header: Wdf.h
req.target-type: Universal
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 1.9
req.umdf-ver: 2.0
req.ddi-compliance: DriverCreate, KmdfIrql, KmdfIrql2
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Wdf01000.sys (KMDF); WUDFx02000.dll (UMDF)
req.dll: 
req.irql: "<= DISPATCH_LEVEL"
topic_type:
- APIRef
- kbSyntax
api_type:
- LibDef
api_location:
- Wdf01000.sys
- Wdf01000.sys.dll
- WUDFx02000.dll
- WUDFx02000.dll.dll
api_name:
- WdfDeviceGetSystemPowerAction
product:
- Windows
targetos: Windows
req.typenames: 
---

# WdfDeviceGetSystemPowerAction function


## -description


<p class="CCE_Message">[Applies to KMDF and UMDF]</p>

The <b>WdfDeviceGetSystemPowerAction</b> method returns the <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/system-power-actions">system power action</a>, if any, that is currently occurring for the computer. 


## -parameters




### -param Device [in]

A handle to a framework device object.


## -returns



<b>WdfDeviceGetSystemPowerAction</b> returns a POWER_ACTION-typed enumerator value. The value indicates the <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/system-power-actions">system power action</a> that is currently occurring for the computer. For more information, see the following Remarks section. The POWER_ACTION enumeration is defined in <i>wdm.h</i>.

A bug check occurs if the driver supplies an invalid object handle.




## -remarks



The <b>WdfDeviceGetSystemPowerAction</b> method enables a driver to determine whether a device's power transition is occurring because the device is idle (or waking up), or because the entire computer is entering (or leaving) a low-power state. 

The driver must call <b>WdfDeviceGetSystemPowerAction</b> only from the event callback functions that the framework calls when the device is <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/a-device-enters-a-low-power-state">entering a low-power state</a> or <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/a-device-returns-to-its-working-state">returning to its working state</a>. 

The value that <b>WdfDeviceGetSystemPowerAction</b> returns depends on the following situations:

<ul>
<li>
If the computer is entering a low-power state when the driver calls <b>WdfDeviceGetSystemPowerAction</b>, the method returns the reason that the computer is entering the low-power state. For example, the method returns <b>PowerActionSleep</b> if the computer is entering its S1, S2, or S3 low-power state.

</li>
<li>
If the computer is returning to its working (S0) state from a low-power state when the driver calls <b>WdfDeviceGetSystemPowerAction</b>, the method returns the reason that the computer entered the low-power state. For example, the method returns <b>PowerActionSleep</b> if the computer is leaving its S1, S2, or S3 low-power state.

</li>
<li>
If the computer is powering up (after having been turned off) when the driver calls <b>WdfDeviceGetSystemPowerAction</b>, the method returns <b>PowerActionNone</b>.

</li>
<li>
If the device is entering a low-power idle state or returning to its working (D0) state when the driver calls <b>WdfDeviceGetSystemPowerAction</b>, while the rest of the system remains at its working (S0) state, the method returns <b>PowerActionNone</b>.

</li>
<li>
If the computer and the device are both in their working states when the driver calls <b>WdfDeviceGetSystemPowerAction</b>, the method returns <b>PowerActionNone</b>.

</li>
</ul>
For more information about low-power states, see <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/a-device-enters-a-low-power-state">A Device Enters a Low-Power State</a>.


#### Examples

The following code example obtains the power transition activity that is currently occurring for the computer.

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>POWER_ACTION SysPowerAction;

SysPowerAction = WdfDeviceGetSystemPowerAction(device);</pre>
</td>
</tr>
</table></span></div>


