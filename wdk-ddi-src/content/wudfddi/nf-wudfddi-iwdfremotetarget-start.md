---
UID: NF:wudfddi.IWDFRemoteTarget.Start
title: IWDFRemoteTarget::Start
author: windows-driver-content
description: The IWDFRemoteTarget::Start method restarts a remote I/O target that is stopped.
old-location: wdf\iwdfremotetarget_start.htm
tech.root: wdf
ms.assetid: f0f21d34-21f2-48ac-994f-e050f4447745
ms.date: 2/26/2018
ms.keywords: IWDFRemoteTarget interface,Start method, IWDFRemoteTarget.Start, IWDFRemoteTarget::Start, Start, Start method, Start method,IWDFRemoteTarget interface, UMDFIoTargetObjectRef_8e44c1ab-5ce6-4c4a-a7dc-e9de4b10ba12.xml, umdf.iwdfremotetarget_start, wdf.iwdfremotetarget_start, wudfddi/IWDFRemoteTarget::Start
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
req.lib: 
req.dll: WUDFx.dll
req.irql: 
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	COM
api_location:
-	WUDFx.dll
api_name:
-	IWDFRemoteTarget.Start
product:
- Windows
targetos: Windows
req.typenames: 
---

# IWDFRemoteTarget::Start


## -description


<p class="CCE_Message">[<b>Warning:</b> UMDF 2 is the latest version of UMDF and supersedes UMDF 1.  All new UMDF drivers should be written using UMDF 2.  No new features are being added to UMDF 1 and there is limited support for UMDF 1 on newer versions of Windows 10.  Universal Windows drivers must use UMDF 2.  For more info, see <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/getting-started-with-umdf-version-2">Getting Started with UMDF</a>.]

The <b>IWDFRemoteTarget::Start</b> method restarts a <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/general-i-o-targets-in-umdf">remote I/O target</a> that is stopped.


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


#### Examples

The following code example restarts a remote I/O target.

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>if (S_OK == RemoteTarget-&gt;Start())
{
    //
    // Resume sending I/O requests to the I/O target.
    //
...}</pre>
</td>
</tr>
</table></span></div>



## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff560247">IWDFRemoteTarget</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff560289">IWDFRemoteTarget::Stop</a>
 

 

