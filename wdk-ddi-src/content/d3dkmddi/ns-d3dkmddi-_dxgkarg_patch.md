---
UID: NS:d3dkmddi._DXGKARG_PATCH
title: "_DXGKARG_PATCH"
author: windows-driver-content
description: The DXGKARG_PATCH structure describes a direct memory access (DMA) buffer that requires patching (that is, requires the assignment of physical addresses).
old-location: display\dxgkarg_patch.htm
old-project: display
ms.assetid: 37ca2208-253c-417e-a44c-fd1303d5f3dc
ms.author: windowsdriverdev
ms.date: 2/24/2018
ms.keywords: ",  , ,, A, C, D, DXGKARG_PATCH, DXGKARG_PATCH structure [Display Devices], DmStructs_1fd78713-859f-4584-a696-e89976b58ab7.xml, G, H, K, P, R, T, X, _, _DXGKARG_PATCH, d3dkmddi/DXGKARG_PATCH, display.dxgkarg_patch"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: d3dkmddi.h
req.include-header: D3dkmddi.h
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
req.irql: PASSIVE_LEVEL
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	d3dkmddi.h
apiname:
-	DXGKARG_PATCH
product: Windows
targetos: Windows
req.typenames: DXGKARG_PATCH
---

# _DXGKARG_PATCH structure


## -description


The DXGKARG_PATCH structure describes a direct memory access (DMA) buffer that requires patching (that is, requires the assignment of physical addresses).


## -syntax


````
typedef struct _DXGKARG_PATCH {
  union {
    HANDLE hDevice;
    HANDLE hContext;
  };
  UINT                           DmaBufferSegmentId;
  PHYSICAL_ADDRESS               DmaBufferPhysicalAddress;
  VOID                           *pDmaBuffer;
  UINT                           DmaBufferSize;
  UINT                           DmaBufferSubmissionStartOffset;
  UINT                           DmaBufferSubmissionEndOffset;
  VOID                           *pDmaBufferPrivateData;
  UINT                           DmaBufferPrivateDataSize;
  UINT                           DmaBufferPrivateDataSubmissionStartOffset;
  UINT                           DmaBufferPrivateDataSubmissionEndOffset;
  const DXGK_ALLOCATIONLIST      *pAllocationList;
  UINT                           AllocationListSize;
  const D3DDDI_PATCHLOCATIONLIST *pPatchLocationList;
  UINT                           PatchLocationListSize;
  UINT                           PatchLocationListSubmissionStart;
  UINT                           PatchLocationListSubmissionLength;
  UINT                           SubmissionFenceId;
  DXGK_PATCHFLAGS                Flags;
  UINT                           EngineOrdinal;
} DXGKARG_PATCH;
````


## -struct-fields




### -field DmaBufferSegmentId

[in] The identifier of the memory segment that the DMA buffer was paged in. 

The identifier can be zero if the driver indicated not to map the DMA buffer into the segment by setting the <b>DmaBufferSegmentSet</b> member of the <a href="..\d3dkmddi\ns-d3dkmddi-_dxgk_contextinfo.md">DXGK_CONTEXTINFO</a> structure to 0 in a call to the driver's <a href="..\d3dkmddi\nc-d3dkmddi-dxgkddi_createcontext.md">DxgkDdiCreateContext</a> function. If <b>DmaBufferSegmentId</b> is zero, the DMA buffer was allocated as a contiguous block of system memory. 


### -field DmaBufferPhysicalAddress

[in] A PHYSICAL_ADDRESS data type (which is defined as LARGE_INTEGER) that indicates the physical address where the DMA buffer was paged in. 

If <b>DmaBufferSegmentId</b> is zero, <b>DmaBufferPhysicalAddress</b> is the physical address in system memory where the DMA buffer is located. 

If <b>DmaBufferSegmentId</b> is nonzero, <b>DmaBufferPhysicalAddress</b> is the segment physical address for the DMA buffer (that is, DXGK_SEGMENTDESCRIPTOR.BaseAddress + DmaBuffer.SegmentOffset). 

Note that <b>DmaBufferPhysicalAddress</b> always refers to the beginning of the DMA buffer even though the driver might be required to patch or submit a section of the DMA buffer that does not include the beginning of the DMA buffer (that is, if the <b>DmaBufferSubmissionStartOffset</b> member is nonzero). 


### -field pDmaBuffer

[in] A pointer to the start of the DMA buffer (that is, the virtual address of the beginning of the DMA buffer).


