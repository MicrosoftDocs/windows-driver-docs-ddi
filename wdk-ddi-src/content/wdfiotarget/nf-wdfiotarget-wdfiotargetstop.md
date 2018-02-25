---
UID: NF:wdfiotarget.WdfIoTargetStop
title: WdfIoTargetStop function
author: windows-driver-content
description: The WdfIoTargetStop method stops sending queued requests to a local or remote I/O target.
old-location: wdf\wdfiotargetstop.htm
old-project: wdf
ms.assetid: 3dd5aa58-e5a6-4ee3-9b88-d9cbb7eb558c
ms.author: windowsdriverdev
ms.date: 2/20/2018
ms.keywords: ",  , DFIOTargetRef_80727681-b08c-4025-aea9-d469735ea00c.xml, I, S, T, W, WdfIoTargetStop, WdfIoTargetStop method, a, d, e, f, g, kmdf.wdfiotargetstop, o, p, r, t, wdf.wdfiotargetstop, wdfiotarget/WdfIoTargetStop"
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	LibDef
apilocation:
-	Wdf01000.sys
-	Wdf01000.sys.dll
-	WUDFx02000.dll
-	WUDFx02000.dll.dll
apiname:
-	WdfIoTargetStop
product: Windows
targetos: Windows
req.typenames: WDF_IO_TARGET_STATE, *PWDF_IO_TARGET_STATE
req.product: Windows 10 or later.
---

# WdfIoTargetStop function


## -description


<p class="CCE_Message">[Applies to KMDF and UMDF]

The <b>WdfIoTargetStop</b> method stops sending queued requests to a local or remote I/O target.


## -syntax


````
VOID WdfIoTargetStop(
  _In_ WDFIOTARGET                  IoTarget,
  _In_ WDF_IO_TARGET_SENT_IO_ACTION Action
);
````


## -parameters




### -param IoTarget [in]

A handle to a local or remote I/O target object that was obtained from a previous call to <a href="..\wdfdevice\nf-wdfdevice-wdfdevicegetiotarget.md">WdfDeviceGetIoTarget</a> or <a href="..\wdfiotarget\nf-wdfiotarget-wdfiotargetcreate.md">WdfIoTargetCreate</a>, or from a method that a specialized I/O target supplies.


### -param Action [in]

A <a href="..\wudfddi_types\ne-wudfddi_types-_wdf_io_target_sent_io_action.md">WDF_IO_TARGET_SENT_IO_ACTION</a>-typed value that specifies how the framework should handle I/O requests that the driver has sent to the I/O target, if the target has not completed the requests.


## -returns



None.

A bug check occurs if the driver supplies an invalid object handle.






## -remarks



If your driver can detect recoverable device errors, you might want your driver to call <b>WdfIoTargetStop</b> to temporarily stop sending requests, then later call <a href="..\wdfiotarget\nf-wdfiotarget-wdfiotargetstart.md">WdfIoTargetStart</a> to resume sending requests.

While stopped, an I/O target continues to accept new requests but does not deliver the queued requests to the appropriate driver.

For more information about possible states for I/O targets, see <a href="https://msdn.microsoft.com/37f756bf-b655-428e-b72c-f86c71f1a2db">Controlling a General I/O Target's State</a>.

If a driver calls <a href="..\wdfusb\nf-wdfusb-wdfusbtargetpipeconfigcontinuousreader.md">WdfUsbTargetPipeConfigContinuousReader</a> to configure a continuous reader for a USB pipe, the driver's <a href="..\wdfdevice\nc-wdfdevice-evt_wdf_device_d0_exit.md">EvtDeviceD0Exit</a> callback function must call <b>WdfIoTargetStop</b> to stop the reader.

If a driver has called <b>WdfIoTargetStop</b>, it can still send a request to the target by setting the <b>WDF_REQUEST_OPTION_IGNORE_TARGET_STATE</b> flag in the request's <a href="..\wdfrequest\ns-wdfrequest-_wdf_request_send_options.md">WDF_REQUEST_SEND_OPTIONS</a> structure. If a driver sets this flag, the driver can send a request, such as a request to reset a USB pipe (see <a href="..\wdfusb\nf-wdfusb-wdfusbtargetpiperesetsynchronously.md">WdfUsbTargetPipeResetSynchronously</a>), to a device after the driver has called <b>WdfIoTargetStop</b>.

