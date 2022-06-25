---
UID: NF:storport.StorPortQueueWorkItem
title: StorPortQueueWorkItem function (storport.h)
description: Schedules a Storport work item to execute within the context of a system worker thread.
old-location: storage\storportqueueworkitem.htm
tech.root: storage
ms.date: 06/24/2022
keywords: ["StorPortQueueWorkItem function"]
ms.keywords: StorPortQueueWorkItem, StorPortQueueWorkItem routine [Storage Devices], storage.storportqueueworkitem, storport/StorPortQueueWorkItem
req.header: storport.h
req.include-header: Storport.h
req.target-type: Universal
req.target-min-winverclnt: Available in Windows 8 and later versions of Windows.
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
req.irql: <= DISPATCH_LEVEL
targetos: Windows
req.typenames: 
f1_keywords:
 - StorPortQueueWorkItem
 - storport/StorPortQueueWorkItem
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - storport.h
api_name:
 - StorPortQueueWorkItem
---

# StorPortQueueWorkItem function

## -description

**StorPortQueueWorkItem** queues a Storport work item to execute within the context of a system (kernel) worker thread.

## -parameters

### -param HwDeviceExtension [in]

A pointer to the hardware device extension for the host bus adapter (HBA).

### -param WorkItemCallback [in]

A pointer to a work item callback routine supplied by the miniport. This routine is called in context of the system thread to process the scheduled work item that **Worker** points to.

### -param Worker [in]

A pointer to an opaque buffer for the allocated and initialized work item returned by [**StorPortInitializeWorker**](nf-storport-storportinitializeworker.md).

### -param Context [in, optional]

Optional context for the **Worker** that is processed by the callback routine in **WorkItemCallback**.

## -returns

**StorPortQueueWorkItem** routine returns one of these status codes:

| Return code | Description |
| ----------- | ----------- |
| STOR_STATUS_BUSY | The work item is already queued for processing. |
| STOR_STATUS_INVALID_DEVICE_STATE | The work item cannot be queued as the device is in process of removal. |
| STOR_STATUS_INVALID_IRQL | The current IRQL is greater than DISPATCH_LEVEL. |
| STOR_STATUS_INVALID_PARAMETER | **HwDeviceExtension**, **Worker**, or **WorkItemCallback** is NULL. |
| STOR_STATUS_SUCCESS | The work item was successfully queued. |

## -see-also

[**HwStorWorkItem**](nc-storport-hw_workitem.md)

[**StorPortFreeWorker**](nf-storport-storportfreeworker.md)

[**StorPortInitializeWorker**](nf-storport-storportinitializeworker.md)
