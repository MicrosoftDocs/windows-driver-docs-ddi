---
UID: NF:wudfddi.IWDFIoTargetStateManagement.Start
title: IWDFIoTargetStateManagement::Start method
author: windows-driver-content
description: The Start method starts sending queued requests to a local I/O target.
old-location: wdf\iwdfiotargetstatemanagement_start.htm
old-project: wdf
ms.assetid: e242b62a-7a4f-491b-b1a7-3388cf9c5a40
ms.author: windowsdriverdev
ms.date: 1/11/2018
ms.keywords: UMDFIoTargetObjectRef_931a0267-704f-44f7-8f52-0344afb86f81.xml, wdf.iwdfiotargetstatemanagement_start, Start, IWDFIoTargetStateManagement::Start, Start method, IWDFIoTargetStateManagement interface, wudfddi/IWDFIoTargetStateManagement::Start, Start method, umdf.iwdfiotargetstatemanagement_start, IWDFIoTargetStateManagement, IWDFIoTargetStateManagement interface, Start method
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: method
req.header: wudfddi.h
req.include-header: Wudfddi.h
req.target-type: Desktop
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 1.5
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: Unavailable in UMDF 2.0 and later.
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: wudfddi.h
req.dll: WUDFx.dll
req.irql: 
topictype:
-	APIRef
-	kbSyntax
apitype:
-	COM
apilocation:
-	WUDFx.dll
apiname:
-	IWDFIoTargetStateManagement.Start
product: Windows
targetos: Windows
req.typenames: "*PPOWER_ACTION, POWER_ACTION"
req.product: Windows 10 or later.
---

# IWDFIoTargetStateManagement::Start method


## -description


<p class="CCE_Message">[<b>Warning:</b> UMDF 2 is the latest version of UMDF and supersedes UMDF 1.  All new UMDF drivers should be written using UMDF 2.  No new features are being added to UMDF 1 and there is limited support for UMDF 1 on newer versions of Windows 10.  Universal Windows drivers must use UMDF 2.  For more info, see <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/getting-started-with-umdf-version-2">Getting Started with UMDF</a>.]

The <b>Start</b> method starts sending queued requests to a <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/general-i-o-targets-in-umdf">local  I/O target</a>.


## -syntax


````
HRESULT Start();
````


## -parameters





## -returns


<b>Start</b> returns S_OK if the operation succeeds. Otherwise, this method might return one of the error codes:
<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>HRESULT_FROM_NT (STATUS_INVALID_DEVICE_STATE)</b></dt>
</dl>
</td>
<td width="60%">
The device has been removed.

</td>
</tr>
</table> 

This method might return one of the other error codes that Winerror.h defines.



## -remarks


If your driver can detect recoverable device errors, you might want your driver to call <a href="https://msdn.microsoft.com/library/windows/hardware/ff559217">IWDFIoTargetStateManagement::Stop</a> to temporarily stop sending requests to the local I/O target, then later call <b>Start</b> to resume sending requests.

Additionally, if a driver calls <a href="https://msdn.microsoft.com/library/windows/hardware/ff560395">IWDFUsbTargetPipe2::ConfigureContinuousReader</a> to configure a continuous reader for a USB pipe, the driver's <a href="https://msdn.microsoft.com/library/windows/hardware/ff556799">IPnpCallback::OnD0Entry</a> callback function must call <b>Start</b> to start the reader.

Your driver must call <b>Start</b> and <a href="https://msdn.microsoft.com/library/windows/hardware/ff559217">IWDFIoTargetStateManagement::Stop</a> synchronously. After the driver calls one of these functions, it must not call the other function before the first one returns.

For more information about <b>Start</b>, see <a href="https://msdn.microsoft.com/479487b2-5ce5-4522-b195-58ee50d210b6">Controlling a General I/O Target's State in UMDF</a>. 

For more information about I/O targets, see <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/using-i-o-targets-in-umdf">Using I/O Targets in UMDF</a>. 



## -see-also

<a href="..\wudfddi\nn-wudfddi-iwdfiotargetstatemanagement.md">IWDFIoTargetStateManagement</a>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff560289">IWDFRemoteTarget::Stop</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [wdf\wdf]:%20IWDFIoTargetStateManagement::Start method%20 RELEASE:%20(1/11/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

