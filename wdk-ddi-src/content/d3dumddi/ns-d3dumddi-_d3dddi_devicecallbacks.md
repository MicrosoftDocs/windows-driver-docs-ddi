---
UID: NS:d3dumddi._D3DDDI_DEVICECALLBACKS
title: D3DDDI_DEVICECALLBACKS (d3dumddi.h)
description: Learn more about the D3DDDI_DEVICECALLBACKS structure.
tech.root: display
ms.date: 10/12/2023
keywords: ["D3DDDI_DEVICECALLBACKS structure"]
ms.keywords: D3DDDI_DEVICECALLBACKS, D3DDDI_DEVICECALLBACKS structure [Display Devices], D3D_other_Structs_a835da78-4f70-4fc5-9f0f-43cef61bd304.xml, _D3DDDI_DEVICECALLBACKS, d3dumddi/D3DDDI_DEVICECALLBACKS, display.d3dddi_devicecallbacks
req.header: d3dumddi.h
req.include-header: D3dumddi.h
req.target-type: Windows
req.target-min-winverclnt: Windows Vista
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
req.typenames: D3DDDI_DEVICECALLBACKS
f1_keywords:
 - _D3DDDI_DEVICECALLBACKS
 - d3dumddi/_D3DDDI_DEVICECALLBACKS
 - D3DDDI_DEVICECALLBACKS
 - d3dumddi/D3DDDI_DEVICECALLBACKS
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - D3dumddi.h
api_name:
 - _D3DDDI_DEVICECALLBACKS
 - D3DDDI_DEVICECALLBACKS
---

# D3DDDI_DEVICECALLBACKS structure

## -description

The **D3DDDI_DEVICECALLBACKS** structure contains Microsoft Direct3D runtime callback functions that the user-mode display driver can use.

## -struct-fields

### -field pfnAllocateCb

A pointer to the <a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_allocatecb.md">pfnAllocateCb</a> function, which the user-mode display driver uses to request that the Direct3D runtime create a memory allocation for use by the driver.

### -field pfnDeallocateCb

A pointer to the <a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_deallocatecb.md">pfnDeallocateCb</a> function, which the user-mode display driver uses to request that the Direct3D runtime free memory that was previously allocated.

### -field pfnSetPriorityCb

A pointer to the <a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_setprioritycb.md">pfnSetPriorityCb</a> function, which the user-mode display driver uses to set the priority of a resource or list of allocations.

### -field pfnQueryResidencyCb

A pointer to the <a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_queryresidencycb.md">pfnQueryResidencyCb</a> function, which the user-mode display driver uses to query the residency status of a resource or list of allocations.

### -field pfnSetDisplayModeCb

A pointer to the <a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_setdisplaymodecb.md">pfnSetDisplayModeCb</a> function, which the user-mode display driver uses to set an allocation for displaying.

### -field pfnPresentCb

A pointer to the <a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_presentcb.md">pfnPresentCb</a> function, which the user-mode display driver uses to submit a present command to the display miniport driver.

### -field pfnRenderCb

A pointer to the <a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_rendercb.md">pfnRenderCb</a> function, which the user-mode display driver uses to submit a command buffer to the display miniport driver.

### -field pfnLockCb

A pointer to the <a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_lockcb.md">pfnLockCb</a> function, which the user-mode display driver uses to request a lock from the display miniport driver. This lock cannot be handled completely by the user-mode display driver.

### -field pfnUnlockCb

A pointer to the <a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_unlockcb.md">pfnUnlockCb</a> function, which the user-mode display driver uses to call the display miniport driver for an unlock. This unlock cannot be handled completely by the user-mode display driver.

### -field pfnEscapeCb

A pointer to the <a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_escapecb.md">pfnEscapeCb</a> function, which the user-mode display driver uses to share information with the display miniport driver.

### -field pfnCreateOverlayCb

A pointer to the <a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_createoverlaycb.md">pfnCreateOverlayCb</a> function, which the user-mode display driver uses to create and display a kernel-mode overlay object.

### -field pfnUpdateOverlayCb

