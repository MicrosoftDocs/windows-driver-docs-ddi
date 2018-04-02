---
UID: NS:d3dumddi._D3DDDI_DEVICECALLBACKS
title: "_D3DDDI_DEVICECALLBACKS"
author: windows-driver-content
description: The D3DDDI_DEVICECALLBACKS structure contains Microsoft Direct3D runtime callback functions that the user-mode display driver can use.
old-location: display\d3dddi_devicecallbacks.htm
old-project: display
ms.assetid: 29810132-5f53-4ba6-8302-6de315ecd04a
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: D3DDDI_DEVICECALLBACKS, D3DDDI_DEVICECALLBACKS structure [Display Devices], D3D_other_Structs_a835da78-4f70-4fc5-9f0f-43cef61bd304.xml, _D3DDDI_DEVICECALLBACKS, d3dumddi/D3DDDI_DEVICECALLBACKS, display.d3dddi_devicecallbacks
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: d3dumddi.h
req.include-header: D3dumddi.h
req.target-type: Windows
req.target-min-winverclnt: Available in Windows Vista and later versions of the Windows operating systems.
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	D3dumddi.h
api_name:
-	D3DDDI_DEVICECALLBACKS
product:
- Windows
targetos: Windows
req.typenames: D3DDDI_DEVICECALLBACKS
---

# _D3DDDI_DEVICECALLBACKS structure


## -description


The D3DDDI_DEVICECALLBACKS structure contains Microsoft Direct3D runtime callback functions that the user-mode display driver can use.


## -struct-fields




### -field pfnAllocateCb

A pointer to the <a href="https://msdn.microsoft.com/a61e6c6a-3992-429c-ad8c-5f1a61dc7b8b">pfnAllocateCb</a> function, which the user-mode display driver uses to request that the Direct3D runtime create a memory allocation for use by the driver.


### -field pfnDeallocateCb

A pointer to the <a href="https://msdn.microsoft.com/2ffa0367-0451-45d2-be05-e450c45be116">pfnDeallocateCb</a> function, which the user-mode display driver uses to request that the Direct3D runtime free memory that was previously allocated.


### -field pfnSetPriorityCb

A pointer to the <a href="https://msdn.microsoft.com/1812cb0f-9232-4813-9c7b-74c9fa4d03cf">pfnSetPriorityCb</a> function, which the user-mode display driver uses to set the priority of a resource or list of allocations.


### -field pfnQueryResidencyCb

A pointer to the <a href="https://msdn.microsoft.com/707ba050-e70c-49f8-aac0-0bcc8fe9bf8b">pfnQueryResidencyCb</a> function, which the user-mode display driver uses to query the residency status of a resource or list of allocations.


### -field pfnSetDisplayModeCb

A pointer to the <a href="https://msdn.microsoft.com/a1f58757-809d-4351-8b1a-fd4420981c24">pfnSetDisplayModeCb</a> function, which the user-mode display driver uses to set an allocation for displaying.


### -field pfnPresentCb

A pointer to the <a href="https://msdn.microsoft.com/460b9be5-5817-4225-9089-f86ad64f4554">pfnPresentCb</a> function, which the user-mode display driver uses to submit a present command to the display miniport driver.


### -field pfnRenderCb

A pointer to the <a href="https://msdn.microsoft.com/f242162e-6237-469c-b178-5a51dcf69e32">pfnRenderCb</a> function, which the user-mode display driver uses to submit a command buffer to the display miniport driver.


### -field pfnLockCb

A pointer to the <a href="https://msdn.microsoft.com/69022797-432a-410b-8cbf-e1ef7111e7ea">pfnLockCb</a> function, which the user-mode display driver uses to request a lock from the display miniport driver. This lock cannot be handled completely by the user-mode display driver.


### -field pfnUnlockCb

A pointer to the <a href="https://msdn.microsoft.com/6684f350-da27-478d-ab7b-36e395f7df8d">pfnUnlockCb</a> function, which the user-mode display driver uses to call the display miniport driver for an unlock. This unlock cannot be handled completely by the user-mode display driver. 


### -field pfnEscapeCb

A pointer to the <a href="https://msdn.microsoft.com/66c0347f-2cf3-42fc-8641-47c731e958c9">pfnEscapeCb</a> function, which the user-mode display driver uses to share information with the display miniport driver. 


