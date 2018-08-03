---
UID: NF:wdfiotarget.WdfIoTargetStop
title: WdfIoTargetStop function
author: windows-driver-content
description: The WdfIoTargetStop method stops sending queued requests to a local or remote I/O target.
old-location: wdf\wdfiotargetstop.htm
tech.root: wdf
ms.assetid: 3dd5aa58-e5a6-4ee3-9b88-d9cbb7eb558c
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: DFIOTargetRef_80727681-b08c-4025-aea9-d469735ea00c.xml, WdfIoTargetStop, WdfIoTargetStop method, kmdf.wdfiotargetstop, wdf.wdfiotargetstop, wdfiotarget/WdfIoTargetStop
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: wdfiotarget.h
req.include-header: Wdf.h
req.target-type: Universal
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 1.0
req.umdf-ver: 2.0
req.ddi-compliance: DriverCreate, FailD0EntryIoTargetState, KmdfIrql, KmdfIrql2
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Wdf01000.sys (KMDF); WUDFx02000.dll (UMDF)
req.dll: 
req.irql: See Remarks section.
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	LibDef
api_location:
-	Wdf01000.sys
-	Wdf01000.sys.dll
-	WUDFx02000.dll
-	WUDFx02000.dll.dll
api_name:
-	WdfIoTargetStop
product:
- Windows
targetos: Windows
req.typenames: 
---

# WdfIoTargetStop function


## -description


<p class="CCE_Message">[Applies to KMDF and UMDF]

The <b>WdfIoTargetStop</b> method stops sending queued requests to a local or remote I/O target.


## -parameters




### -param IoTarget [in]

A handle to a local or remote I/O target object that was obtained from a previous call to <a href="https://msdn.microsoft.com/library/windows/hardware/ff546017">WdfDeviceGetIoTarget</a> or <a href="https://msdn.microsoft.com/library/windows/hardware/ff548591">WdfIoTargetCreate</a>, or from a method that a specialized I/O target supplies.


### -param Action [in]

A <a href="https://msdn.microsoft.com/library/windows/hardware/ff552388">WDF_IO_TARGET_SENT_IO_ACTION</a>-typed value that specifies how the framework should handle I/O requests that the driver has sent to the I/O target, if the target has not completed the requests.


## -returns



None.

A bug check occurs if the driver supplies an invalid object handle.






## -remarks



If your driver can detect recoverable device errors, you might want your driver to call <b>WdfIoTargetStop</b> to temporarily stop sending requests, then later call <a href="https://msdn.microsoft.com/library/windows/hardware/ff548677">WdfIoTargetStart</a> to resume sending requests.

While stopped, an I/O target continues to accept new requests but does not deliver the queued requests to the appropriate driver.

For more information about possible states for I/O targets, see <a href="https://msdn.microsoft.com/37f756bf-b655-428e-b72c-f86c71f1a2db">Controlling a General I/O Target's State</a>.

If a driver calls <a href="https://msdn.microsoft.com/library/windows/hardware/ff551130">WdfUsbTargetPipeConfigContinuousReader</a> to configure a continuous reader for a USB pipe, the driver's <a href="https://msdn.microsoft.com/bc3af732-f9ab-43a4-bc6f-7fa0b4c05a66">EvtDeviceD0Exit</a> callback function must call <b>WdfIoTargetStop</b> to stop the reader.

If a driver has called <b>WdfIoTargetStop</b>, it can still send a request to the target by setting the <b>WDF_REQUEST_OPTION_IGNORE_TARGET_STATE</b> flag in the request's <a href="https://msdn.microsoft.com/library/windows/hardware/ff552491">WDF_REQUEST_SEND_OPTIONS</a> structure. If a driver sets this flag, the driver can send a request, such as a request to reset a USB pipe (see <a href="https://msdn.microsoft.com/library/windows/hardware/ff551156">WdfUsbTargetPipeResetSynchronously</a>), to a device after the driver has called <b>WdfIoTargetStop</b>.

