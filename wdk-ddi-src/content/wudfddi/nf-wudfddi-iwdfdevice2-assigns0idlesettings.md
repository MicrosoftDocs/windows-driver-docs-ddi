---
UID: NF:wudfddi.IWDFDevice2.AssignS0IdleSettings
title: IWDFDevice2::AssignS0IdleSettings (wudfddi.h)
description: The AssignS0IdleSettings method provides driver-supplied information that the framework uses when a device is idle and the system is in its working (S0) state.
old-location: wdf\iwdfdevice2_assigns0idlesettings.htm
tech.root: wdf
ms.assetid: ffe91b9a-3b74-4dd9-b23d-096f1992485e
ms.date: 02/26/2018
keywords: ["IWDFDevice2::AssignS0IdleSettings"]
ms.keywords: AssignS0IdleSettings, AssignS0IdleSettings method, AssignS0IdleSettings method,IWDFDevice2 interface, IWDFDevice2 interface,AssignS0IdleSettings method, IWDFDevice2.AssignS0IdleSettings, IWDFDevice2::AssignS0IdleSettings, UMDFDeviceObjectRef_337ed405-40bd-4162-ad50-3ee59e4e6c73.xml, umdf.iwdfdevice2_assigns0idlesettings, wdf.iwdfdevice2_assigns0idlesettings, wudfddi/IWDFDevice2::AssignS0IdleSettings
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
 - IWDFDevice2::AssignS0IdleSettings
 - wudfddi/IWDFDevice2::AssignS0IdleSettings
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - COM
api_location:
 - WUDFx.dll
api_name:
 - IWDFDevice2.AssignS0IdleSettings
---

# IWDFDevice2::AssignS0IdleSettings


## -description

