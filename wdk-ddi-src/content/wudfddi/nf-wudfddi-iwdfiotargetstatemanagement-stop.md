---
UID: NF:wudfddi.IWDFIoTargetStateManagement.Stop
title: IWDFIoTargetStateManagement::Stop
author: windows-driver-content
description: The Stop method stops sending queued requests to a local I/O target.
old-location: wdf\iwdfiotargetstatemanagement_stop.htm
tech.root: wdf
ms.assetid: c0d5ea59-c1df-403b-9e74-b1ab60761640
ms.date: 2/26/2018
ms.keywords: IWDFIoTargetStateManagement interface,Stop method, IWDFIoTargetStateManagement.Stop, IWDFIoTargetStateManagement::Stop, Stop, Stop method, Stop method,IWDFIoTargetStateManagement interface, UMDFIoTargetObjectRef_e3b5b892-9d72-49ad-8d58-9cf751f831ad.xml, umdf.iwdfiotargetstatemanagement_stop, wdf.iwdfiotargetstatemanagement_stop, wudfddi/IWDFIoTargetStateManagement::Stop
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
-	IWDFIoTargetStateManagement.Stop
product:
- Windows
targetos: Windows
req.typenames: 
---

# IWDFIoTargetStateManagement::Stop


## -description


<p class="CCE_Message">[<b>Warning:</b> UMDF 2 is the latest version of UMDF and supersedes UMDF 1.  All new UMDF drivers should be written using UMDF 2.  No new features are being added to UMDF 1 and there is limited support for UMDF 1 on newer versions of Windows 10.  Universal Windows drivers must use UMDF 2.  For more info, see <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/getting-started-with-umdf-version-2">Getting Started with UMDF</a>.]

The <b>Stop</b> method stops sending queued requests to a <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/general-i-o-targets-in-umdf">local  I/O target</a>.


## -parameters




### -param Action [in]

A <a href="https://msdn.microsoft.com/library/windows/hardware/ff552388">WDF_IO_TARGET_SENT_IO_ACTION</a>-typed value that identifies how to handle sent I/O when the I/O target object is stopped.


## -returns



<b>Stop</b> always returns S_OK.




## -remarks



If your driver can detect recoverable device errors, you might want your driver to call <b>Stop</b> to temporarily stop sending requests to the local I/O target, then later call <a href="https://msdn.microsoft.com/library/windows/hardware/ff559213">IWDFIoTargetStateManagement::Start</a> to resume sending requests.

Additionally, if a driver calls <a href="https://msdn.microsoft.com/library/windows/hardware/ff560395">IWDFUsbTargetPipe2::ConfigureContinuousReader</a> to configure a continuous reader for a USB pipe, the driver's <a href="https://msdn.microsoft.com/library/windows/hardware/ff556803">IPnpCallback::OnD0Exit</a> callback function must call <b>Stop</b> to stop the reader.

If a driver has called <b>Stop</b>, it can still send a request to the target by setting the WDF_REQUEST_OPTION_IGNORE_TARGET_STATE flag when it calls <a href="https://msdn.microsoft.com/library/windows/hardware/ff559149">IWDFIoRequest::Send</a>. If a driver sets this flag, the driver can send a request, such as a request to reset a USB pipe (see <a href="https://msdn.microsoft.com/library/windows/hardware/ff560416">IWDFUsbTargetPipe::Reset</a>), to a device after the driver has called <b>Stop</b>.

Your driver must call <a href="https://msdn.microsoft.com/library/windows/hardware/ff559213">IWDFIoTargetStateManagement::Start</a> and <b>Stop</b> synchronously. After the driver calls one of these functions, it must not call either function before the first call returns.

Your driver can call <b>Stop</b> multiple times without calling <a href="https://msdn.microsoft.com/library/windows/hardware/ff559213">IWDFIoTargetStateManagement::Start</a>. For example, your driver might do the following:

<ol>
<li>
Call <b>Stop</b> and specify an <i>Action</i> value of <b>WdfIoTargetLeaveSentIoPending</b>. 

</li>
<li>
Determine whether the target should resume processing I/O requests. 

</li>
<li>
If the target should resume, call <a href="https://msdn.microsoft.com/library/windows/hardware/ff559213">IWDFIoTargetStateManagement::Start</a>. Otherwise, call <b>Stop</b> again with an <i>Action</i> value of <b>WdfIoTargetCancelSentIo</b>. 

</li>
</ol>
For more information about <b>Stop</b>, see <a href="https://msdn.microsoft.com/37f756bf-b655-428e-b72c-f86c71f1a2db">Controlling a General I/O Target's State</a>. 

For more information about I/O targets, see <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/using-i-o-targets-in-umdf">Using I/O Targets</a>.


#### Examples

The following code example shows how an <a href="https://msdn.microsoft.com/library/windows/hardware/ff556803">IPnpCallback::OnD0Exit</a> callback function can call <b>Stop</b>, if the driver uses a continuous reader for a USB pipe. (To see how to obtain the <a href="https://msdn.microsoft.com/library/windows/hardware/ff559198">IWDFIoTargetStateManagement</a> interface, see the code example at <a href="https://msdn.microsoft.com/library/windows/hardware/ff559213">IWDFIoTargetStateManagement::Start</a>.)

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>HRESULT
CMyDevice::OnD0Exit(
    __in IWDFDevice*  pWdfDevice,
    __in WDF_POWER_DEVICE_STATE  previousState
    )
{
    HRESULT hr;
    hr = m_pIoTargetInterruptPipeStateMgmt-&gt;Stop(WdfIoTargetCancelSentIo);
    return hr;
}</pre>
</td>
</tr>
</table></span></div>



## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff559198">IWDFIoTargetStateManagement</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff560289">IWDFRemoteTarget::Stop</a>
 

 