### -field DmaBufferSize

[in] The size, in bytes, of the DMA buffer that <b>pDmaBuffer</b> points to.

Note that <b>DmaBufferSize</b> represents the entire length of the DMA buffer; however, the request to patch or submit might refer to only a portion of the DMA buffer. 


### -field DmaBufferSubmissionStartOffset

[in] The offset, in bytes, from the beginning of the DMA buffer that <b>pDmaBuffer</b> specifies to the start of the portion of the DMA buffer that requires patching or submitting. The offset that is received at patch time matches the offset that is received at submission time. 


### -field DmaBufferSubmissionEndOffset

[in] The offset, in bytes, from the beginning of the DMA buffer that <b>pDmaBuffer</b> specifies to the end of the portion of the DMA buffer that requires patching or submitting. The offset that is received at patch time matches the offset that is received at submission time. 


### -field pDmaBufferPrivateData

[in] A pointer to the driver-resident private data that is associated with the DMA buffer that <b>pDmaBuffer</b> points to. 

For paging operations, a single paging buffer is used for multiple independent submissions. In that scenario, the driver can indicate—by returning the appropriate private driver data pointer in a call to its <a href="..\d3dkmddi\nc-d3dkmddi-dxgkddi_buildpagingbuffer.md">DxgkDdiBuildPagingBuffer</a> function—to have either a single driver private data range for all submissions or one for each submission. 


### -field DmaBufferPrivateDataSize

[in] The size, in bytes, of the private driver data at <b>pDmaBufferPrivateData</b>.

Note that <b>DmaBufferPrivateDataSize</b> represents the entire length of the private driver data buffer; however, the portion that is associated with the current submission might be smaller. 


### -field DmaBufferPrivateDataSubmissionStartOffset

[in] The offset, in bytes, from the beginning of the DMA buffer private data that <b>pDmaBufferPrivateData</b> specifies to the start of the portion of the private data that is associated with the current submission. <b>DmaBufferPrivateDataSubmissionStartOffset</b> is always zero for a nonpaging request. 


### -field DmaBufferPrivateDataSubmissionEndOffset

[in] The offset, in bytes, from the beginning of the DMA buffer private data that <b>pDmaBufferPrivateData</b> specifies to the end of the portion of the private data that is associated with the current submission. 


### -field pAllocationList

[in] A pointer to an array of <a href="..\d3dkmddi\ns-d3dkmddi-_dxgk_allocationlist.md">DXGK_ALLOCATIONLIST</a> structures for the list of allocations that is associated with the DMA buffer that <b>pDmaBuffer</b> points to. 

For paging operations, <b>pAllocationList</b> is <b>NULL</b> because paging buffers are not associated with allocation lists. 


### -field AllocationListSize

[in] The number of elements in the array that <b>pAllocationList</b> specifies.

Note that <b>AllocationListSize</b> represents the total size of the allocation list; however, the portion of the allocation list that is associated with the current submission might be smaller. 

Note that for paging operations <b>AllocationListSize</b> is zero because paging buffers are not associated with allocation lists. 


### -field pPatchLocationList

[in] A pointer to an array of <a href="..\d3dukmdt\ns-d3dukmdt-_d3dddi_patchlocationlist.md">D3DDDI_PATCHLOCATIONLIST</a> structures for the list of patch locations that is associated with the DMA buffer that <b>pDmaBuffer</b> points to.

Note that the array can begin with an element that is before the range that is used to patch the DMA buffer.

For paging operations, <b>pPatchLocationList</b> is <b>NULL</b> because paging buffers are not associated with patch-location lists.


### -field PatchLocationListSize

[in] The number of elements in the array that <b>pPatchLocationList</b> specifies.

Note that <b>PatchLocationListSize</b> represents the total size of the patch-location list; however, the range that the driver must process is typically smaller. 

For paging operations, <b>PatchLocationListSize</b> is zero because paging buffers are not associated with patch-location lists.


### -field PatchLocationListSubmissionStart

[in] The index of the first element in the patch-location list that <b>pPatchLocationList</b> specifies that must be processed. 

For paging operations, <b>PatchLocationListSubmissionStart</b> is zero.


### -field PatchLocationListSubmissionLength

[in] The number of elements in the patch-location list that <b>pPatchLocationList</b> specifies that must be processed.

For paging operations, <b>PatchLocationListSubmissionLength</b> is zero.


### -field SubmissionFenceId

