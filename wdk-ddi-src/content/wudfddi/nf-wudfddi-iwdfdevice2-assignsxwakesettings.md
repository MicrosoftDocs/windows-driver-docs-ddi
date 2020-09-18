---
UID: NF:wudfddi.IWDFDevice2.AssignSxWakeSettings
title: IWDFDevice2::AssignSxWakeSettings (wudfddi.h)
description: The AssignSxWakeSettings method provides driver-supplied information about a device's ability to trigger a wake signal while both the device and the system are in a low-power state.
old-location: wdf\iwdfdevice2_assignsxwakesettings.htm
tech.root: wdf
ms.assetid: 32d3b680-298b-443e-a2c4-db8fc057bf75
ms.date: 02/26/2018
keywords: ["IWDFDevice2::AssignSxWakeSettings"]
ms.keywords: AssignSxWakeSettings, AssignSxWakeSettings method, AssignSxWakeSettings method,IWDFDevice2 interface, IWDFDevice2 interface,AssignSxWakeSettings method, IWDFDevice2.AssignSxWakeSettings, IWDFDevice2::AssignSxWakeSettings, UMDFDeviceObjectRef_7e411333-6c21-4ed6-af60-b78f3a32bd65.xml, umdf.iwdfdevice2_assignsxwakesettings, wdf.iwdfdevice2_assignsxwakesettings, wudfddi/IWDFDevice2::AssignSxWakeSettings
req.header: wudfddi.h
req.include-header: Wudfddi.h
req.target-type: Desktop
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 1.9
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: Unavailable in UMDF 2.0 and later.
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: WUDFx.dll
req.irql: 
targetos: Windows
req.typenames: 
f1_keywords:
 - IWDFDevice2::AssignSxWakeSettings
 - wudfddi/IWDFDevice2::AssignSxWakeSettings
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - COM
api_location:
 - WUDFx.dll
api_name:
 - IWDFDevice2.AssignSxWakeSettings
---

# IWDFDevice2::AssignSxWakeSettings


## -description