### -field pfnCreateOverlayCb

A pointer to the <a href="https://msdn.microsoft.com/fbd5b3af-0963-4e41-8be3-41e3e1ecf8bc">pfnCreateOverlayCb</a> function, which the user-mode display driver uses to create and display a kernel-mode overlay object. 


### -field pfnUpdateOverlayCb

A pointer to the <a href="https://msdn.microsoft.com/17f89cea-350c-43f6-a60d-32fc2d299dd7">pfnUpdateOverlayCb</a> function, which the user-mode display driver uses to modify a kernel-mode overlay object. 


### -field pfnFlipOverlayCb

A pointer to the <a href="https://msdn.microsoft.com/91e4876a-82c0-4e74-84c8-4b7a6abe0756">pfnFlipOverlayCb</a> function, which the user-mode display driver uses to change the allocation that the overlay displays. 


### -field pfnDestroyOverlayCb

A pointer to the <a href="https://msdn.microsoft.com/9fc83bad-c183-4cba-9514-bfe1c676cba5">pfnDestroyOverlayCb</a> function, which the user-mode display driver uses to destroy a kernel-mode overlay object and stop the overlay from being displayed. 


### -field pfnCreateContextCb

A pointer to the <a href="https://msdn.microsoft.com/f3f5d6bc-3bc6-4214-830a-cffff01069cc">pfnCreateContextCb</a> function, which the user-mode display driver uses to create a context to submit requests to. 


### -field pfnDestroyContextCb

A pointer to the <a href="https://msdn.microsoft.com/6b65d75b-544b-4153-b821-d59d6f85673d">pfnDestroyContextCb</a> function, which the user-mode display driver uses to destroy a context that <a href="https://msdn.microsoft.com/f3f5d6bc-3bc6-4214-830a-cffff01069cc">pfnCreateContextCb</a> created. 


### -field pfnCreateSynchronizationObjectCb

A pointer to the <a href="https://msdn.microsoft.com/1b87d3cc-685a-4768-b4fd-dbe0a0cbec37">pfnCreateSynchronizationObjectCb</a> function, which the user-mode display driver uses to create a synchronization object. 


### -field pfnDestroySynchronizationObjectCb

A pointer to the <a href="https://msdn.microsoft.com/7ba549a2-f165-4b5e-8cf4-ab707222532c">pfnDestroySynchronizationObjectCb</a> function, which the user-mode display driver uses to destroy a synchronization object that <a href="https://msdn.microsoft.com/1b87d3cc-685a-4768-b4fd-dbe0a0cbec37">pfnCreateSynchronizationObjectCb</a> created. 


### -field pfnWaitForSynchronizationObjectCb

A pointer to the <a href="https://msdn.microsoft.com/d33ca665-897d-4e99-b9a6-b794127fecfd">pfnWaitForSynchronizationObjectCb</a> function, which the user-mode display driver uses to wait for synchronization events to occur and then uses to return. 


### -field pfnSignalSynchronizationObjectCb

A pointer to the <a href="https://msdn.microsoft.com/12ffa230-2c26-4cd3-ae83-f753a0b6ba38">pfnSignalSynchronizationObjectCb</a> function, which the user-mode display driver uses to signal that synchronization events are no longer owned by a context. 


### -field pfnSetAsyncCallbacksCb

A pointer to the <a href="https://msdn.microsoft.com/7f046e5a-e8a2-4e39-ae31-d37afc03f21f">pfnSetAsyncCallbacksCb</a> function that the user-mode display driver uses to notify the Direct3D runtime whether the runtime will start or stop receiving calls to the runtime's callback functions from a worker thread.

Only DirectX 9 and Direct 9L versions of the runtime support the <a href="https://msdn.microsoft.com/7f046e5a-e8a2-4e39-ae31-d37afc03f21f">pfnSetAsyncCallbacksCb</a> function. DirectX 10 and later versions of the runtime set the <b>pfnSetAsyncCallbacksCb</b> member to <b>NULL</b> when the runtime calls the user-mode display driver's <a href="https://msdn.microsoft.com/c69eedb1-c975-412c-aa9f-cf64a702f937">CreateDevice(D3D10)</a> function to create a rendering device. 


### -field pfnSetDisplayPrivateDriverFormatCb

