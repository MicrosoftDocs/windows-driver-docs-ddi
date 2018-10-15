---
UID: NF:wdfdevice.WdfDeviceAssignS0IdleSettings
title: WdfDeviceAssignS0IdleSettings function
author: windows-driver-content
description: The WdfDeviceAssignS0IdleSettings method provides driver-supplied information that the framework uses when a device is idle and the system is in its working (S0) state.
old-location: wdf\wdfdeviceassigns0idlesettings.htm
tech.root: wdf
ms.assetid: 78bb5b51-b5b2-4177-8965-e54c04881dd3
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: DFDeviceObjectGeneralRef_e43c95d7-1261-45d0-b47c-460b65bc28c8.xml, WdfDeviceAssignS0IdleSettings, WdfDeviceAssignS0IdleSettings method, kmdf.wdfdeviceassigns0idlesettings, wdf.wdfdeviceassigns0idlesettings, wdfdevice/WdfDeviceAssignS0IdleSettings
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: wdfdevice.h
req.include-header: Wdf.h
req.target-type: Universal
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 1.0
req.umdf-ver: 2.0
req.ddi-compliance: DriverCreate, FDOPowerPolicyOwnerAPI, KmdfIrql, KmdfIrql2, NonFDONotPowerPolicyOwnerAPI
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
-	APIRef
-	kbSyntax
api_type:
-	LibDef
api_location:
-	Wdf01000.sys
-	Wdf01000.sys.dll
-	WUDFx02000.dll
-	WUDFx02000.dll.dll
api_name:
-	WdfDeviceAssignS0IdleSettings
product:
- Windows
targetos: Windows
req.typenames: 
---

# WdfDeviceAssignS0IdleSettings function


## -description


<p class="CCE_Message">[Applies to KMDF and UMDF]</p>

The <b>WdfDeviceAssignS0IdleSettings</b> method provides driver-supplied information that the framework uses when a device is idle and the system is in its working (S0) state.


## -parameters




### -param Device [in]

A handle to a framework device object.


### -param Settings [in]

A pointer to a caller-supplied <a href="https://msdn.microsoft.com/library/windows/hardware/ff551270">WDF_DEVICE_POWER_POLICY_IDLE_SETTINGS</a> structure. 


## -returns



If the operation succeeds, <b>WdfDeviceAssignS0IdleSettings</b> returns STATUS_SUCCESS. Additional return values include:

<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INVALID_DEVICE_REQUEST</b></dt>
</dl>
</td>
<td width="60%">
The calling driver is not the device's power policy owner.


</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INVALID_PARAMETER</b></dt>
</dl>
</td>
<td width="60%">
An invalid <i>Settings</i> value is detected.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INFO_LENGTH_MISMATCH</b></dt>
</dl>
</td>
<td width="60%">
The size of the <a href="https://msdn.microsoft.com/library/windows/hardware/ff551270">WDF_DEVICE_POWER_POLICY_IDLE_SETTINGS</a> structure is incorrect. 

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_POWER_STATE_INVALID</b></dt>
</dl>
</td>
<td width="60%">
This value is returned if one of the following occurs:

<ul>
<li>The <a href="https://msdn.microsoft.com/library/windows/hardware/ff551270">WDF_DEVICE_POWER_POLICY_IDLE_SETTINGS</a> structure contains an invalid device power state.</li>
<li>The <b>IdleCaps</b> member of the <a href="https://msdn.microsoft.com/library/windows/hardware/ff551270">WDF_DEVICE_POWER_POLICY_IDLE_SETTINGS</a> structure indicates the device can wake itself, but the bus driver indicates the device cannot wake itself.</li>
<li>
Starting in KMDF version 1.11 running on Windows 8, the framework checks if the system's firmware can handle a wake signal while the system is in its fully on (S0) power state. If the machine fails this check, <a href="https://msdn.microsoft.com/library/windows/hardware/ff545903">WdfDeviceAssignS0IdleSettings</a> returns <b>STATUS_POWER_STATE_INVALID</b>, and the device remains in its fully on (D0) power state as long as the system remains in S0.

In this case, the driver should not return an error status value from <a href="https://msdn.microsoft.com/b20db029-ee2c-4fb1-bd69-ccd2e37fdc9a">EvtDriverDeviceAdd</a> or any other runtime callback.  At most, the driver might log an error indicating that the device will consume more power than it normally would.

</li>
</ul>
</td>
</tr>
</table>
 

The method might return other <a href="https://msdn.microsoft.com/library/windows/hardware/ff557697">NTSTATUS values</a>.

A bug check occurs if the driver supplies an invalid object handle.




## -remarks



If the driver sets the <b>IdleTimeoutType</b> member of <a href="https://msdn.microsoft.com/library/windows/hardware/ff551270">WDF_DEVICE_POWER_POLICY_IDLE_SETTINGS</a> to <b>SystemManagedIdleTimeout</b> or <b>SystemManagedIdleTimeoutWithHint</b>, it must call <b>WdfDeviceAssignS0IdleSettings</b> before returning from <a href="https://msdn.microsoft.com/0cfabb0f-2d5e-4445-8683-d2916de5b549">EvtDeviceD0Entry</a>. Typically, a driver first calls <b>WdfDeviceAssignS0IdleSettings</b> from <a href="https://msdn.microsoft.com/b20db029-ee2c-4fb1-bd69-ccd2e37fdc9a">EvtDriverDeviceAdd</a>.

 Additional calls to <b>WdfDeviceAssignS0IdleSettings</b> can be made at any time. However, after the driver  sets the value of the <b>IdleTimeoutType</b> member in its first call to <b>WdfDeviceAssignS0IdleSettings</b>, it must not change this value in later calls to this method.

If the driver registers for asynchronous notifications in <a href="https://msdn.microsoft.com/b20db029-ee2c-4fb1-bd69-ccd2e37fdc9a">EvtDriverDeviceAdd</a> (for example by calling <a href="https://msdn.microsoft.com/library/windows/hardware/ff559727">PoRegisterPowerSettingCallback</a> or <a href="https://msdn.microsoft.com/library/windows/hardware/ff549526">IoRegisterPlugPlayNotification</a>), the driver must not subsequently call <b>WdfDeviceAssignS0IdleSettings</b> from within the driver callback routine that it registered.

For more information, see <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/supporting-idle-power-down">Supporting Idle Power-Down</a>.


#### Examples

The following code example initializes a <a href="https://msdn.microsoft.com/library/windows/hardware/ff551270">WDF_DEVICE_POWER_POLICY_IDLE_SETTINGS</a> structure, sets an idle time-out value of 10 seconds, and calls <b>WdfDeviceAssignS0IdleSettings</b>.

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>WDF_DEVICE_POWER_POLICY_IDLE_SETTINGS  idleSettings;
NTSTATUS  status = STATUS_SUCCESS;

WDF_DEVICE_POWER_POLICY_IDLE_SETTINGS_INIT(
                                           &amp;idleSettings,
                                           IdleCanWakeFromS0
                                           );
idleSettings.IdleTimeout = 10000;

status = WdfDeviceAssignS0IdleSettings(
                                       device,
                                       &amp;idleSettings
                                       );
if (!NT_SUCCESS(status)) {
    return status;
}</pre>
</td>
</tr>
</table></span></div>



## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff551270">WDF_DEVICE_POWER_POLICY_IDLE_SETTINGS</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff545909">WdfDeviceAssignSxWakeSettings</a>
 

 

