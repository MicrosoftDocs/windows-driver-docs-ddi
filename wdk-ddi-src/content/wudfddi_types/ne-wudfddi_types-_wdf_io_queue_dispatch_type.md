---
UID: NE:wudfddi_types._WDF_IO_QUEUE_DISPATCH_TYPE
title: _WDF_IO_QUEUE_DISPATCH_TYPE (wudfddi_types.h)
description: The WDF_IO_QUEUE_DISPATCH_TYPE enumeration contains values that identify how a driver must receive requests from an I/O queue.
old-location: wdf\wdf_io_queue_dispatch_type_umdf.htm
tech.root: wdf
ms.assetid: 40f4cd91-ba84-426c-b248-6027d1e8d1a4
ms.date: 02/26/2018
keywords: ["WDF_IO_QUEUE_DISPATCH_TYPE enumeration"]
ms.keywords: WDF_IO_QUEUE_DISPATCH_TYPE, WDF_IO_QUEUE_DISPATCH_TYPE enumeration, WdfIoQueueDispatchManual, WdfIoQueueDispatchMaximum, WdfIoQueueDispatchParallel, WdfIoQueueDispatchSequential, _WDF_IO_QUEUE_DISPATCH_TYPE, umdf.wdf_io_queue_dispatch_type, umdfstructs_7f7744f6-7f47-4e8e-a74d-fb0217a59f34.xml, wdf.wdf_io_queue_dispatch_type_umdf, wudfddi_types/WDF_IO_QUEUE_DISPATCH_TYPE, wudfddi_types/WdfIoQueueDispatchManual, wudfddi_types/WdfIoQueueDispatchMaximum, wudfddi_types/WdfIoQueueDispatchParallel, wudfddi_types/WdfIoQueueDispatchSequential
req.header: wudfddi_types.h
req.include-header: Wudfddi.h
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
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
targetos: Windows
req.typenames: WDF_IO_QUEUE_DISPATCH_TYPE
f1_keywords:
 - _WDF_IO_QUEUE_DISPATCH_TYPE
 - wudfddi_types/_WDF_IO_QUEUE_DISPATCH_TYPE
 - WDF_IO_QUEUE_DISPATCH_TYPE
 - wudfddi_types/WDF_IO_QUEUE_DISPATCH_TYPE
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - Wudfddi_types.h
api_name:
 - WDF_IO_QUEUE_DISPATCH_TYPE
---

# _WDF_IO_QUEUE_DISPATCH_TYPE enumeration (wudfddi_types.h)


## -description

<p class="CCE_Message">[<b>Warning:</b> UMDF 2 is the latest version of UMDF and supersedes UMDF 1.  All new UMDF drivers should be written using UMDF 2.  No new features are being added to UMDF 1 and there is limited support for UMDF 1 on newer versions of Windows 10.  Universal Windows drivers must use UMDF 2.  For more info, see <a href="/windows-hardware/drivers/wdf/getting-started-with-umdf-version-2">Getting Started with UMDF</a>.]


The <a href="/windows-hardware/drivers/ddi/wdfio/ne-wdfio-_wdf_io_queue_dispatch_type">WDF_IO_QUEUE_DISPATCH_TYPE</a> enumeration contains values that identify how a driver must receive requests from an I/O queue.

## -enum-fields

### -field WdfIoQueueDispatchSequential

The I/O queue's requests are presented to the driver's I/O queue callback functions one at a time. The framework delivers the next request after the driver calls the <a href="/windows-hardware/drivers/ddi/wudfddi/nf-wudfddi-iwdfiorequest-complete">IWDFIoRequest::Complete</a> method to complete the current request.

### -field WdfIoQueueDispatchParallel

The framework presents requests to the driver's I/O queue callback functions as soon as the requests are available.

### -field WdfIoQueueDispatchManual

The framework places requests into the queue but does not deliver them to the driver. The driver must call the <a href="/windows-hardware/drivers/ddi/wudfddi/nf-wudfddi-iwdfioqueue-retrievenextrequest">IWDFIoQueue::RetrieveNextRequest</a> method to retrieve a request from the queue.

### -field WdfIoQueueDispatchMaximum

Valid enumeration values were exceeded.

## -see-also

<a href="/windows-hardware/drivers/ddi/wudfddi/nf-wudfddi-iwdfioqueue-retrievenextrequest">IWDFIoQueue::RetrieveNextRequest</a>



<a href="/windows-hardware/drivers/ddi/wudfddi/nf-wudfddi-iwdfiorequest-complete">IWDFIoRequest::Complete</a>