A pointer to the <a href="https://msdn.microsoft.com/499e6de7-67cc-4834-bcec-4f3907b180f7">pfnSetDisplayPrivateDriverFormatCb</a> function that the user-mode display driver uses to change the format of the shared primary surface. 


### -field pfnOfferAllocationsCb

A pointer to the <a href="https://msdn.microsoft.com/library/windows/hardware/hh451693">pfnOfferAllocationsCb</a> function, which a WDDM 1.2 and later user-mode display driver   calls to offer  video memory allocations for reuse.

Supported starting with Windows 8.


### -field pfnReclaimAllocationsCb

A pointer to the <a href="https://msdn.microsoft.com/library/windows/hardware/hh451695">pfnReclaimAllocationsCb</a> function, which a WDDM 1.2 and later user-mode display driver   calls to reclaim access to video memory allocations that were previously offered  for reuse.

Supported starting with Windows 8.


### -field pfnCreateSynchronizationObject2Cb

A pointer to the <a href="https://msdn.microsoft.com/9B0F058C-B71F-4A4F-A053-F9381A5FD3A8">pfnCreateSynchronizationObject2Cb</a> function, which a WDDM 1.2 and later user-mode display driver uses to create a GPU synchronization object.

Supported starting with Windows 8.


### -field pfnWaitForSynchronizationObject2Cb

A pointer to the <a href="https://msdn.microsoft.com/4542C49F-C26C-45BE-B961-C5F65BDA78CF">pfnWaitForSynchronizationObject2Cb</a> function, which a WDDM 1.2 and later user-mode display driver uses to wait for GPU synchronization events to occur and then uses to return.

Supported starting with Windows 8.


### -field pfnSignalSynchronizationObject2Cb

A pointer to the <a href="https://msdn.microsoft.com/01B5E793-D075-42B5-9ADF-D033249AEE9F">pfnSignalSynchronizationObject2Cb</a> function, which a WDDM 1.2 and later user-mode display driver uses to signal that GPU synchronization events are no longer owned by a context.

Supported starting with Windows 8.


### -field pfnPresentMultiPlaneOverlayCb

A pointer to the <a href="https://msdn.microsoft.com/library/windows/hardware/hh780323">pfnPresentMultiPlaneOverlayCb (D3D)</a> function, which a WDDM 1.3 and later user-mode display driver uses to copy content from a source multiplane overlay allocation to a destination allocation.

Supported starting with Windows 8.1.


### -field pfnLogUMDMarkerCb

A pointer to the <a href="https://msdn.microsoft.com/BD544686-20D3-4577-9950-9C3B6853C4BD">pfnLogUMDMarkerCb</a> function, which a WDDM 1.3 and later user-mode display driver calls to log a custom Event Tracing for Windows (ETW) marker event.

Supported starting with Windows 8.1.


### -field pfnMakeResidentCb

A pointer to the <a href="https://msdn.microsoft.com/8D65C3F7-3D07-4341-A989-A1438F821802">pfnMakeResidentCb</a> function.


### -field pfnEvictCb

A pointer to the <a href="https://msdn.microsoft.com/5E66A522-BC1C-4E7C-8732-87D40F99BBDA">pfnEvictCb</a> function.


### -field pfnWaitForSynchronizationObjectFromCpuCb

A pointer to the <a href="https://msdn.microsoft.com/304A5BCE-19E6-4F92-B840-FD3BE1CFB856">pfnWaitForSynchronizationObjectFromCpuCb</a> function.


### -field pfnSignalSynchronizationObjectFromCpuCb

A pointer to the <a href="https://msdn.microsoft.com/E6FD5215-09CE-4DC8-B5AB-F65E68E2A884">pfnSignalSynchronizationObjectFromCpuCb</a> function.


### -field pfnWaitForSynchronizationObjectFromGpuCb

A pointer to the <a href="https://msdn.microsoft.com/49023D25-D57E-418F-AD10-133377B90493">pfnWaitForSynchronizationObjectFromGpuCb</a> function.


### -field pfnSignalSynchronizationObjectFromGpuCb

A pointer to the <a href="https://msdn.microsoft.com/46F23D7A-5C7A-4BCC-A575-5D47F590B07C">pfnSignalSynchronizationObjectFromGpuCb</a> function.


### -field pfnCreatePagingQueueCb