[in] A unique identifier that the driver can write into the fence command at the end of the DMA buffer. For more information about this type of identifier, see <a href="https://msdn.microsoft.com/0ec8a4eb-c441-47ae-b5de-d86e6065ffd4">Supplying Fence Identifiers</a>.


### -field Flags

[in] A <a href="..\d3dkmddi\ns-d3dkmddi-_dxgk_patchflags.md">DXGK_PATCHFLAGS</a> structure that identifies information about the DMA buffer that requires patching.


### -field EngineOrdinal

[in] Reserved for future use.


#### - hDevice

[in] If a driver is not multiple-engine aware (that is, the driver does not support context creation), a handle to the display device (graphics context) that the submission request originated from. A device handle is supplied to the driver's <a href="..\d3dkmddi\nc-d3dkmddi-dxgkddi_patch.md">DxgkDdiPatch</a> function in the union that DXGKARG_PATCH contains.

For some paging operations, <b>hDevice</b> is <b>NULL</b> (for example, paging operations that evict the content of the entire frame buffer during power management). Paging operations are indicated by the <b>Paging</b> bit-field flag in the <b>Flags</b> member. 


#### - hContext

[in] If the driver is multiple-engine aware (that is, the driver supports context creation), a handle to the device context that the submission request originated from. A context handle is supplied to the driver's <a href="..\d3dkmddi\nc-d3dkmddi-dxgkddi_patch.md">DxgkDdiPatch</a> function in the union that DXGKARG_PATCH contains. 

For some paging operations, <b>hContext</b> is <b>NULL</b> (for example, paging operations that evict the content of the entire frame buffer during power management). Paging operations are indicated by the <b>Paging</b> bit-field flag in the <b>Flags</b> member.


## -remarks



The display miniport driver returns an array in the <b>pAllocationList</b> member of a <a href="..\d3dkmddi\ns-d3dkmddi-_dxgkarg_present.md">DXGKARG_PRESENT</a> or <a href="..\d3dkmddi\ns-d3dkmddi-_dxgkarg_render.md">DXGKARG_RENDER</a> structure from its <a href="..\d3dkmddi\nc-d3dkmddi-dxgkddi_present.md">DxgkDdiPresent</a> or <a href="..\d3dkmddi\nc-d3dkmddi-dxgkddi_render.md">DxgkDdiRender</a> function after it translates the command buffer to a direct memory access (DMA) buffer. The video memory manager assigns physical addresses to the <b>PhysicalAddress</b> members of the <a href="..\d3dkmddi\ns-d3dkmddi-_dxgk_allocationlist.md">DXGK_ALLOCATIONLIST</a> structures in the array and passes this array to the driver's <a href="..\d3dkmddi\nc-d3dkmddi-dxgkddi_patch.md">DxgkDdiPatch</a> function. <b>DxgkDdiPatch</b> patches places in the DMA buffer with these physical addresses.




## -see-also

<a href="..\d3dkmddi\ns-d3dkmddi-_dxgkarg_present.md">DXGKARG_PRESENT</a>



<a href="..\d3dkmddi\ns-d3dkmddi-_dxgk_contextinfo.md">DXGK_CONTEXTINFO</a>



<a href="..\d3dkmddi\nc-d3dkmddi-dxgkddi_patch.md">DxgkDdiPatch</a>



<a href="..\d3dkmddi\ns-d3dkmddi-_dxgk_patchflags.md">DXGK_PATCHFLAGS</a>



<a href="..\d3dkmddi\nc-d3dkmddi-dxgkddi_present.md">DxgkDdiPresent</a>



<a href="..\d3dkmddi\nc-d3dkmddi-dxgkddi_createcontext.md">DxgkDdiCreateContext</a>



<a href="..\d3dkmddi\ns-d3dkmddi-_dxgk_allocationlist.md">DXGK_ALLOCATIONLIST</a>



<a href="..\d3dkmddi\nc-d3dkmddi-dxgkddi_buildpagingbuffer.md">DxgkDdiBuildPagingBuffer</a>



<a href="..\d3dkmddi\ns-d3dkmddi-_dxgkarg_render.md">DXGKARG_RENDER</a>



<a href="..\d3dukmdt\ns-d3dukmdt-_d3dddi_patchlocationlist.md">D3DDDI_PATCHLOCATIONLIST</a>



<a href="..\d3dkmddi\nc-d3dkmddi-dxgkddi_render.md">DxgkDdiRender</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20DXGKARG_PATCH structure%20 RELEASE:%20(2/24/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