<p class="CCE_Message">[<b>Warning:</b> UMDF 2 is the latest version of UMDF and supersedes UMDF 1.  All new UMDF drivers should be written using UMDF 2.  No new features are being added to UMDF 1 and there is limited support for UMDF 1 on newer versions of Windows 10.  Universal Windows drivers must use UMDF 2.  For more info, see <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/getting-started-with-umdf-version-2">Getting Started with UMDF</a>.]

The <b>AssignSxWakeSettings</b> method provides driver-supplied information about a device's ability to trigger a wake signal while both the device and the system are in a low-power state.

## -parameters

### -param DxState 

[in]
A <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wudfddi/ne-wudfddi-_device_power_state">DEVICE_POWER_STATE</a>-typed enumerator that identifies the low <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/device-power-states">device power state</a> that the device will enter when the system power state drops to a wakeable low-power state. The value of <i>DxState</i> cannot be <b>PowerDeviceD0</b>. DEVICE_POWER_STATE values are defined in wdm.h.

### -param UserControlOfWakeSettings 

[in]
A <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfdevice/ne-wdfdevice-_wdf_power_policy_sx_wake_user_control">WDF_POWER_POLICY_SX_WAKE_USER_CONTROL</a>-typed enumerator that indicates whether users have the ability to modify the device's wake settings.

### -param Enabled 

[in]
A <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdftypes/ne-wdftypes-_wdf_tri_state">WDF_TRI_STATE</a>-typed enumerator that indicates whether the device can wake the system (that is, restore the system to S0) when the system is in a low-power state. This member can have one of the following values:

<b>WdfTrue</b> - Waking the system is enabled.

<b>WdfFalse</b> - Waking the system is disabled.

<b>WdfUseDefault</b> - Waking the system is initially enabled by default; but if the <b>UserControlOfWakeSettings</b> member is set to <b>WakeAllowUserControl</b>, the <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/user-control-of-device-idle-and-wake-behavior">user's setting or driver's INF file</a> overrides the initial value.

If waking the system is enabled and the system is about to enter a low-power state, the framework calls the driver's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wudfddi/nf-wudfddi-ipowerpolicycallbackwakefromsx-onarmwakefromsx">IPowerPolicyCallbackWakeFromSx::OnArmWakeFromSx</a> callback function before the device enters a low-power state.

## -returns

<b>AssignSxWakeSettings</b> returns S_OK if the operation succeeds. Otherwise, the method might return one of the following values:

<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>E_INVALIDARG</b></dt>
</dl>
</td>
<td width="60%">
The caller specified an invalid value for an input parameter.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>HRESULT_FROM_NT(STATUS_INVALID_DEVICE_REQUEST)</b></dt>
</dl>
</td>
<td width="60%">
The calling driver is not the device's <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/power-policy-ownership-in-umdf">power policy owner</a>.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>HRESULT_FROM_NT(STATUS_POWER_STATE_INVALID)</b></dt>
</dl>
</td>
<td width="60%">
The <i>DxState</i> parameter specifies an invalid device power state, or the bus driver indicates that the device cannot trigger a wake signal,

</td>
</tr>
</table>
 

This method might return one of the other values that Winerror.h contains.

## -remarks

The first time a driver calls <b>AssignSxWakeSettings</b>, the following actions occur:

<ul>
<li>
The framework stores the parameter values. 

</li>
<li>
If the <i>UserControlOfWakeSettings</i> parameter is set to <b>WakeAllowUserControl</b> and if the <i>Enabled</i> parameter is set to <b>WdfUseDefault</b>, the framework reads the registry to find out if the user has enabled waking the system. 

</li>
</ul>
During subsequent calls to <b>AssignSxWakeSettings</b>, the framework does not store the value of the <i>UserControlOfWakeSettings</i> parameter. In other words, the framework performs the following steps the first time the driver calls <b>AssignSxWakeSettings</b> but not during later calls:

<ul>
<li>
Stores the value of the <i>UserControlOfWakeSettings</i> parameter.

</li>
<li>
Looks for a user setting in the registry, if the value of the <i>Enabled</i> parameter is <b>WdfUseDefault</b>.

</li>
</ul>
The following rules apply to the value that you specify for the <i>DxState</i> parameter:

<ul>
<li>
The value cannot be <b>PowerDeviceD0</b>. 

</li>
<li>
If you specify <b>DevicePowerMaximum</b>, the framework uses the value that the kernel-mode driver for the device's bus supplied in the <b>DeviceWake</b> member of its <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfdevice/ns-wdfdevice-_wdf_device_power_capabilities">WDF_DEVICE_POWER_CAPABILITIES</a> structure.

</li>
<li>
You cannot specify a device power state that is lower than the device power state in the <b>DeviceWake</b> member of the kernel-mode bus driver's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfdevice/ns-wdfdevice-_wdf_device_power_capabilities">WDF_DEVICE_POWER_CAPABILITIES</a> structure. (In other words, if the bus driver's <b>DeviceWake</b> value is <b>PowerDeviceD2</b>, your function driver's <i>DxState</i> value cannot be <b>PowerDeviceD3</b>.) 

</li>
</ul>
For information about registry entries that control a device's wake capabilities, see <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/user-control-of-device-idle-and-wake-behavior-in-umdf">User Control of Device Idle and Wake Behavior in UMDF</a>. 

For more information about supporting a device's wake capabilities, see <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/supporting-system-wake-up-in-umdf-drivers">Supporting System Wake-Up in UMDF-based Drivers</a>.

The following code example obtains the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wudfddi/nn-wudfddi-iwdfdevice2">IWDFDevice2</a> interface and then calls <b>AssignSxWakeSettings</b>.


```
    IWDFDevice2 *pIWDFDevice2 = NULL;
    HRESULT hr;

    //
    // Get a pointer to the IWDFDevice2 interface.
    //
    hr = pIWDFDevice->QueryInterface(__uuidof(IWDFDevice2),
                                     (void**) &pIWDFDevice2);
    if (SUCCEEDED(hr)) 
    {
        hr = pIWDFDevice2->AssignSxWakeSettings(PowerDeviceMaximum,
                                                WakeAllowUserControl,
                                                WdfUseDefault);
    }
...
    SAFE_RELEASE(pIWDFDevice2);
```


## -see-also

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wudfddi/nn-wudfddi-iwdfdevice2">IWDFDevice2</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wudfddi/nf-wudfddi-iwdfdevice2-assigns0idlesettings">IWDFDevice2::AssignS0IdleSettings</a>

