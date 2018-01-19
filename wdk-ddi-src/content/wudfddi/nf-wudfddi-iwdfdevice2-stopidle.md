---
UID: NF:wudfddi.IWDFDevice2.StopIdle
title: IWDFDevice2::StopIdle method
author: windows-driver-content
description: The StopIdle method informs the framework that the device must be placed in its working (D0) power state.
old-location: wdf\iwdfdevice2_stopidle.htm
old-project: wdf
ms.assetid: 1a4907c9-8e3b-4fb6-a7d4-89985e470e48
ms.author: windowsdriverdev
ms.date: 1/11/2018
ms.keywords: IWDFDevice2, IWDFDevice2::StopIdle, StopIdle
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: method
req.header: wudfddi.h
req.include-header: Wudfddi.h
req.target-type: Desktop
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 1.9
req.alt-api: IWDFDevice2.StopIdle
req.alt-loc: WUDFx.dll
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
req.typenames: *PPOWER_ACTION, POWER_ACTION
req.product: Windows 10 or later.
---

# IWDFDevice2::StopIdle method



## -description
<p class="CCE_Message">[<b>Warning:</b> UMDF 2 is the latest version of UMDF and supersedes UMDF 1.  All new UMDF drivers should be written using UMDF 2.  No new features are being added to UMDF 1 and there is limited support for UMDF 1 on newer versions of Windows 10.  Universal Windows drivers must use UMDF 2.  For more info, see <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/getting-started-with-umdf-version-2">Getting Started with UMDF</a>.]

The <b>StopIdle</b> method informs the framework that the device must be placed in its working (D0) power state.



## -syntax

````
HRESULT StopIdle(
  [in] BOOL WaitForD0
);
````


## -parameters

### -param WaitForD0 [in]

A Boolean value that indicates when <b>StopIdle</b> will return. If <b>TRUE</b>, it returns only after the specified device enters the D0 device power state. If <b>FALSE</b>, the method returns immediately.


## -returns
<b>StopIdle</b> returns S_OK if the operation succeeds. Otherwise, the method might return one of the following values:
<dl>
<dt><b>HRESULT_FROM_NT(STATUS_INVALID_DEVICE_REQUEST)</b></dt>
</dl>The calling driver is not the device's <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/power-policy-ownership-in-umdf">power policy owner</a>.
<dl>
<dt><b>HRESULT_FROM_NT(STATUS_PENDING)</b></dt>
</dl>The device was already returning to its working state.
<dl>
<dt><b>HRESULT_FROM_NT(STATUS_POWER_STATE_INVALID)</b></dt>
</dl>A device failure occurred and the device cannot enter its D0 power state.

 

This method might return one of the other values that Winerror.h contains.


## -remarks
If your device can enter a low-power state when it becomes idle, your driver might have to occasionally call <b>StopIdle</b> to bring the device back to its working (D0) state or to prevent it from entering a low-power state. 

Your driver does not have to call <b>StopIdle</b> when a device is idle and the framework places an I/O request in the device's power-managed I/O queue. Additionally, your driver does not have to call <b>StopIdle</b> when a device is idle and it detects a wake signal. In both of these cases, the framework requests the bus driver to restore the device's power state to D0.

Although drivers typically do not need to call <b>StopIdle</b> when handling I/O requests that they obtain from a power-managed I/O queue, the call is allowed. However, drivers must not set the <i>WaitForD0</i> parameter to <b>TRUE</b> when handling I/O requests from a power-managed I/O queue.

Your driver does have to call <b>StopIdle</b> if it must access the device because of a request that the driver has received outside of a power-managed I/O queue. For example, your driver might support a driver-defined interface or a WMI request that requires accessing the device. In this case, you must ensure that the device is in its working state before the driver accesses the device, and that the device remains in its working state until the driver has finished accessing the device.

Calling <b>StopIdle</b> forces the device into its working (D0) state, if the system is in its working (S0) state. The device remains in its working state until the driver calls <a href="https://msdn.microsoft.com/library/windows/hardware/ff556943">IWDFDevice2::ResumeIdle</a>, at which point the framework can place the device in a low-power state if it remains idle.

Do not call <b>StopIdle</b> before the framework has called the driver's <a href="https://msdn.microsoft.com/library/windows/hardware/ff556799">IPnpCallback::OnD0Entry</a> callback method for the first time.

A call to <b>StopIdle</b> can restore an idle device to its working state only if the system is in its working (S0) state. If the system is entering a low-power state when a driver calls <b>StopIdle</b> with the <i>WaitForD0</i> parameter set to <b>TRUE</b>, the function does not return until the system returns to its S0 state. 

Every call to <b>StopIdle</b> must eventually be followed by a call to <a href="https://msdn.microsoft.com/e821f738-3712-49c2-9026-ff6ddc0381a6">ResumeIdle</a>, or else the device will never return to a low-power state if it again becomes idle. Calls to <b>StopIdle</b> can be nested, so the number of calls to <b>ResumeIdle</b> must be equal to the number of calls to <b>StopIdle</b>.

For more information about <b>StopIdle</b> and <a href="https://msdn.microsoft.com/e821f738-3712-49c2-9026-ff6ddc0381a6">ResumeIdle</a>, see <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/supporting-idle-power-down-in-umdf-drivers">Supporting Idle Power-Down in UMDF-based Drivers</a>.

The following code example obtains the <a href="..\wudfddi\nn-wudfddi-iwdfdevice2.md">IWDFDevice2</a> interface and then calls <b>StopIdle</b>. <b>StopIdle</b> will return after the device enters the D0 device power state.


## -see-also
<dl>
<dt>
<a href="..\wudfddi\nn-wudfddi-iwdfdevice2.md">IWDFDevice2</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff556943">IWDFDevice2::ResumeIdle</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [wdf\wdf]:%20IWDFDevice2::StopIdle method%20 RELEASE:%20(1/11/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

