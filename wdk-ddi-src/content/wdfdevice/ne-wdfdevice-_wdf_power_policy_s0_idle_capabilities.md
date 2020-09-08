---
UID: NE:wdfdevice._WDF_POWER_POLICY_S0_IDLE_CAPABILITIES
title: _WDF_POWER_POLICY_S0_IDLE_CAPABILITIES (wdfdevice.h)
description: The WDF_POWER_POLICY_S0_IDLE_CAPABILITIES enumeration identifies the capabilities that a device can support when it enters a low-power state while it is idling.
old-location: wdf\wdf_power_policy_s0_idle_capabilities.htm
tech.root: wdf
ms.assetid: b4a3611d-5eb6-4fb2-a66a-e563569c4790
ms.date: 02/26/2018
keywords: ["WDF_POWER_POLICY_S0_IDLE_CAPABILITIES enumeration"]
ms.keywords: DFDeviceObjectGeneralRef_42de97ef-91c2-44e1-9b69-fe92ca5b0edc.xml, IdleCanWakeFromS0, IdleCannotWakeFromS0, IdleCapsInvalid, IdleUsbSelectiveSuspend, WDF_POWER_POLICY_S0_IDLE_CAPABILITIES, WDF_POWER_POLICY_S0_IDLE_CAPABILITIES enumeration, _WDF_POWER_POLICY_S0_IDLE_CAPABILITIES, kmdf.wdf_power_policy_s0_idle_capabilities, wdf.wdf_power_policy_s0_idle_capabilities, wdfdevice/IdleCanWakeFromS0, wdfdevice/IdleCannotWakeFromS0, wdfdevice/IdleCapsInvalid, wdfdevice/IdleUsbSelectiveSuspend, wdfdevice/WDF_POWER_POLICY_S0_IDLE_CAPABILITIES, wudfddi_types/IdleCanWakeFromS0, wudfddi_types/IdleCannotWakeFromS0, wudfddi_types/IdleCapsInvalid, wudfddi_types/IdleUsbSelectiveSuspend, wudfddi_types/WDF_POWER_POLICY_S0_IDLE_CAPABILITIES
req.header: wdfdevice.h
req.include-header: Wdf.h
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 1.0
req.umdf-ver: 1.11
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: 
targetos: Windows
req.typenames: WDF_POWER_POLICY_S0_IDLE_CAPABILITIES
f1_keywords:
 - _WDF_POWER_POLICY_S0_IDLE_CAPABILITIES
 - wdfdevice/_WDF_POWER_POLICY_S0_IDLE_CAPABILITIES
 - WDF_POWER_POLICY_S0_IDLE_CAPABILITIES
 - wdfdevice/WDF_POWER_POLICY_S0_IDLE_CAPABILITIES
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - wdfdevice.h
 - wudfddi_types.h
api_name:
 - WDF_POWER_POLICY_S0_IDLE_CAPABILITIES
---

# _WDF_POWER_POLICY_S0_IDLE_CAPABILITIES enumeration (wdfdevice.h)


## -description

<p class="CCE_Message">[Applies to KMDF and UMDF]</p>

The <b>WDF_POWER_POLICY_S0_IDLE_CAPABILITIES</b> enumeration identifies the capabilities that a device can support when it enters a low-power state while it is idling.

## -enum-fields

### -field IdleCapsInvalid

For internal use only.

### -field IdleCannotWakeFromS0

The device cannot wake itself from a low-power state while the system is in its working (S0) state.

### -field IdleCanWakeFromS0

The device can wake itself from a low-power state while the system is in its working (S0) state.

### -field IdleUsbSelectiveSuspend

The device is connected to a USB bus and supports <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/index">USB selective suspend</a>. Use this value if your USB-connected device supports both idling and waking itself while the computer is in its working state. If your USB device supports only idling, use <b>IdleCannotWakeFromS0</b>. (Drivers for USB devices must not specify <b>IdleCanWakeFromS0</b>.) See the code examples in the following Examples section.

For Windows XP, the framework supports USB selective suspend only if the device's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/usbspec/ns-usbspec-_usb_configuration_descriptor">USB_CONFIGURATION_DESCRIPTOR</a> structure shows that the device supports <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/index">remote wakeup</a>. For Windows Vista and later versions of Windows, the framework supports USB selective suspend whether or not the device supports remote wakeup.

## -remarks

The <b>WDF_POWER_POLICY_S0_IDLE_CAPABILITIES</b> enumeration is used in the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfdevice/ns-wdfdevice-_wdf_device_power_policy_idle_settings">WDF_DEVICE_POWER_POLICY_IDLE_SETTINGS</a> structure. 


#### Examples

The following code examples show how to enable idle support for a USB device. In each case, the STATUS_POWER_STATE_INVALID return value means the bus driver has reported that the device cannot wake itself.

<b>KMDF Example</b>

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>WDF_DEVICE_POWER_POLICY_IDLE_SETTINGS_INIT(&idleSettings,
                                           IdleUsbSelectSuspend);
status = WdfDeviceAssignS0IdleSettings(device,
                                       &idleSettings);
if (status == STATUS_POWER_STATE_INVALID){
    //
    // The device probably does not support wake. 
    // It might support idle without wake.
    //
    idleSettings.IdleCaps = IdleCannotWakeFromS0;
    status = WdfDeviceAssignS0IdleSettings(device,
                                           &IdleSettings);
    if (!NT_SUCCESS(status) {...}
 }
else {...}</pre>
</td>
</tr>
</table></span></div>
<b>UMDF Example</b>

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>hr = pIWDFDevice2->AssignS0IdleSettings(IdleUsbSelectSuspend,
                                        PowerDeviceD3,
                                        IDLEWAKE_TIMEOUT_MSEC,
                                        IdleAllowUserControl,
                                        WdfTrue);
if (hr == HRESULT_FROM_NT(STATUS_POWER_STATE_INVALID)){
    //
    // The device probably does not support wake. 
    // It might support idle without wake.
    //
    hr = pIWDFDevice2->AssignS0IdleSettings(IdleCannotWakeFromS0,
                                         PowerDeviceD3,
                                         IDLEWAKE_TIMEOUT_MSEC,
                                         IdleAllowUserControl,
                                         WdfTrue);
    if (!SUCCEEDED(hr)) {...}
}
else {...}</pre>
</td>
</tr>
</table></span></div>

## -see-also

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfdevice/ns-wdfdevice-_wdf_device_power_policy_idle_settings">WDF_DEVICE_POWER_POLICY_IDLE_SETTINGS</a>

