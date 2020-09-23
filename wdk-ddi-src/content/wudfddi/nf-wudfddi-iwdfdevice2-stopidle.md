---
UID: NF:wudfddi.IWDFDevice2.StopIdle
title: IWDFDevice2::StopIdle (wudfddi.h)
description: The StopIdle method informs the framework that the device must be placed in its working (D0) power state.
old-location: wdf\iwdfdevice2_stopidle.htm
tech.root: wdf
ms.assetid: 1a4907c9-8e3b-4fb6-a7d4-89985e470e48
ms.date: 02/26/2018
keywords: ["IWDFDevice2::StopIdle"]
ms.keywords: IWDFDevice2 interface,StopIdle method, IWDFDevice2.StopIdle, IWDFDevice2::StopIdle, StopIdle, StopIdle method, StopIdle method,IWDFDevice2 interface, UMDFDeviceObjectRef_8b32ad46-c35a-4b3a-8779-fa183d9cbb72.xml, umdf.iwdfdevice2_stopidle, wdf.iwdfdevice2_stopidle, wudfddi/IWDFDevice2::StopIdle
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
 - IWDFDevice2::StopIdle
 - wudfddi/IWDFDevice2::StopIdle
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - COM
api_location:
 - WUDFx.dll
api_name:
 - IWDFDevice2.StopIdle
---

# IWDFDevice2::StopIdle


## -description

<p class="CCE_Message">[<b>Warning:</b> UMDF 2 is the latest version of UMDF and supersedes UMDF 1.  All new UMDF drivers should be written using UMDF 2.  No new features are being added to UMDF 1 and there is limited support for UMDF 1 on newer versions of Windows 10.  Universal Windows drivers must use UMDF 2.  For more info, see <a href="/windows-hardware/drivers/wdf/getting-started-with-umdf-version-2">Getting Started with UMDF</a>.]

The <b>StopIdle</b> method informs the framework that the device must be placed in its working (D0) power state.

## -parameters

### -param WaitForD0 

[in]
A Boolean value that indicates when <b>StopIdle</b> will return. If <b>TRUE</b>, it returns only after the specified device enters the D0 device power state. If <b>FALSE</b>, the method returns immediately.

## -returns

<b>StopIdle</b> returns S_OK if the operation succeeds. Otherwise, the method might return one of the following values:

<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>HRESULT_FROM_NT(STATUS_INVALID_DEVICE_REQUEST)</b></dt>
</dl>
</td>
<td width="60%">
The calling driver is not the device's <a href="/windows-hardware/drivers/wdf/power-policy-ownership-in-umdf">power policy owner</a>.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>HRESULT_FROM_NT(STATUS_PENDING)</b></dt>
</dl>
</td>
<td width="60%">
The device was already returning to its working state.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>HRESULT_FROM_NT(STATUS_POWER_STATE_INVALID)</b></dt>
</dl>
</td>
<td width="60%">
A device failure occurred and the device cannot enter its D0 power state.

</td>
</tr>
</table>
 

This method might return one of the other values that Winerror.h contains.

## -remarks

If your device can enter a low-power state when it becomes idle, your driver might have to occasionally call <b>StopIdle</b> to bring the device back to its working (D0) state or to prevent it from entering a low-power state. 

Your driver does not have to call <b>StopIdle</b> when a device is idle and the framework places an I/O request in the device's power-managed I/O queue. Additionally, your driver does not have to call <b>StopIdle</b> when a device is idle and it detects a wake signal. In both of these cases, the framework requests the bus driver to restore the device's power state to D0.

Although drivers typically do not need to call <b>StopIdle</b> when handling I/O requests that they obtain from a power-managed I/O queue, the call is allowed. However, drivers must not set the <i>WaitForD0</i> parameter to <b>TRUE</b> when handling I/O requests from a power-managed I/O queue.

Your driver does have to call <b>StopIdle</b> if it must access the device because of a request that the driver has received outside of a power-managed I/O queue. For example, your driver might support a driver-defined interface or a WMI request that requires accessing the device. In this case, you must ensure that the device is in its working state before the driver accesses the device, and that the device remains in its working state until the driver has finished accessing the device.

Calling <b>StopIdle</b> forces the device into its working (D0) state, if the system is in its working (S0) state. The device remains in its working state until the driver calls <a href="/windows-hardware/drivers/ddi/wudfddi/nf-wudfddi-iwdfdevice2-resumeidle">IWDFDevice2::ResumeIdle</a>, at which point the framework can place the device in a low-power state if it remains idle.

Do not call <b>StopIdle</b> before the framework has called the driver's <a href="/windows-hardware/drivers/ddi/wudfddi/nf-wudfddi-ipnpcallback-ond0entry">IPnpCallback::OnD0Entry</a> callback method for the first time.

A call to <b>StopIdle</b> can restore an idle device to its working state only if the system is in its working (S0) state. If the system is entering a low-power state when a driver calls <b>StopIdle</b> with the <i>WaitForD0</i> parameter set to <b>TRUE</b>, the function does not return until the system returns to its S0 state. 

Every call to <b>StopIdle</b> must eventually be followed by a call to <a href="/windows-hardware/drivers/ddi/wudfddi/nf-wudfddi-iwdfdevice2-resumeidle">ResumeIdle</a>, or else the device will never return to a low-power state if it again becomes idle. Calls to <b>StopIdle</b> can be nested, so the number of calls to <b>ResumeIdle</b> must be equal to the number of calls to <b>StopIdle</b>.

For more information about <b>StopIdle</b> and <a href="/windows-hardware/drivers/ddi/wudfddi/nf-wudfddi-iwdfdevice2-resumeidle">ResumeIdle</a>, see <a href="/windows-hardware/drivers/wdf/supporting-idle-power-down-in-umdf-drivers">Supporting Idle Power-Down in UMDF-based Drivers</a>.


#### Examples

The following code example obtains the <a href="/windows-hardware/drivers/ddi/wudfddi/nn-wudfddi-iwdfdevice2">IWDFDevice2</a> interface and then calls <b>StopIdle</b>. <b>StopIdle</b> will return after the device enters the D0 device power state.


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
        hr = pIWDFDevice2->StopIdle(TRUE);
    }
...
   SAFE_RELEASE(pIWDFDevice2);
```


## -see-also

<a href="/windows-hardware/drivers/ddi/wudfddi/nn-wudfddi-iwdfdevice2">IWDFDevice2</a>



<a href="/windows-hardware/drivers/ddi/wudfddi/nf-wudfddi-iwdfdevice2-resumeidle">IWDFDevice2::ResumeIdle</a>