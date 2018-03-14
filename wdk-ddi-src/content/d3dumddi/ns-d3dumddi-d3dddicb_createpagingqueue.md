---
UID: NS:d3dumddi.D3DDDICB_CREATEPAGINGQUEUE
title: D3DDDICB_CREATEPAGINGQUEUE
author: windows-driver-content
description: D3DDDICB_CREATEPAGINGQUEUE is used with pfnCreatePagingQueueCb to create a device paging queue that can be used to synchronize with video memory management operations for the device, such as making the device resource resident.
old-location: display\d3dddicb_createpagingqueue.htm
old-project: display
ms.assetid: 9E36B02F-2292-416C-AA09-1968EECE5A3D
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: D3DDDICB_CREATEPAGINGQUEUE, D3DDDICB_CREATEPAGINGQUEUE structure [Display Devices], d3dumddi/D3DDDICB_CREATEPAGINGQUEUE, display.d3dddicb_createpagingqueue
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: d3dumddi.h
req.include-header: D3dumddi.h
req.target-type: Windows
req.target-min-winverclnt: Windows 10
req.target-min-winversvr: Windows Server 2016
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	d3dumddi.h
api_name:
-	D3DDDICB_CREATEPAGINGQUEUE
product: Windows
targetos: Windows
req.typenames: D3DDDICB_CREATEPAGINGQUEUE
---

# D3DDDICB_CREATEPAGINGQUEUE structure


## -description


<b>D3DDDICB_CREATEPAGINGQUEUE</b> is used with <a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_createpagingqueuecb.md">pfnCreatePagingQueueCb</a> to create a device paging queue that can be used to synchronize with video memory management operations for the device, such as making the device resource resident.


## -syntax


````
typedef struct D3DDDICB_CREATEPAGINGQUEUE {
  D3DDDI_PAGINGQUEUE_PRIORITY Priority;
  D3DKMT_HANDLE               hPagingQueue;
  D3DKMT_HANDLE               hSyncObject;
  VOID                        *FenceValueCPUVirtualAddress;
  UINT                        PhysicalAdapterIndex;
} D3DDDICB_CREATEPAGINGQUEUE;
````


## -struct-fields




### -field Priority

[in] Scheduling priority relative to other paging queues on this device. Paging queues with higher priority values will be processed ahead of paging queues with lower priority values.


### -field hPagingQueue

[out] A paging queue handle that will be used to synchronize paging operations.


### -field hSyncObject

[out] Handle to the monitored fence object used to synchronize paging operations for this paging queue. Destroying the paging queue (either implicitly or explicitly) will automatically destroy this sync object.


### -field FenceValueCPUVirtualAddress

[out] A read-only mapping of the paging fence object value for the CPU. This is a user mode address readable from the process that created the monitored fence object.


### -field PhysicalAdapterIndex

[in] Physical adapter index (engine ordinal) for the queue.


## -remarks



A device can have multiple paging queues created for it. Paging queues can be destroyed either explicitly by calling <a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_destroypagingqueuecb.md">pfnDestroyPagingQueueCb</a>, or by implicitly destroying the device they belong to. After the latter, paging queue handles will become invalid.




## -see-also

<a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_destroypagingqueuecb.md">pfnDestroyPagingQueueCb</a>



<a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_createpagingqueuecb.md">pfnCreatePagingQueueCb</a>



 

 