A pointer to the <a href="https://msdn.microsoft.com/99E4CFCF-7A0A-43A9-9E23-B7A9F9375690">pfnCreatePagingQueueCb</a> function.


### -field pfnDestroyPagingQueueCb

A pointer to the <a href="https://msdn.microsoft.com/2C039656-5384-4864-8F29-A336B0ED06C0">pfnDestroyPagingQueueCb</a> function.


### -field pfnLock2Cb

A pointer to the <a href="https://msdn.microsoft.com/C046F34A-4304-4B96-8D7A-7A951016437F">pfnLock2Cb</a> function.


### -field pfnUnlock2Cb

A pointer to the <a href="https://msdn.microsoft.com/642C6A05-DA8C-453A-B1AA-030C59F32DA5">pfnUnlock2Cb</a> function.


### -field pfnInvalidateCacheCb

A pointer to the <a href="https://msdn.microsoft.com/56DF8936-4DD1-4352-9063-72F441FDF343">pfnInvalidateCacheCb</a> function.


### -field pfnReserveGpuVirtualAddressCb

A pointer to the <a href="https://msdn.microsoft.com/CEDE03E1-4B0D-4839-B7D6-0826CC103C5E">pfnReserveGpuVirtualAddressCb</a> function.


### -field pfnMapGpuVirtualAddressCb

A pointer to the <a href="https://msdn.microsoft.com/DA67A98C-BE9C-412D-9382-CAC5B05FEE3B">pfnMapGpuVirtualAddressCb</a> function.


### -field pfnFreeGpuVirtualAddressCb

A pointer to the <a href="https://msdn.microsoft.com/92F2A43C-699B-4580-8A56-472D837A76E2">pfnFreeGpuVirtualAddressCb</a> function.


### -field pfnUpdateGpuVirtualAddressCb

A pointer to the <a href="https://msdn.microsoft.com/99D075A0-4483-47D1-BA24-80C45BFF407A">pfnUpdateGpuVirtualAddressCb</a> function.


### -field pfnCreateContextVirtualCb

A pointer to the <a href="https://msdn.microsoft.com/7787FEDF-E18C-4120-A073-A13933856F57">pfnCreateContextVirtualCb</a> function.


### -field pfnSubmitCommandCb

A pointer to the <a href="https://msdn.microsoft.com/60300845-9050-4D0A-83D1-76A45EA823C1">pfnSubmitCommandCb</a> function.


### -field pfnDeallocate2Cb

A pointer to the <a href="https://msdn.microsoft.com/68C7EC44-D744-4C69-86D9-35B3B089875A">pfnDeallocate2Cb</a> function.


### -field pfnSignalSynchronizationObjectFromGpu2Cb

A pointer to the <a href="https://msdn.microsoft.com/03F9E47D-A3CA-44A1-A136-8236309D3D36">pfnSignalSynchronizationObjectFromGpu2Cb</a> function.


### -field pfnReclaimAllocations2Cb

A pointer to the <a href="https://msdn.microsoft.com/library/windows/hardware/dn903528">pfnReclaimAllocations2Cb</a> function.


### -field pfnGetResourcePresentPrivateDriverDataCb

A pointer to the <a href="https://msdn.microsoft.com/D4F0F272-60DC-4060-9762-3DB49236CE62">pfnGetResourcePresentPrivateDriverDataCb</a> function.


### -field pfnUpdateAllocationPropertyCb

A pointer to the <a href="https://msdn.microsoft.com/49E4189A-2183-4033-BF17-ADFAC1CF1EF2">pfnUpdateAllocationPropertyCb</a> function.


### -field pfnOfferAllocations2Cb

A pointer to the <a href="https://msdn.microsoft.com/4A8123D3-3A7D-4716-BD02-DD6533DB22F6">pfnOfferAllocations2Cb</a> function.


### -field pfnReclaimAllocations3Cb

A pointer to the <a href="https://msdn.microsoft.com/BA0A8BF0-39C2-4641-9952-05512B1B1662">pfnReclaimAllocations3Cb</a> function.


### -field pfnAcquireResourceCb

 


### -field pfnReleaseResourceCb

 


### -field pfnCreateHwContextCb

 


### -field pfnDestroyHwContextCb

 


### -field pfnCreateHwQueueCb

 