When a driver calls <b>WdfIoTargetStop</b>, the framework does not attempt to cancel or wait for I/O requests that were previously sent to the target using either the <b>WDF_REQUEST_SEND_OPTION_IGNORE_TARGET_STATE</b> flag or the <b>WDF_REQUEST_SEND_OPTION_SEND_AND_FORGET</b> flag in the request's <a href="https://msdn.microsoft.com/library/windows/hardware/ff552491">WDF_REQUEST_SEND_OPTIONS</a> structure.

Your driver must call <a href="https://msdn.microsoft.com/library/windows/hardware/ff548677">WdfIoTargetStart</a> and <b>WdfIoTargetStop</b> synchronously. After the driver calls one of these functions, it must not call either function before the first call returns.

Your driver can call <b>WdfIoTargetStop</b> multiple times from a single thread without calling <a href="https://msdn.microsoft.com/library/windows/hardware/ff548677">WdfIoTargetStart</a>. For example, your driver might do the following:

<ol>
<li>
Call <b>WdfIoTargetStop</b> and specify an <i>Action</i> value of <b>WdfIoTargetLeaveSentIoPending</b>. 

</li>
<li>
Determine whether the target should resume processing I/O requests. 

</li>
<li>
If the target should resume, call <a href="https://msdn.microsoft.com/library/windows/hardware/ff548677">WdfIoTargetStart</a>. Otherwise, call <b>WdfIoTargetStop</b> again with an <i>Action</i> value of <b>WdfIoTargetCancelSentIo</b>. 

</li>
</ol>
<div class="alert"><b>Note</b>  It is not safe to call <b>WdfIoTargetStop</b> multiple times from different threads.</div>
<div> </div>
For more information about I/O targets, see <a href="https://msdn.microsoft.com/77fd1b64-c3a9-4e12-ac69-0e3725695795">Using I/O Targets</a>.

If the driver has called <a href="https://msdn.microsoft.com/library/windows/hardware/ff551130">WdfUsbTargetPipeConfigContinuousReader</a> for the pipe, <b>WdfIoTargetStop</b> must be called at IRQL = PASSIVE_LEVEL.

If the driver has not called <a href="https://msdn.microsoft.com/library/windows/hardware/ff551130">WdfUsbTargetPipeConfigContinuousReader</a> and if the <i>Action</i> parameter of <b>WdfIoTargetStop</b> is <b>WdfIoTargetLeaveSentIoPending</b>, <b>WdfIoTargetStop</b> can be called at IRQL &lt;= DISPATCH_LEVEL. Otherwise, <b>WdfIoTargetStop</b> is called at IRQL = PASSIVE_LEVEL. 


#### Examples

The following code example shows how an <a href="https://msdn.microsoft.com/bc3af732-f9ab-43a4-bc6f-7fa0b4c05a66">EvtDeviceD0Exit</a> callback function can call <b>WdfIoTargetStop</b>, if the driver uses a continuous reader for a USB pipe. 

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>NTSTATUS
MyEvtDeviceD0Exit(
    IN  WDFDEVICE Device,
    IN  WDF_POWER_DEVICE_STATE TargetState
)
{
    PDEVICE_CONTEXT  pDeviceContext;
    pDeviceContext = GetMyDeviceContext(Device);

    WdfIoTargetStop(
                    WdfUsbTargetPipeGetIoTarget(pDeviceContext-&gt;InterruptPipe),
                    WdfIoTargetCancelSentIo
                    );

    return STATUS_SUCCESS;
}</pre>
</td>
</tr>
</table></span></div>



## -see-also




<a href="https://msdn.microsoft.com/bc3af732-f9ab-43a4-bc6f-7fa0b4c05a66">EvtDeviceD0Exit</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff552491">WDF_REQUEST_SEND_OPTIONS</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff546017">WdfDeviceGetIoTarget</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff548591">WdfIoTargetCreate</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff548677">WdfIoTargetStart</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff551130">WdfUsbTargetPipeConfigContinuousReader</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff551156">WdfUsbTargetPipeResetSynchronously</a>
 

 

