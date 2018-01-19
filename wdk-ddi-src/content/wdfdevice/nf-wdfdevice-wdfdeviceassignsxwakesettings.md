---
UID: NF:wdfdevice.WdfDeviceAssignSxWakeSettings
title: WdfDeviceAssignSxWakeSettings function
author: windows-driver-content
description: The WdfDeviceAssignSxWakeSettings method provides driver-supplied information about a device's ability to trigger a wake signal while both the device and the system are in a low-power state.
old-location: wdf\wdfdeviceassignsxwakesettings.htm
old-project: wdf
ms.assetid: af25d03f-32c5-4e2c-930f-1b905edc566b
ms.author: windowsdriverdev
ms.date: 1/11/2018
ms.keywords: WdfDeviceAssignSxWakeSettings
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
req.alt-api: WdfDeviceAssignSxWakeSettings
req.alt-loc: Wdf01000.sys,Wdf01000.sys.dll,WUDFx02000.dll,WUDFx02000.dll.dll
req.ddi-compliance: DriverCreate, FDOPowerPolicyOwnerAPI, KmdfIrql, KmdfIrql2, NonFDONotPowerPolicyOwnerAPI
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Wdf01000.sys (KMDF); WUDFx02000.dll (UMDF)
req.dll: 
req.irql: <= DISPATCH_LEVEL
req.typenames: WDF_STATE_NOTIFICATION_TYPE
req.product: Windows 10 or later.
---

# WdfDeviceAssignSxWakeSettings function



## -description
<p class="CCE_Message">[Applies to KMDF and UMDF]

The <b>WdfDeviceAssignSxWakeSettings</b> method provides driver-supplied information about a device's ability to trigger a wake signal while both the device and the system are in a low-power state.



## -syntax

````
NTSTATUS WdfDeviceAssignSxWakeSettings(
  _In_ WDFDEVICE                              Device,
  _In_ PWDF_DEVICE_POWER_POLICY_WAKE_SETTINGS Settings
);
````


## -parameters

### -param Device [in]

A handle to a framework device object.


### -param Settings [in]

A pointer to a caller-supplied <a href="..\wdfdevice\ns-wdfdevice-_wdf_device_power_policy_wake_settings.md">WDF_DEVICE_POWER_POLICY_WAKE_SETTINGS</a> structure. 


## -returns
If the operation succeeds, <b>WdfDeviceAssignSxWakeSettings</b> returns STATUS_SUCCESS. Additional return values include:
<dl>
<dt><b>STATUS_INVALID_DEVICE_REQUEST</b></dt>
</dl>The calling driver is not the device's power policy owner.

<dl>
<dt><b>STATUS_INVALID_PARAMETER</b></dt>
</dl>An invalid <i>Settings</i> value is detected.
<dl>
<dt><b>STATUS_INFO_LENGTH_MISMATCH</b></dt>
</dl>The size of the <a href="..\wdfdevice\ns-wdfdevice-_wdf_device_power_policy_wake_settings.md">WDF_DEVICE_POWER_POLICY_WAKE_SETTINGS</a> structure is incorrect. 
<dl>
<dt><b>STATUS_POWER_STATE_INVALID</b></dt>
</dl>The bus driver indicates the device cannot trigger a wake signal, or the <a href="..\wdfdevice\ns-wdfdevice-_wdf_device_power_policy_wake_settings.md">WDF_DEVICE_POWER_POLICY_WAKE_SETTINGS</a> structure contains an invalid device power state.


 

The method might return other <a href="https://msdn.microsoft.com/library/windows/hardware/ff557697">NTSTATUS values</a>.

A bug check occurs if the driver supplies an invalid object handle.


## -remarks
For more information, see <a href="https://msdn.microsoft.com/519dcd1a-9975-48b1-a032-04348b903ac5">Supporting System Wake-Up</a>.

The following code example initializes a WDF_DEVICE_POWER_POLICY_WAKE_SETTINGS structure and then calls <b>WdfDeviceAssignSxWakeSettings</b>. The example uses the default settings that <a href="..\wdfdevice\nf-wdfdevice-wdf_device_power_policy_wake_settings_init.md">WDF_DEVICE_POWER_POLICY_WAKE_SETTINGS_INIT</a> sets.


## -see-also
<dl>
<dt>
<a href="..\wdfdevice\nf-wdfdevice-wdfdeviceassigns0idlesettings.md">WdfDeviceAssignS0IdleSettings</a>
</dt>
<dt>
<a href="..\wdfdevice\ns-wdfdevice-_wdf_device_power_policy_wake_settings.md">WDF_DEVICE_POWER_POLICY_WAKE_SETTINGS</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [wdf\wdf]:%20WdfDeviceAssignSxWakeSettings method%20 RELEASE:%20(1/11/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

