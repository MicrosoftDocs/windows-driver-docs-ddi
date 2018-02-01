---
UID: NF:wudfddi.IWDFRemoteTarget.Start
title: IWDFRemoteTarget::Start method
author: windows-driver-content
description: The IWDFRemoteTarget::Start method restarts a remote I/O target that is stopped.
old-location: wdf\iwdfremotetarget_start.htm
old-project: wdf
ms.assetid: f0f21d34-21f2-48ac-994f-e050f4447745
ms.author: windowsdriverdev
ms.date: 1/11/2018
ms.keywords: Start method, wdf.iwdfremotetarget_start, IWDFRemoteTarget::Start, umdf.iwdfremotetarget_start, UMDFIoTargetObjectRef_8e44c1ab-5ce6-4c4a-a7dc-e9de4b10ba12.xml, wudfddi/IWDFRemoteTarget::Start, Start method, IWDFRemoteTarget interface, IWDFRemoteTarget, Start, IWDFRemoteTarget interface, Start method
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
-	IWDFRemoteTarget.Start
product: Windows
targetos: Windows
req.typenames: POWER_ACTION, *PPOWER_ACTION
req.product: Windows 10 or later.
---

# IWDFRemoteTarget::Start method


## -description


<p class="CCE_Message">[<b>Warning:</b> UMDF 2 is the latest version of UMDF and supersedes UMDF 1.  All new UMDF drivers should be written using UMDF 2.  No new features are being added to UMDF 1 and there is limited support for UMDF 1 on newer versions of Windows 10.  Universal Windows drivers must use UMDF 2.  For more info, see <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/getting-started-with-umdf-version-2">Getting Started with UMDF</a>.]

The <b>IWDFRemoteTarget::Start</b> method restarts a <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/general-i-o-targets-in-umdf">remote I/O target</a> that is stopped.


## -syntax


````
HRESULT Start();
````


## -parameters





## -returns


<b>Start</b> returns S_OK if the operation succeeds. Otherwise, the method might return the following value:
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
The remote I/O target object was deleted.

</td>
</tr>
</table> 

This method might return one of the other values that Winerror.h contains.





## -remarks


The <b>Start</b> method resumes processing any I/O requests that are in queued to the remote I/O target. After a driver calls <a href="https://msdn.microsoft.com/library/windows/hardware/ff560289">IWDFRemoteTarget::Stop</a>, the driver must call <b>Start</b> so the framework can resume sending I/O requests to the I/O target.

For more information about <b>Start</b>, and how to use remote I/O targets in UMDF-based drivers, see <a href="https://msdn.microsoft.com/479487b2-5ce5-4522-b195-58ee50d210b6">Controlling a General I/O Target's State in UMDF</a>.



## -see-also

<a href="..\wudfddi\nn-wudfddi-iwdfremotetarget.md">IWDFRemoteTarget</a>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff560289">IWDFRemoteTarget::Stop</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [wdf\wdf]:%20IWDFRemoteTarget::Start method%20 RELEASE:%20(1/11/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