When a driver calls <b>WdfIoTargetStop</b>, the framework does not attempt to cancel or wait for I/O requests that were previously sent to the target using either the <b>WDF_REQUEST_SEND_OPTION_IGNORE_TARGET_STATE</b> flag or the <b>WDF_REQUEST_SEND_OPTION_SEND_AND_FORGET</b> flag in the request's <a href="..\wdfrequest\ns-wdfrequest-_wdf_request_send_options.md">WDF_REQUEST_SEND_OPTIONS</a> structure.

Your driver must call <a href="..\wdfiotarget\nf-wdfiotarget-wdfiotargetstart.md">WdfIoTargetStart</a> and <b>WdfIoTargetStop</b> synchronously. After the driver calls one of these functions, it must not call either function before the first call returns.

Your driver can call <b>WdfIoTargetStop</b> multiple times from a single thread without calling <a href="..\wdfiotarget\nf-wdfiotarget-wdfiotargetstart.md">WdfIoTargetStart</a>. For example, your driver might do the following:

<ol>
<li>
Call <b>WdfIoTargetStop</b> and specify an <i>Action</i> value of <b>WdfIoTargetLeaveSentIoPending</b>. 

</li>
<li>
Determine whether the target should resume processing I/O requests. 

</li>
<li>
If the target should resume, call <a href="..\wdfiotarget\nf-wdfiotarget-wdfiotargetstart.md">WdfIoTargetStart</a>. Otherwise, call <b>WdfIoTargetStop</b> again with an <i>Action</i> value of <b>WdfIoTargetCancelSentIo</b>. 

</li>
</ol>
<div class="alert"><b>Note</b>  It is not safe to call <b>WdfIoTargetStop</b> multiple times from different threads.</div>
<div> </div>
For more information about I/O targets, see <a href="https://msdn.microsoft.com/77fd1b64-c3a9-4e12-ac69-0e3725695795">Using I/O Targets</a>.

If the driver has called <a href="..\wdfusb\nf-wdfusb-wdfusbtargetpipeconfigcontinuousreader.md">WdfUsbTargetPipeConfigContinuousReader</a> for the pipe, <b>WdfIoTargetStop</b> must be called at IRQL = PASSIVE_LEVEL.

If the driver has not called <a href="..\wdfusb\nf-wdfusb-wdfusbtargetpipeconfigcontinuousreader.md">WdfUsbTargetPipeConfigContinuousReader</a> and if the <i>Action</i> parameter of <b>WdfIoTargetStop</b> is <b>WdfIoTargetLeaveSentIoPending</b>, <b>WdfIoTargetStop</b> can be called at IRQL &lt;= DISPATCH_LEVEL. Otherwise, <b>WdfIoTargetStop</b> is called at IRQL = PASSIVE_LEVEL. 


#### Examples

The following code example shows how an <a href="..\wdfdevice\nc-wdfdevice-evt_wdf_device_d0_exit.md">EvtDeviceD0Exit</a> callback function can call <b>WdfIoTargetStop</b>, if the driver uses a continuous reader for a USB pipe. 

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

<a href="..\wdfiotarget\nf-wdfiotarget-wdfiotargetstart.md">WdfIoTargetStart</a>



<a href="..\wdfiotarget\nf-wdfiotarget-wdfiotargetcreate.md">WdfIoTargetCreate</a>



<a href="..\wdfusb\nf-wdfusb-wdfusbtargetpipeconfigcontinuousreader.md">WdfUsbTargetPipeConfigContinuousReader</a>



<a href="..\wdfusb\nf-wdfusb-wdfusbtargetpiperesetsynchronously.md">WdfUsbTargetPipeResetSynchronously</a>



<a href="..\wdfdevice\nf-wdfdevice-wdfdevicegetiotarget.md">WdfDeviceGetIoTarget</a>



<a href="..\wdfrequest\ns-wdfrequest-_wdf_request_send_options.md">WDF_REQUEST_SEND_OPTIONS</a>



<a href="..\wdfdevice\nc-wdfdevice-evt_wdf_device_d0_exit.md">EvtDeviceD0Exit</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [wdf\wdf]:%20WdfIoTargetStop method%20 RELEASE:%20(2/20/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

