---
UID: NE:wudfddi_types._WDF_IO_TARGET_SENT_IO_ACTION
title: _WDF_IO_TARGET_SENT_IO_ACTION (wudfddi_types.h)
description: The WDF_IO_TARGET_SENT_IO_ACTION enumeration identifies the actions that the framework can take when a driver calls IWDFIoTargetStateManagement::Stop or IWDFRemoteTarget::Stop to stop an I/O target.
old-location: wdf\wdf_io_target_sent_io_action__umdf_.htm
tech.root: wdf
ms.assetid: 9cdcf964-9f2d-437f-8693-de5bb4bb9895
ms.date: 02/26/2018
ms.keywords: WDF_IO_TARGET_SENT_IO_ACTION, WDF_IO_TARGET_SENT_IO_ACTION enumeration, WdfIoTargetCancelSentIo, WdfIoTargetLeaveSentIoPending, WdfIoTargetSentIoMaximum, WdfIoTargetSentIoUndefined, WdfIoTargetWaitForSentIoToComplete, _WDF_IO_TARGET_SENT_IO_ACTION, umdf.wdf_io_target_sent_io_action__umdf_, umdfstructs_c5c41acc-35ac-4894-bb1b-af3b3a9b75d1.xml, wdf.wdf_io_target_sent_io_action__umdf_, wudfddi_types/WDF_IO_TARGET_SENT_IO_ACTION, wudfddi_types/WdfIoTargetCancelSentIo, wudfddi_types/WdfIoTargetLeaveSentIoPending, wudfddi_types/WdfIoTargetSentIoMaximum, wudfddi_types/WdfIoTargetSentIoUndefined, wudfddi_types/WdfIoTargetWaitForSentIoToComplete
f1_keywords:
 - "wudfddi_types/WDF_IO_TARGET_SENT_IO_ACTION"
req.header: wudfddi_types.h
req.include-header: Wudfddi.h
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 1.0
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: Unavailable in UMDF 2.0 and later.
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: 
topic_type:
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- Wudfddi_types.h
api_name:
- WDF_IO_TARGET_SENT_IO_ACTION
product:
- Windows
targetos: Windows
req.typenames: WDF_IO_TARGET_SENT_IO_ACTION
---

# _WDF_IO_TARGET_SENT_IO_ACTION enumeration


## -description


<p class="CCE_Message">[<b>Warning:</b> UMDF 2 is the latest version of UMDF and supersedes UMDF 1.  All new UMDF drivers should be written using UMDF 2.  No new features are being added to UMDF 1 and there is limited support for UMDF 1 on newer versions of Windows 10.  Universal Windows drivers must use UMDF 2.  For more info, see <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/getting-started-with-umdf-version-2">Getting Started with UMDF</a>.]


The <b>WDF_IO_TARGET_SENT_IO_ACTION</b> enumeration identifies the actions that the framework can take when a driver calls <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wudfddi/nf-wudfddi-iwdfiotargetstatemanagement-stop">IWDFIoTargetStateManagement::Stop</a> or  <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wudfddi/nf-wudfddi-iwdfremotetarget-stop">IWDFRemoteTarget::Stop</a> to stop an I/O target.


## -enum-fields




### -field WdfIoTargetSentIoUndefined

Reservied for system use.


### -field WdfIoTargetCancelSentIo

Before the framework stops the I/O target, it will attempt to cancel I/O requests that are in the I/O target's queue. The framework cancels all of the target queue's I/O requests before <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wudfddi/nf-wudfddi-iwdfiotargetstatemanagement-stop">IWDFIoTargetStateManagement::Stop</a> or <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wudfddi/nf-wudfddi-iwdfremotetarget-stop">IWDFRemoteTarget::Stop</a> returns.


### -field WdfIoTargetWaitForSentIoToComplete

Before the framework stops the I/O target, it will wait for I/O requests that are in the I/O target's queue to be completed. The framework completes all of the target queue's I/O requests, and calls each request's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wudfddi/nf-wudfddi-irequestcallbackrequestcompletion-oncompletion">IRequestCallbackRequestCompletion::OnCompletion</a> callback function, before <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wudfddi/nf-wudfddi-iwdfiotargetstatemanagement-stop">IWDFIoTargetStateManagement::Stop</a> or <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wudfddi/nf-wudfddi-iwdfremotetarget-stop">IWDFRemoteTarget::Stop</a> returns.


### -field WdfIoTargetLeaveSentIoPending

The framework will leave I/O requests in the I/O target's queue. The requests remain in the target's queue until the driver calls <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wudfddi/nf-wudfddi-iwdfiotargetstatemanagement-start">IWDFIoTargetStateManagement::Start</a> or <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wudfddi/nf-wudfddi-iwdfremotetarget-start">IWDFRemoteTarget::Start</a> or the device is removed.


### -field WdfIoTargetSentIoMaximum

Valid enumeration values were exceeded.


## -remarks



The <b>WDF_IO_TARGET_SENT_IO_ACTION</b> enumeration is used as an input parameter to the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wudfddi/nf-wudfddi-iwdfiotargetstatemanagement-stop">IWDFIoTargetStateManagement::Stop</a> and  <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wudfddi/nf-wudfddi-iwdfremotetarget-stop">IWDFRemoteTarget::Stop</a> methods.

If your driver specifies the <b>WdfIoTargetWaitForSentIoToComplete</b> flag, the driver must not call <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wudfddi/nf-wudfddi-iwdfiotargetstatemanagement-stop">IWDFIoTargetStateManagement::Stop</a> or <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wudfddi/nf-wudfddi-iwdfremotetarget-stop">IWDFRemoteTarget::Stop</a> from a request handler, an <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wudfddi/nf-wudfddi-irequestcallbackrequestcompletion-oncompletion">IRequestCallbackRequestCompletion::OnCompletion</a> callback function, or an <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wudfusb/nf-wudfusb-iusbtargetpipecontinuousreadercallbackreadersfailed-onreaderfailure">IUsbTargetPipeContinuousReaderCallbackReadersFailed::OnReaderFailure</a> callback function.

For the KMDF version of this enumeration, see <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfiotarget/ne-wdfiotarget-_wdf_io_target_sent_io_action">WDF_IO_TARGET_SENT_IO_ACTION</a>.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfiotarget/ne-wdfiotarget-_wdf_io_target_sent_io_action">WDF_IO_TARGET_SENT_IO_ACTION</a>
 

 