### -field pfnDestroyHwQueueCb

 


### -field pfnSubmitCommandToHwQueueCb

 


### -field pfnSubmitWaitForSyncObjectsToHwQueueCb

 


### -field pfnSubmitSignalSyncObjectsToHwQueueCb

 




## -remarks



The following code, from D3dumddi.h, shows the function declarations for the callback functions that the members of <b>D3DDDI_DEVICECALLBACKS</b> point to.

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>typedef _Check_return_ HRESULT (APIENTRY CALLBACK *PFND3DDDI_ALLOCATECB)(
        _In_ HANDLE hDevice, _Inout_ D3DDDICB_ALLOCATE*);
typedef _Check_return_ HRESULT (APIENTRY CALLBACK *PFND3DDDI_DEALLOCATECB)(
        _In_ HANDLE hDevice, _In_ CONST D3DDDICB_DEALLOCATE*);
typedef _Check_return_ HRESULT (APIENTRY CALLBACK *PFND3DDDI_SETPRIORITYCB)(
        _In_ HANDLE hDevice, _In_ D3DDDICB_SETPRIORITY*);
typedef _Check_return_ HRESULT (APIENTRY CALLBACK *PFND3DDDI_QUERYRESIDENCYCB)(
        _In_ HANDLE hDevice, _Inout_ CONST D3DDDICB_QUERYRESIDENCY*);
typedef _Check_return_ HRESULT (APIENTRY CALLBACK *PFND3DDDI_SETDISPLAYMODECB)(
        _In_ HANDLE hDevice, _Inout_ D3DDDICB_SETDISPLAYMODE*);
typedef _Check_return_ HRESULT (APIENTRY CALLBACK *PFND3DDDI_SETDISPLAYPRIVATEDRIVERFORMATCB)(
        _In_ HANDLE hDevice, _In_ CONST D3DDDICB_SETDISPLAYPRIVATEDRIVERFORMAT*);
typedef _Check_return_ HRESULT (APIENTRY CALLBACK *PFND3DDDI_PRESENTCB)(
        _In_ HANDLE hDevice, _In_ CONST D3DDDICB_PRESENT*);
typedef _Check_return_ HRESULT (APIENTRY CALLBACK *PFND3DDDI_RENDERCB)(
        _In_ HANDLE hDevice, _Inout_ D3DDDICB_RENDER*);
typedef _Check_return_ HRESULT (APIENTRY CALLBACK *PFND3DDDI_LOCKCB)(
        _In_ HANDLE hDevice, _Inout_ D3DDDICB_LOCK*);
typedef _Check_return_ HRESULT (APIENTRY CALLBACK *PFND3DDDI_UNLOCKCB)(
        _In_ HANDLE hDevice, _In_ CONST D3DDDICB_UNLOCK*);
typedef _Check_return_ HRESULT (APIENTRY CALLBACK *PFND3DDDI_ESCAPECB)(
        _In_ HANDLE hAdapter, _Inout_ CONST D3DDDICB_ESCAPE*);
typedef _Check_return_ HRESULT (APIENTRY CALLBACK *PFND3DDDI_CREATEOVERLAYCB)(
        _In_ HANDLE hDevice, _Inout_ D3DDDICB_CREATEOVERLAY*);
typedef _Check_return_ HRESULT (APIENTRY CALLBACK *PFND3DDDI_UPDATEOVERLAYCB)(
        _In_ HANDLE hDevice, _In_ CONST D3DDDICB_UPDATEOVERLAY*);
typedef _Check_return_ HRESULT (APIENTRY CALLBACK *PFND3DDDI_FLIPOVERLAYCB)(
        _In_ HANDLE hDevice, _In_ CONST D3DDDICB_FLIPOVERLAY*);
typedef _Check_return_ HRESULT (APIENTRY CALLBACK *PFND3DDDI_DESTROYOVERLAYCB)(
        _In_ HANDLE hDevice, _In_ CONST D3DDDICB_DESTROYOVERLAY*);
typedef _Check_return_ HRESULT (APIENTRY CALLBACK *PFND3DDDI_CREATECONTEXTCB)(
        _In_ HANDLE hDevice, _Inout_ D3DDDICB_CREATECONTEXT*);
