---
UID: NE:wdfiotarget._WDF_IO_TARGET_PURGE_IO_ACTION
title: _WDF_IO_TARGET_PURGE_IO_ACTION (wdfiotarget.h)
description: The WDF_IO_TARGET_PURGE_IO_ACTION enumeration identifies the actions that the framework can take when a driver calls WdfIoTargetPurge to purge an I/O target.
old-location: wdf\wdf_io_target_purge_io_action.htm
tech.root: wdf
ms.assetid: E282976A-4143-468C-B944-FBBAD5BBA388
ms.date: 02/26/2018
ms.keywords: WDF_IO_TARGET_PURGE_IO_ACTION, WDF_IO_TARGET_PURGE_IO_ACTION enumeration, WdfIoTargetPurgeIo, WdfIoTargetPurgeIoAndWait, WdfIoTargetPurgeIoUndefined, _WDF_IO_TARGET_PURGE_IO_ACTION, kmdf.wdf_io_target_purge_io_action, wdf.wdf_io_target_purge_io_action, wdfiotarget/WDF_IO_TARGET_PURGE_IO_ACTION, wdfiotarget/WdfIoTargetPurgeIo, wdfiotarget/WdfIoTargetPurgeIoAndWait, wdfiotarget/WdfIoTargetPurgeIoUndefined
ms.topic: enum
f1_keywords:
 - "wdfiotarget/WDF_IO_TARGET_PURGE_IO_ACTION"
req.header: wdfiotarget.h
req.include-header: Wdf.h
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 1.11
req.umdf-ver: 2.0
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
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
- wdfiotarget.h
api_name:
- WDF_IO_TARGET_PURGE_IO_ACTION
product:
- Windows
targetos: Windows
req.typenames: WDF_IO_TARGET_PURGE_IO_ACTION
---

# _WDF_IO_TARGET_PURGE_IO_ACTION enumeration


## -description


<p class="CCE_Message">[Applies to KMDF and UMDF]</p>


   The 
  <b>WDF_IO_TARGET_PURGE_IO_ACTION</b> enumeration identifies the actions that the framework can take when a driver calls <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdfiotarget/nf-wdfiotarget-wdfiotargetpurge">WdfIoTargetPurge</a> to purge an I/O target.



## -enum-fields




### -field WdfIoTargetPurgeIoUndefined

Reserved for system use.


### -field WdfIoTargetPurgeIoAndWait

The framework attempts to cancel all of the I/O requests in the target's queue, and waits until all delivered requests are completed or canceled, before <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdfiotarget/nf-wdfiotarget-wdfiotargetpurge">WdfIoTargetPurge</a> returns. If the framework receives additional requests for the queue, it completes them with a completion status value of STATUS_INVALID_DEVICE_STATE.



### -field WdfIoTargetPurgeIo

The framework attempts to cancel all of the target queue's I/O requests, before <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdfiotarget/nf-wdfiotarget-wdfiotargetpurge">WdfIoTargetPurge</a> returns.


## -remarks



The <b>WDF_IO_TARGET_PURGE_IO_ACTION</b> enumeration is used as an input parameter to the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdfiotarget/nf-wdfiotarget-wdfiotargetpurge">WdfIoTargetPurge</a> method.

If your driver specifies the <b>WdfIoTargetPurgeIoAndWait</b> flag, the driver must not call <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdfiotarget/nf-wdfiotarget-wdfiotargetpurge">WdfIoTargetPurge</a> from a request handler, a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdfrequest/nc-wdfrequest-evt_wdf_request_completion_routine">CompletionRoutine</a> callback function, or an <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdfusb/nc-wdfusb-evt_wdf_usb_readers_failed">EvtUsbTargetPipeReadersFailed</a> callback function.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdfiotarget/ne-wdfiotarget-_wdf_io_target_state">WDF_IO_TARGET_STATE</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdfiotarget/nf-wdfiotarget-wdfiotargetpurge">WdfIoTargetPurge</a>
 

 