A pointer to the <a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_updateoverlaycb.md">pfnUpdateOverlayCb</a> function, which the user-mode display driver uses to modify a kernel-mode overlay object.

### -field pfnFlipOverlayCb

A pointer to the <a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_flipoverlaycb.md">pfnFlipOverlayCb</a> function, which the user-mode display driver uses to change the allocation that the overlay displays.

### -field pfnDestroyOverlayCb

A pointer to the <a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_destroyoverlaycb.md">pfnDestroyOverlayCb</a> function, which the user-mode display driver uses to destroy a kernel-mode overlay object and stop the overlay from being displayed.

### -field pfnCreateContextCb

A pointer to the <a href="/previous-versions/ff568895(v=vs.85)">pfnCreateContextCb</a> function, which the user-mode display driver uses to create a context to submit requests to.

### -field pfnDestroyContextCb

A pointer to the <a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_destroycontextcb.md">pfnDestroyContextCb</a> function, which the user-mode display driver uses to destroy a context that <a href="/previous-versions/ff568895(v=vs.85)">pfnCreateContextCb</a> created.

### -field pfnCreateSynchronizationObjectCb

A pointer to the <a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_createsynchronizationobjectcb.md">pfnCreateSynchronizationObjectCb</a> function, which the user-mode display driver uses to create a synchronization object.

### -field pfnDestroySynchronizationObjectCb

A pointer to the <a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_destroysynchronizationobjectcb.md">pfnDestroySynchronizationObjectCb</a> function, which the user-mode display driver uses to destroy a synchronization object that <a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_createsynchronizationobjectcb.md">pfnCreateSynchronizationObjectCb</a> created.

### -field pfnWaitForSynchronizationObjectCb

A pointer to the <a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_waitforsynchronizationobjectcb.md">pfnWaitForSynchronizationObjectCb</a> function, which the user-mode display driver uses to wait for synchronization events to occur and then uses to return.

### -field pfnSignalSynchronizationObjectCb

A pointer to the <a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_signalsynchronizationobjectcb.md">pfnSignalSynchronizationObjectCb</a> function, which the user-mode display driver uses to signal that synchronization events are no longer owned by a context.

### -field pfnSetAsyncCallbacksCb

A pointer to the <a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_setasynccallbackscb.md">pfnSetAsyncCallbacksCb</a> function that the user-mode display driver uses to notify the Direct3D runtime whether the runtime will start or stop receiving calls to the runtime's callback functions from a worker thread.

Only DirectX 9 and Direct 9L versions of the runtime support the <a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_setasynccallbackscb.md">pfnSetAsyncCallbacksCb</a> function. DirectX 10 and later versions of the runtime set the **pfnSetAsyncCallbacksCb** member to NULL when the runtime calls the user-mode display driver's <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi_createdevice.md">CreateDevice(D3D10)</a> function to create a rendering device.

### -field pfnSetDisplayPrivateDriverFormatCb

A pointer to the <a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_setdisplayprivatedriverformatcb.md">pfnSetDisplayPrivateDriverFormatCb</a> function that the user-mode display driver uses to change the format of the shared primary surface.

### -field pfnOfferAllocationsCb

A pointer to the <a href="/windows-hardware/drivers/ddi/d3dumddi/nc-d3dumddi-pfnd3dddi_offerallocationscb">pfnOfferAllocationsCb</a> function, which a WDDM 1.2 and later user-mode display driver   calls to offer  video memory allocations for reuse.

Supported starting with Windows 8.

### -field pfnReclaimAllocationsCb

A pointer to the <a href="/windows-hardware/drivers/ddi/d3dumddi/nc-d3dumddi-pfnd3dddi_reclaimallocationscb">pfnReclaimAllocationsCb</a> function, which a WDDM 1.2 and later user-mode display driver   calls to reclaim access to video memory allocations that were previously offered  for reuse.

Supported starting with Windows 8.

### -field pfnCreateSynchronizationObject2Cb

A pointer to the <a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_createsynchronizationobject2cb.md">pfnCreateSynchronizationObject2Cb</a> function, which a WDDM 1.2 and later user-mode display driver uses to create a GPU synchronization object.

Supported starting with Windows 8.

