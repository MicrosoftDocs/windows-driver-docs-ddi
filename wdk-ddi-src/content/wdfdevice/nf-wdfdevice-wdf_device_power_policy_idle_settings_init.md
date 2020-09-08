---
UID: NF:wdfdevice.WDF_DEVICE_POWER_POLICY_IDLE_SETTINGS_INIT
title: WDF_DEVICE_POWER_POLICY_IDLE_SETTINGS_INIT function (wdfdevice.h)
description: The WDF_DEVICE_POWER_POLICY_IDLE_SETTINGS_INIT function initializes a driver's WDF_DEVICE_POWER_POLICY_IDLE_SETTINGS structure.
old-location: wdf\wdf_device_power_policy_idle_settings_init.htm
tech.root: wdf
ms.assetid: e5a80021-1d9d-42f4-9344-9dd8d9524d0b
ms.date: 02/26/2018
keywords: ["WDF_DEVICE_POWER_POLICY_IDLE_SETTINGS_INIT function"]
ms.keywords: DFDeviceObjectGeneralRef_1aaae0d7-3b13-43f6-b7e4-7c105b2e41b2.xml, WDF_DEVICE_POWER_POLICY_IDLE_SETTINGS_INIT, WDF_DEVICE_POWER_POLICY_IDLE_SETTINGS_INIT function, kmdf.wdf_device_power_policy_idle_settings_init, wdf.wdf_device_power_policy_idle_settings_init, wdfdevice/WDF_DEVICE_POWER_POLICY_IDLE_SETTINGS_INIT
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
req.irql: 
targetos: Windows
req.typenames: 
f1_keywords:
 - WDF_DEVICE_POWER_POLICY_IDLE_SETTINGS_INIT
 - wdfdevice/WDF_DEVICE_POWER_POLICY_IDLE_SETTINGS_INIT
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - wdfdevice.h
api_name:
 - WDF_DEVICE_POWER_POLICY_IDLE_SETTINGS_INIT
---

# WDF_DEVICE_POWER_POLICY_IDLE_SETTINGS_INIT function


## -description

<p class="CCE_Message">[Applies to KMDF and UMDF]</p>

The <b>WDF_DEVICE_POWER_POLICY_IDLE_SETTINGS_INIT</b> function initializes a driver's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfdevice/ns-wdfdevice-_wdf_device_power_policy_idle_settings">WDF_DEVICE_POWER_POLICY_IDLE_SETTINGS</a> structure.

## -parameters

### -param Settings 

[out]
A pointer to a driver-allocated <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfdevice/ns-wdfdevice-_wdf_device_power_policy_idle_settings">WDF_DEVICE_POWER_POLICY_IDLE_SETTINGS</a> structure.

### -param IdleCaps 

[in]
A <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfdevice/ne-wdfdevice-_wdf_power_policy_s0_idle_capabilities">WDF_POWER_POLICY_S0_IDLE_CAPABILITIES</a>-typed enumerator.

## -remarks

First, the <b>WDF_DEVICE_POWER_POLICY_IDLE_SETTINGS_INIT</b> function zeros the specified <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfdevice/ns-wdfdevice-_wdf_device_power_policy_idle_settings">WDF_DEVICE_POWER_POLICY_IDLE_SETTINGS</a> structure and sets the structure's <b>Size</b> member. 

Then, the function sets the structure's <b>IdleTimeout</b> member to <b>IdleTimeoutDefaultValue</b>, sets the <b>UserControlOfIdleSettings</b> member to <b>IdleAllowUserControl</b>, and sets the <b>Enabled</b> member to <b>WdfUseDefault</b>. 

In addition, the function sets the <b>PowerUpIdleDeviceOnSystemWake</b> member to  <b>WdfUseDefault</b> and the <b>IdleTimeoutType</b> member to <b>DriverManagedIdleTimeout</b>.

 In addition, the function sets the <b>ExcludeD3Cold</b> member to <b>WdfUseDefault</b>.

Next, the function sets the structure's <b>IdleCaps</b> member to the value that the <i>IdleCaps</i> parameter specifies. 

Finally, if the <i>IdleCaps</i> parameter specifies <b>IdleUsbSelectiveSuspend</b> or <b>IdleCanWakeFromS0</b>, the function sets the <b>DxState</b> member to <b>PowerDeviceMaximum</b>. If the <i>IdleCaps</i> parameter specifies <b>IdleCannotWakeFromS0</b>, the function sets the <b>DxState</b> member to <b>PowerDeviceD3</b>.


#### Examples

For a code example that uses <b>WDF_DEVICE_POWER_POLICY_IDLE_SETTINGS_INIT</b>, see <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfdevice/nf-wdfdevice-wdfdeviceassigns0idlesettings">WdfDeviceAssignS0IdleSettings</a>.

<div class="code"></div>

## -see-also

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfdevice/ns-wdfdevice-_wdf_device_power_policy_idle_settings">WDF_DEVICE_POWER_POLICY_IDLE_SETTINGS</a>

