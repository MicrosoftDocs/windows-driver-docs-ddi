---
UID: NS:d3dkmthk._D3DKMT_CREATEPAGINGQUEUE
title: _D3DKMT_CREATEPAGINGQUEUE (d3dkmthk.h)
description: D3DKMT_CREATEPAGINGQUEUE is used with D3DKMTCreatePagingQueue to create a device paging queue that can be used to synchronize with video memory management operations for the device, such as making the device resource resident.
old-location: display\d3dkmt_createpagingqueue.htm
ms.assetid: F7C2847F-D095-4A79-ADBB-DA0745E3192A
ms.date: 05/10/2018
ms.keywords: D3DKMT_CREATEPAGINGQUEUE, D3DKMT_CREATEPAGINGQUEUE structure [Display Devices], _D3DKMT_CREATEPAGINGQUEUE, d3dkmthk/D3DKMT_CREATEPAGINGQUEUE, display.d3dkmt_createpagingqueue
ms.topic: struct
f1_keywords:
 - "d3dkmthk/D3DKMT_CREATEPAGINGQUEUE"
req.header: d3dkmthk.h
req.include-header: D3dkmthk.h
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
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- d3dkmthk.h
api_name:
- D3DKMT_CREATEPAGINGQUEUE
product:
- Windows
targetos: Windows
tech.root: display
req.typenames: D3DKMT_CREATEPAGINGQUEUE
---

# _D3DKMT_CREATEPAGINGQUEUE structure


## -description


<b>D3DKMT_CREATEPAGINGQUEUE</b> is used with <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3dkmthk/nf-d3dkmthk-d3dkmtcreatepagingqueue">D3DKMTCreatePagingQueue</a> to create a device paging queue that can be used to synchronize with video memory management operations for the device, such as making the device resource resident.


## -struct-fields




### -field hDevice

[in] Device to create a new paging queue object for.


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



A device can have multiple paging queues created for it. Paging queues can be destroyed either explicitly by calling <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3dkmthk/nf-d3dkmthk-d3dkmtdestroypagingqueue">D3DKMTDestroyPagingQueue</a>, or by implicitly destroying the device they belong to. After the latter, paging queue handles will become invalid.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3dkmthk/nf-d3dkmthk-d3dkmtcreatepagingqueue">D3DKMTCreatePagingQueue</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3dkmthk/nf-d3dkmthk-d3dkmtdestroypagingqueue">D3DKMTDestroyPagingQueue</a>
 

 