### -field pfnWaitForSynchronizationObject2Cb

A pointer to the <a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_waitforsynchronizationobject2cb.md">pfnWaitForSynchronizationObject2Cb</a> function, which a WDDM 1.2 and later user-mode display driver uses to wait for GPU synchronization events to occur and then uses to return.

Supported starting with Windows 8.

### -field pfnSignalSynchronizationObject2Cb

A pointer to the <a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_signalsynchronizationobject2cb.md">pfnSignalSynchronizationObject2Cb</a> function, which a WDDM 1.2 and later user-mode display driver uses to signal that GPU synchronization events are no longer owned by a context.

Supported starting with Windows 8.

### -field pfnPresentMultiPlaneOverlayCb

A pointer to the <a href="/windows-hardware/drivers/ddi/d3dumddi/nc-d3dumddi-pfnd3dddi_presentmultiplaneoverlaycb">pfnPresentMultiPlaneOverlayCb (D3D)</a> function, which a WDDM 1.3 and later user-mode display driver uses to copy content from a source multiplane overlay allocation to a destination allocation.

Supported starting with Windows 8.1.

### -field pfnLogUMDMarkerCb

A pointer to the <a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_logumdmarkercb.md">pfnLogUMDMarkerCb</a> function, which a WDDM 1.3 and later user-mode display driver calls to log a custom Event Tracing for Windows (ETW) marker event.

Supported starting with Windows 8.1.

### -field pfnMakeResidentCb

A pointer to the <a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_makeresidentcb.md">pfnMakeResidentCb</a> function.

### -field pfnEvictCb

A pointer to the <a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_evictcb.md">pfnEvictCb</a> function.

### -field pfnWaitForSynchronizationObjectFromCpuCb

A pointer to the <a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_waitforsynchronizationobjectfromcpucb.md">pfnWaitForSynchronizationObjectFromCpuCb</a> function.

### -field pfnSignalSynchronizationObjectFromCpuCb

A pointer to the <a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_signalsynchronizationobjectfromcpucb.md">pfnSignalSynchronizationObjectFromCpuCb</a> function.

### -field pfnWaitForSynchronizationObjectFromGpuCb

A pointer to the <a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_waitforsynchronizationobjectfromgpucb.md">pfnWaitForSynchronizationObjectFromGpuCb</a> function.

### -field pfnSignalSynchronizationObjectFromGpuCb

A pointer to the <a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_signalsynchronizationobjectfromgpucb.md">pfnSignalSynchronizationObjectFromGpuCb</a> function.

### -field pfnCreatePagingQueueCb

A pointer to the <a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_createpagingqueuecb.md">pfnCreatePagingQueueCb</a> function.

### -field pfnDestroyPagingQueueCb

A pointer to the <a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_destroypagingqueuecb.md">pfnDestroyPagingQueueCb</a> function.

### -field pfnLock2Cb

A pointer to the <a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_lock2cb.md">pfnLock2Cb</a> function.

### -field pfnUnlock2Cb

A pointer to the <a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_unlock2cb.md">pfnUnlock2Cb</a> function.

### -field pfnInvalidateCacheCb

A pointer to the <a href="/previous-versions/visualstudio">pfnInvalidateCacheCb</a> function.

### -field pfnReserveGpuVirtualAddressCb

A pointer to the <a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_reservegpuvirtualaddresscb.md">pfnReserveGpuVirtualAddressCb</a> function.

### -field pfnMapGpuVirtualAddressCb

A pointer to the <a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_mapgpuvirtualaddresscb.md">pfnMapGpuVirtualAddressCb</a> function.

### -field pfnFreeGpuVirtualAddressCb

A pointer to the <a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_freegpuvirtualaddresscb.md">pfnFreeGpuVirtualAddressCb</a> function.

### -field pfnUpdateGpuVirtualAddressCb

A pointer to the <a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_updategpuvirtualaddresscb.md">pfnUpdateGpuVirtualAddressCb</a> function.

### -field pfnCreateContextVirtualCb

A pointer to the <a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_createcontextvirtualcb.md">pfnCreateContextVirtualCb</a> function.