typedef _Check_return_ HRESULT (APIENTRY CALLBACK *PFND3DDDI_DESTROYCONTEXTCB)(
        _In_ HANDLE hDevice, _In_ CONST D3DDDICB_DESTROYCONTEXT*);
typedef _Check_return_ HRESULT (APIENTRY CALLBACK *PFND3DDDI_CREATESYNCHRONIZATIONOBJECTCB)(
        _In_ HANDLE hDevice, _Inout_ D3DDDICB_CREATESYNCHRONIZATIONOBJECT*);
typedef _Check_return_ HRESULT (APIENTRY CALLBACK *PFND3DDDI_DESTROYSYNCHRONIZATIONOBJECTCB)(
        _In_ HANDLE hDevice, _In_ CONST D3DDDICB_DESTROYSYNCHRONIZATIONOBJECT*);
typedef _Check_return_ HRESULT (APIENTRY CALLBACK *PFND3DDDI_WAITFORSYNCHRONIZATIONOBJECTCB)(
        _In_ HANDLE hDevice, _In_ CONST D3DDDICB_WAITFORSYNCHRONIZATIONOBJECT*);
typedef _Check_return_ HRESULT (APIENTRY CALLBACK *PFND3DDDI_SIGNALSYNCHRONIZATIONOBJECTCB)(
        _In_ HANDLE hDevice, _In_ CONST D3DDDICB_SIGNALSYNCHRONIZATIONOBJECT*);
typedef _Check_return_ HRESULT (APIENTRY CALLBACK *PFND3DDDI_SETASYNCCALLBACKSCB)(
        _In_ HANDLE hDevice, _In_ BOOL Enable);
#if (D3D_UMD_INTERFACE_VERSION &gt;= D3D_UMD_INTERFACE_VERSION_WIN8)
typedef _Check_return_ HRESULT (APIENTRY CALLBACK *PFND3DDDI_CREATESYNCHRONIZATIONOBJECT2CB)(
        _In_ HANDLE hDevice, _Inout_ D3DDDICB_CREATESYNCHRONIZATIONOBJECT2*);
typedef _Check_return_ HRESULT (APIENTRY CALLBACK *PFND3DDDI_WAITFORSYNCHRONIZATIONOBJECT2CB)(
        _In_ HANDLE hDevice, _In_ CONST D3DDDICB_WAITFORSYNCHRONIZATIONOBJECT2*);
typedef _Check_return_ HRESULT (APIENTRY CALLBACK *PFND3DDDI_SIGNALSYNCHRONIZATIONOBJECT2CB)(
        _In_ HANDLE hDevice, _In_ CONST D3DDDICB_SIGNALSYNCHRONIZATIONOBJECT2*);
typedef _Check_return_ HRESULT (APIENTRY CALLBACK *PFND3DDDI_OFFERALLOCATIONSCB)(
        _In_ HANDLE hDevice, _In_ CONST D3DDDICB_OFFERALLOCATIONS*);
typedef _Check_return_ HRESULT (APIENTRY CALLBACK *PFND3DDDI_RECLAIMALLOCATIONSCB)(
        _In_ HANDLE hDevice, _Inout_ CONST D3DDDICB_RECLAIMALLOCATIONS*);
typedef _Check_return_ HRESULT (APIENTRY CALLBACK *PFND3DDDI_PRESENTMULTIPLANEOVERLAYCB)(
        _In_ HANDLE hDevice, _In_ CONST D3DDDICB_PRESENTMULTIPLANEOVERLAY*);
#endif
#if (D3D_UMD_INTERFACE_VERSION &gt;= D3D_UMD_INTERFACE_VERSION_WDDM1_3)
typedef _Check_return_ HRESULT (APIENTRY CALLBACK *PFND3DDDI_LOGUMDMARKERCB)(
        _In_ HANDLE hDevice, _In_ CONST D3DDDICB_LOGUMDMARKER*);
#endif
</pre>
</td>
</tr>
</table></span></div>



## -see-also




<a href="https://msdn.microsoft.com/ce35bdac-af90-471f-af93-0e665be6c7f6">CreateDevice</a>



<a href="https://msdn.microsoft.com/c69eedb1-c975-412c-aa9f-cf64a702f937">CreateDevice(D3D10)</a>



<a href="https://msdn.microsoft.com/a61e6c6a-3992-429c-ad8c-5f1a61dc7b8b">pfnAllocateCb</a>



