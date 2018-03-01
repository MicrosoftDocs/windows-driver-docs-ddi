---
UID: NE:wdfiotarget._WDF_IO_TARGET_PURGE_IO_ACTION
title: "_WDF_IO_TARGET_PURGE_IO_ACTION"
author: windows-driver-content
description: The WDF_IO_TARGET_PURGE_IO_ACTION enumeration identifies the actions that the framework can take when a driver calls WdfIoTargetPurge to purge an I/O target.
old-location: wdf\wdf_io_target_purge_io_action.htm
old-project: wdf
ms.assetid: E282976A-4143-468C-B944-FBBAD5BBA388
ms.author: windowsdriverdev
ms.date: 2/20/2018
ms.keywords: WDF_IO_TARGET_PURGE_IO_ACTION, WDF_IO_TARGET_PURGE_IO_ACTION enumeration, WdfIoTargetPurgeIo, WdfIoTargetPurgeIoAndWait, WdfIoTargetPurgeIoUndefined, _WDF_IO_TARGET_PURGE_IO_ACTION, kmdf.wdf_io_target_purge_io_action, wdf.wdf_io_target_purge_io_action, wdfiotarget/WDF_IO_TARGET_PURGE_IO_ACTION, wdfiotarget/WdfIoTargetPurgeIo, wdfiotarget/WdfIoTargetPurgeIoAndWait, wdfiotarget/WdfIoTargetPurgeIoUndefined
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
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
req.irql: PASSIVE_LEVEL
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	wdfiotarget.h
api_name:
-	WDF_IO_TARGET_PURGE_IO_ACTION
product: Windows
targetos: Windows
req.typenames: WDF_IO_TARGET_PURGE_IO_ACTION
req.product: Windows 10 or later.
---

# _WDF_IO_TARGET_PURGE_IO_ACTION enumeration


## -description


<p class="CCE_Message">[Applies to KMDF and UMDF]


   The 
  <b>WDF_IO_TARGET_PURGE_IO_ACTION</b> enumeration identifies the actions that the framework can take when a driver calls <a href="..\wdfiotarget\nf-wdfiotarget-wdfiotargetpurge.md">WdfIoTargetPurge</a> to purge an I/O target.



## -syntax


````
typedef enum _WDF_IO_TARGET_PURGE_IO_ACTION { 
  WdfIoTargetPurgeIoUndefined  = 0,
  WdfIoTargetPurgeIoAndWait    = 1,
  WdfIoTargetPurgeIo           = 2
} WDF_IO_TARGET_PURGE_IO_ACTION;
````


## -enum-fields




### -field WdfIoTargetPurgeIoUndefined

Reserved for system use.


### -field WdfIoTargetPurgeIoAndWait

The framework attempts to cancel all of the I/O requests in the target's queue, and waits until all delivered requests are completed or canceled, before <a href="..\wdfiotarget\nf-wdfiotarget-wdfiotargetpurge.md">WdfIoTargetPurge</a> returns. If the framework receives additional requests for the queue, it completes them with a completion status value of STATUS_INVALID_DEVICE_STATE.



### -field WdfIoTargetPurgeIo

The framework attempts to cancel all of the target queue's I/O requests, before <a href="..\wdfiotarget\nf-wdfiotarget-wdfiotargetpurge.md">WdfIoTargetPurge</a> returns.


## -remarks



The <b>WDF_IO_TARGET_PURGE_IO_ACTION</b> enumeration is used as an input parameter to the <a href="..\wdfiotarget\nf-wdfiotarget-wdfiotargetpurge.md">WdfIoTargetPurge</a> method.

If your driver specifies the <b>WdfIoTargetPurgeIoAndWait</b> flag, the driver must not call <a href="..\wdfiotarget\nf-wdfiotarget-wdfiotargetpurge.md">WdfIoTargetPurge</a> from a request handler, a <a href="..\wdfrequest\nc-wdfrequest-evt_wdf_request_completion_routine.md">CompletionRoutine</a> callback function, or an <a href="..\wdfusb\nc-wdfusb-evt_wdf_usb_readers_failed.md">EvtUsbTargetPipeReadersFailed</a> callback function.




## -see-also

<a href="..\wdfiotarget\nf-wdfiotarget-wdfiotargetpurge.md">WdfIoTargetPurge</a>



<a href="..\wudfddi_types\ne-wudfddi_types-_wdf_io_target_state.md">WDF_IO_TARGET_STATE</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [wdf\wdf]:%20WDF_IO_TARGET_PURGE_IO_ACTION enumeration%20 RELEASE:%20(2/20/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