<p class="CCE_Message">[<b>Warning:</b> UMDF 2 is the latest version of UMDF and supersedes UMDF 1.  All new UMDF drivers should be written using UMDF 2.  No new features are being added to UMDF 1 and there is limited support for UMDF 1 on newer versions of Windows 10.  Universal Windows drivers must use UMDF 2.  For more info, see <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/getting-started-with-umdf-version-2">Getting Started with UMDF</a>.]

The <b>AssignS0IdleSettings</b> method provides driver-supplied information that the framework uses when a device is idle and the system is in its working (S0) state.

## -parameters

### -param IdleCaps 

[in]
A <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfdevice/ne-wdfdevice-_wdf_power_policy_s0_idle_capabilities">WDF_POWER_POLICY_S0_IDLE_CAPABILITIES</a>-typed enumerator that identifies the device's ability to wake itself after it is set to a low-power state, while the system remains in its working (S0) state.

### -param DxState 

[in]
A <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wudfddi/ne-wudfddi-_device_power_state">DEVICE_POWER_STATE</a>-typed enumerator that identifies the low <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/device-power-states">device power state</a> that the device will enter after the idle timeout period ends. DEVICE_POWER_STATE values are defined in wdm.h.

### -param IdleTimeout 

[in]
The amount of time, in milliseconds, that the device will remain idle before the framework places it in the <i>DxState</i>-supplied low-power state. To use the framework's default idle timeout value, specify <b>IdleTimeoutDefaultValue</b> For more information, see the Remarks section.

### -param UserControlOfIdleSettings 

[in]
A <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfdevice/ne-wdfdevice-_wdf_power_policy_s0_idle_user_control">WDF_POWER_POLICY_S0_IDLE_USER_CONTROL</a>-typed enumerator that indicates whether users have the ability to modify the device's idle settings.

### -param Enabled 

[in]
A <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdftypes/ne-wdftypes-_wdf_tri_state">WDF_TRI_STATE</a>-typed enumerator that indicates whether the device will be powered down if it remains idle and while the system power is at S0. This member can have one of the following values:

<b>WdfTrue</b> - Powering down is enabled.

<b>WdfFalse</b> - Powering down is disabled.

<b>WdfUseDefault</b> - Powering down is initially enabled by default; but if the <i>UserControlOfIdleSettings</i> parameter is set to <b>IdleAllowUserControl</b>, the <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/user-control-of-device-idle-and-wake-behavior">user's setting or driver's INF file</a> overrides the initial value.

If powering down is enabled, the device has a wake-up capability, and the idle timeout value expires, the framework calls the driver's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wudfddi/nf-wudfddi-ipowerpolicycallbackwakefroms0-onarmwakefroms0">IPowerPolicyCallbackWakeFromS0::OnArmWakeFromS0</a> callback function before the device enters a low-power state.

## -returns

<b>AssignS0IdleSettings</b> returns S_OK if the operation succeeds. Otherwise, the method might return one of the following values:

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
The <i>DxState</i> parameter specifies an invalid device power state, or the <i>IdleCaps</i> parameter indicates the device can wake itself, but the bus driver indicates the device cannot wake itself.

</td>
</tr>
</table>
 

This method might return one of the other values that Winerror.h contains.

## -remarks

The first time a driver calls <b>AssignS0IdleSettings</b>, the following actions occur:

<ul>
<li>
The framework stores the values of all parameters. 

</li>
<li>
If the <i>UserControlOfIdleSettings</i> parameter is set to <b>IdleAllowUserControl</b> and if the <i>Enabled</i> parameter is set to <b>WdfUseDefault</b>, the framework reads the registry to find out if the user has enabled powering down the device when it is idle.

</li>
</ul>
During subsequent calls to <b>AssignS0IdleSettings</b>, the framework only stores the values of the <i>DxState</i>, <i>IdleTimeout</i>, and <i>Enabled</i> parameters. Also, the framework stores the value of the <i>IdleCaps</i> parameter subject to the following rules:


<ul>
<li>
If the driver has ever specified <b>IdleCanWakeFromS0</b> for the <i>IdleCaps</i> parameter's value in a previous call to <b>AssignS0IdleSettings</b>, it cannot subsequently change that value to <b>IdleUsbSelectiveSuspend</b>.

</li>
<li>
If the driver has ever specified <b>IdleUsbSelectiveSuspend</b> for the <i>IdleCaps</i> parameter's value in a previous call to <b>AssignS0IdleSettings</b>, it cannot subsequently change that value to <b>IdleCanWakeFromS0</b>.

</li>
</ul>


The following rules apply to the value that you specify for the <i>DxState</i> parameter:

<ul>
<li>
The value cannot be <b>PowerDeviceD0</b>. 

</li>
<li>
For USB devices, the value cannot be <b>PowerDeviceD0</b> or <b>PowerDeviceD3</b>.

</li>
<li>
If you specify <b>DevicePowerMaximum</b>, the framework uses the value that the kernel-mode driver for the device's bus supplied in the <b>DeviceWake</b> member of its <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfdevice/ns-wdfdevice-_wdf_device_power_capabilities">WDF_DEVICE_POWER_CAPABILITIES</a> structure. 

</li>
<li>
If the value of the <i>IdleCaps</i> parameter is <b>IdleCanWakeFromS0</b> or <b>IdleUsbSelectiveSuspend</b>, you cannot specify a device power state that is lower than the device power state in the <b>DeviceWake</b> member of the kernel-mode bus driver's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfdevice/ns-wdfdevice-_wdf_device_power_capabilities">WDF_DEVICE_POWER_CAPABILITIES</a> structure. (In other words, if the bus driver's <b>DeviceWake</b> value is <b>PowerDeviceD2</b>, your function driver's <i>DxState</i> value cannot be <b>PowerDeviceD3</b>.) 

</li>
</ul>
If you specify <b>IdleTimeoutDefaultValue</b> for the <i>IdleTimeout</i> parameter, the timeout defaults to five seconds. You can examine the output from the <a href="https://docs.microsoft.com/windows-hardware/drivers/debugger/-wudfext-wudfdevice">!wudfext.wudfdevice</a> and <a href="https://docs.microsoft.com/windows-hardware/drivers/debugger/-wudfext-umdevstacks">!wudfext.umdevstacks</a> debugger extensions to see the effective settings and power references.

For information about registry entries that control a device's idle capabilities, see <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/user-control-of-device-idle-and-wake-behavior-in-umdf">User Control of Device Idle and Wake Behavior in UMDF</a>. 

For more information about supporting a device's idle capabilities, see <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/supporting-idle-power-down-in-umdf-drivers">Supporting Idle Power-Down in UMDF-based Drivers</a>.


#### Examples

The following code example is based on the UMDF version of the toaster sample. The example obtains the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wudfddi/nn-wudfddi-iwdfdevice2">IWDFDevice2</a> interface and then calls <b>AssignS0IdleSettings</b>.


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
    //
    // The toaster device is virtual, so we tell the framework that the 
    // device cannot wake if it sleeps while the system is in S0. The device 
    // can return to D0 only when the driver stack receives an I/O request.
    //
    hr = pIWDFDevice2->AssignS0IdleSettings(IdleCannotWakeFromS0,
                                            PowerDeviceD3,
                                            IDLEWAKE_TIMEOUT_MSEC,
                                            IdleAllowUserControl,
                                            WdfTrue);
    }
...
    SAFE_RELEASE(pIWDFDevice2);
```


## -see-also

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wudfddi/nn-wudfddi-iwdfdevice2">IWDFDevice2</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wudfddi/nf-wudfddi-iwdfdevice2-assignsxwakesettings">IWDFDevice2::AssignSxWakeSettings</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wudfddi/nf-wudfddi-iwdfdevice3-assigns0idlesettingsex">IWDFDevice3::AssignS0IdleSettingsEx</a>