<a href="https://msdn.microsoft.com/f3f5d6bc-3bc6-4214-830a-cffff01069cc">pfnCreateContextCb</a>



<a href="https://msdn.microsoft.com/fbd5b3af-0963-4e41-8be3-41e3e1ecf8bc">pfnCreateOverlayCb</a>



<a href="https://msdn.microsoft.com/9B0F058C-B71F-4A4F-A053-F9381A5FD3A8">pfnCreateSynchronizationObject2Cb</a>



<a href="https://msdn.microsoft.com/1b87d3cc-685a-4768-b4fd-dbe0a0cbec37">pfnCreateSynchronizationObjectCb</a>



<a href="https://msdn.microsoft.com/2ffa0367-0451-45d2-be05-e450c45be116">pfnDeallocateCb</a>



<a href="https://msdn.microsoft.com/6b65d75b-544b-4153-b821-d59d6f85673d">pfnDestroyContextCb</a>



<a href="https://msdn.microsoft.com/9fc83bad-c183-4cba-9514-bfe1c676cba5">pfnDestroyOverlayCb</a>



<a href="https://msdn.microsoft.com/7ba549a2-f165-4b5e-8cf4-ab707222532c">pfnDestroySynchronizationObjectCb</a>



<a href="https://msdn.microsoft.com/66c0347f-2cf3-42fc-8641-47c731e958c9">pfnEscapeCb</a>



<a href="https://msdn.microsoft.com/91e4876a-82c0-4e74-84c8-4b7a6abe0756">pfnFlipOverlayCb</a>



<a href="https://msdn.microsoft.com/69022797-432a-410b-8cbf-e1ef7111e7ea">pfnLockCb</a>



<a href="https://msdn.microsoft.com/BD544686-20D3-4577-9950-9C3B6853C4BD">pfnLogUMDMarkerCb</a>



<a href="https://msdn.microsoft.com/4A8123D3-3A7D-4716-BD02-DD6533DB22F6">pfnOfferAllocations2Cb</a>



<a href="https://msdn.microsoft.com/460b9be5-5817-4225-9089-f86ad64f4554">pfnPresentCb</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh780323">pfnPresentMultiPlaneOverlayCb (D3D)</a>



<a href="https://msdn.microsoft.com/707ba050-e70c-49f8-aac0-0bcc8fe9bf8b">pfnQueryResidencyCb</a>



<a href="https://msdn.microsoft.com/BA0A8BF0-39C2-4641-9952-05512B1B1662">pfnReclaimAllocations3Cb</a>



<a href="https://msdn.microsoft.com/f242162e-6237-469c-b178-5a51dcf69e32">pfnRenderCb</a>



<a href="https://msdn.microsoft.com/7f046e5a-e8a2-4e39-ae31-d37afc03f21f">pfnSetAsyncCallbacksCb</a>



<a href="https://msdn.microsoft.com/a1f58757-809d-4351-8b1a-fd4420981c24">pfnSetDisplayModeCb</a>



<a href="https://msdn.microsoft.com/499e6de7-67cc-4834-bcec-4f3907b180f7">pfnSetDisplayPrivateDriverFormatCb</a>



<a href="https://msdn.microsoft.com/1812cb0f-9232-4813-9c7b-74c9fa4d03cf">pfnSetPriorityCb</a>



<a href="https://msdn.microsoft.com/01B5E793-D075-42B5-9ADF-D033249AEE9F">pfnSignalSynchronizationObject2Cb</a>



<a href="https://msdn.microsoft.com/12ffa230-2c26-4cd3-ae83-f753a0b6ba38">pfnSignalSynchronizationObjectCb</a>



<a href="https://msdn.microsoft.com/6684f350-da27-478d-ab7b-36e395f7df8d">pfnUnlockCb</a>



<a href="https://msdn.microsoft.com/17f89cea-350c-43f6-a60d-32fc2d299dd7">pfnUpdateOverlayCb</a>



<a href="https://msdn.microsoft.com/4542C49F-C26C-45BE-B961-C5F65BDA78CF">pfnWaitForSynchronizationObject2Cb</a>



<a href="https://msdn.microsoft.com/d33ca665-897d-4e99-b9a6-b794127fecfd">pfnWaitForSynchronizationObjectCb</a>
 

 