### -field pfnSubmitCommandCb

A pointer to the <a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_submitcommandcb.md">pfnSubmitCommandCb</a> function.

### -field pfnDeallocate2Cb

A pointer to the <a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_deallocate2cb.md">pfnDeallocate2Cb</a> function.

### -field pfnSignalSynchronizationObjectFromGpu2Cb

A pointer to the <a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_signalsynchronizationobjectfromgpu2cb.md">pfnSignalSynchronizationObjectFromGpu2Cb</a> function.

### -field pfnReclaimAllocations2Cb

A pointer to the <a href="/windows-hardware/drivers/ddi/d3dumddi/nc-d3dumddi-pfnd3dddi_reclaimallocations2cb">pfnReclaimAllocations2Cb</a> function.

### -field pfnGetResourcePresentPrivateDriverDataCb

A pointer to the <a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_getresourcepresentprivatedriverdatacb.md">pfnGetResourcePresentPrivateDriverDataCb</a> function.

### -field pfnUpdateAllocationPropertyCb

A pointer to the <a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_updateallocationpropertycb.md">pfnUpdateAllocationPropertyCb</a> function.

### -field pfnOfferAllocations2Cb

A pointer to the <a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_offerallocations2cb.md">pfnOfferAllocations2Cb</a> function.

### -field pfnReclaimAllocations3Cb

A pointer to the <a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_reclaimallocations3cb.md">pfnReclaimAllocations3Cb</a> function.

### -field pfnAcquireResourceCb

### -field pfnReleaseResourceCb

### -field pfnCreateHwContextCb

A pointer to a [PFND3DDDI_CREATEHWCONTEXTCB](nc-d3dumddi-pfnd3dddi_createhwcontextcb.md) callback function.

### -field pfnDestroyHwContextCb

A pointer to a [PFND3DDDI_DESTROYHWCONTEXTCB](nc-d3dumddi-pfnd3dddi_destroyhwcontextcb.md) callback function.

### -field pfnCreateHwQueueCb

A pointer to a [PFND3DDDI_CREATEHWQUEUECB](nc-d3dumddi-pfnd3dddi_createhwqueuecb.md) callback function.

### -field pfnDestroyHwQueueCb

A pointer to a [PFND3DDDI_DESTROYHWQUEUECB](nc-d3dumddi-pfnd3dddi_destroyhwqueuecb.md) callback function.

### -field pfnSubmitCommandToHwQueueCb

A pointer to a [PFND3DDDI_SUBMITCOMMANDTOHWQUEUECB](nc-d3dumddi-pfnd3dddi_submitcommandtohwqueuecb.md) callback function.

### -field pfnSubmitWaitForSyncObjectsToHwQueueCb

A pointer to a [PFND3DDDI_SUBMITWAITFORSYNCOBJECTSTOHWQUEUECB](nc-d3dumddi-pfnd3dddi_submitwaitforsyncobjectstohwqueuecb.md) callback function.

### -field pfnSubmitSignalSyncObjectsToHwQueueCb

A pointer to a [PFND3DDDI_SUBMITSIGNALSYNCOBJECTSTOHWQUEUECB](nc-d3dumddi-pfnd3dddi_submitsignalsyncobjectstohwqueuecb.md) callback function.

### -field pfnSubmitPresentBltToHwQueueCb

A pointer to a [PFND3DDDI_SUBMITPRESENTBLTTOHWQUEUECB](nc-d3dumddi-pfnd3dddi_submitpresentblttohwqueuecb.md) callback function.

### -field pfnSubmitPresentToHwQueueCb

Pointer to a [PFND3DDDI_SUBMITPRESENTTOHWQUEUECB](nc-d3dumddi-pfnd3dddi_submitpresenttohwqueuecb.md) callback function.

### -field pfnSubmitHistorySequenceCb

Pointer to a [PFND3DDDI_SUBMITHISTORYSEQUENCECB](nc-d3dumddi-pfnd3dddi_submithistorysequencecb.md) callback function.

## -remarks

Declarations for the callback functions that **D3DDDI_DEVICECALLBACKS** members point to can be found in *d3dumddi.h*.
