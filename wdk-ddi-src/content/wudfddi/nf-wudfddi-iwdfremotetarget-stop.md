---
UID: NF:wudfddi.IWDFRemoteTarget.Stop
title: IWDFRemoteTarget::Stop (wudfddi.h)
description: The Stop method temporarily stops a remote I/O target.
old-location: wdf\iwdfremotetarget_stop.htm
tech.root: wdf
ms.assetid: 4aaef251-7387-4e42-a7ae-e08120fc95ff
ms.date: 02/26/2018
keywords: ["IWDFRemoteTarget::Stop"]
ms.keywords: IWDFRemoteTarget interface,Stop method, IWDFRemoteTarget.Stop, IWDFRemoteTarget::Stop, Stop, Stop method, Stop method,IWDFRemoteTarget interface, UMDFIoTargetObjectRef_a7d1be6f-890c-4e06-9544-7bd18876b56e.xml, umdf.iwdfremotetarget_stop, wdf.iwdfremotetarget_stop, wudfddi/IWDFRemoteTarget::Stop
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
 - IWDFRemoteTarget::Stop
 - wudfddi/IWDFRemoteTarget::Stop
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - COM
api_location:
 - WUDFx.dll
api_name:
 - IWDFRemoteTarget.Stop
---

# IWDFRemoteTarget::Stop


## -description

<p class="CCE_Message">[<b>Warning:</b> UMDF 2 is the latest version of UMDF and supersedes UMDF 1.  All new UMDF drivers should be written using UMDF 2.  No new features are being added to UMDF 1 and there is limited support for UMDF 1 on newer versions of Windows 10.  Universal Windows drivers must use UMDF 2.  For more info, see <a href="/windows-hardware/drivers/wdf/getting-started-with-umdf-version-2">Getting Started with UMDF</a>.]

The <b>Stop</b> method temporarily stops a <a href="/windows-hardware/drivers/wdf/general-i-o-targets-in-umdf">remote I/O target</a>.

## -parameters

### -param Action 

[in]
A <a href="/windows-hardware/drivers/ddi/wdfiotarget/ne-wdfiotarget-_wdf_io_target_sent_io_action">WDF_IO_TARGET_SENT_IO_ACTION</a>-typed value that specifies how the framework should handle I/O requests that the driver has sent to the remote I/O target, if the target has not completed the requests.

## -returns

<b>Stop</b> always returns S_OK.

## -remarks

If your driver can detect recoverable errors on a remote I/O target, you might want your driver to call <b>Stop</b> to temporarily stop sending requests, and later call <a href="/windows-hardware/drivers/ddi/wudfddi/nf-wudfddi-iwdfremotetarget-start">IWDFRemoteTarget::Start</a> to resume sending requests.

For more information about <b>Stop</b>, and how to use remote I/O targets in UMDF-based drivers, see <a href="/windows-hardware/drivers/wdf/controlling-a-general-i-o-target-s-state-in-umdf">Controlling a General I/O Target's State in UMDF</a>.


#### Examples

The following code example stops a remote I/O target.


```
RemoteTarget->Stop();
```


## -see-also

<a href="/windows-hardware/drivers/ddi/wudfddi/nn-wudfddi-iwdfremotetarget">IWDFRemoteTarget</a>



<a href="/windows-hardware/drivers/ddi/wudfddi/nf-wudfddi-iwdfremotetarget-start">IWDFRemoteTarget::Start</a>