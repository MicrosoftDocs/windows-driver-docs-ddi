---
UID: NS:d3dkmddi._DXGKARG_SUBMITCOMMAND
title: "_DXGKARG_SUBMITCOMMAND"
author: windows-driver-content
description: The DXGKARG_SUBMITCOMMAND structure describes the direct memory access (DMA) buffer that a display miniport driver submits to the hardware command execution unit.
old-location: display\dxgkarg_submitcommand.htm
old-project: display
ms.assetid: f0b5c7aa-855e-419a-ac27-c9f4edefd648
ms.author: windowsdriverdev
ms.date: 2/20/2018
ms.keywords: DXGKARG_SUBMITCOMMAND, _DXGKARG_SUBMITCOMMAND, DXGKARG_SUBMITCOMMAND structure [Display Devices], DmStructs_04cbfdbf-3b43-4b70-8964-75eb9f9c4128.xml, d3dkmddi/DXGKARG_SUBMITCOMMAND, display.dxgkarg_submitcommand
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
-	DXGKARG_SUBMITCOMMAND
product: Windows
targetos: Windows
req.typenames: DXGKARG_SUBMITCOMMAND
---

# _DXGKARG_SUBMITCOMMAND structure


## -description


The DXGKARG_SUBMITCOMMAND structure describes the direct memory access (DMA) buffer that a display miniport driver submits to the hardware command execution unit.


## -syntax


````
typedef struct _DXGKARG_SUBMITCOMMAND {
  union {
    HANDLE hDevice;
    HANDLE hContext;
  };
  UINT                           DmaBufferSegmentId;
  PHYSICAL_ADDRESS               DmaBufferPhysicalAddress;
  UINT                           DmaBufferSize;
  UINT                           DmaBufferSubmissionStartOffset;
  UINT                           DmaBufferSubmissionEndOffset;
  VOID                           *pDmaBufferPrivateData;
  UINT                           DmaBufferPrivateDataSize;
  UINT                           DmaBufferPrivateDataSubmissionStartOffset;
  UINT                           DmaBufferPrivateDataSubmissionEndOffset;
  UINT                           SubmissionFenceId;
  D3DDDI_VIDEO_PRESENT_SOURCE_ID VidPnSourceId;
  D3DDDI_FLIPINTERVAL_TYPE       FlipInterval;
  DXGK_SUBMITCOMMANDFLAGS        Flags;
  UINT                           EngineOrdinal;
#if (DXGKDDI_INTERFACE_VERSION >= DXGKDDI_INTERFACE_VERSION_WIN7)
  D3DGPU_VIRTUAL_ADDRESS         DmaBufferVirtualAddress;
#endif 
#if (DXGKDDI_INTERFACE_VERSION >= DXGKDDI_INTERFACE_VERSION_WIN8)
  UINT                           NodeOrdinal;
#endif 
} DXGKARG_SUBMITCOMMAND;
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


### -field DmaBufferSize

[in] The size, in bytes, of the DMA buffer.

Note that <b>DmaBufferSize</b> represents the entire length of the DMA buffer; however, the request to patch or submit might refer to only a portion of the DMA buffer. 


### -field DmaBufferSubmissionStartOffset

[in] The offset, in bytes, from the beginning of the DMA buffer to the start of the portion of the DMA buffer that requires patching or submitting. The offset that is received at patch time matches the offset that is received at submission time. 


### -field DmaBufferSubmissionEndOffset

[in] The offset, in bytes, from the beginning of the DMA buffer to the end of the portion of the DMA buffer that requires patching or submitting. The offset that is received at patch time matches the offset that is received at submission time. 


### -field pDmaBufferPrivateData

[in] A pointer to the driver-resident private data that is associated with the DMA buffer that was filled during the <a href="..\d3dkmddi\nc-d3dkmddi-dxgkddi_render.md">DxgkDdiRender</a>, <a href="..\d3dkmddi\nc-d3dkmddi-dxgkddi_present.md">DxgkDdiPresent</a>, or <a href="..\d3dkmddi\nc-d3dkmddi-dxgkddi_patch.md">DxgkDdiPatch</a> function. 

For paging operations, a single paging buffer is used for multiple independent submissions. In that scenario, the driver can indicate--by returning the appropriate private driver data pointer in a call to its <a href="..\d3dkmddi\nc-d3dkmddi-dxgkddi_buildpagingbuffer.md">DxgkDdiBuildPagingBuffer</a> function--to have either a single driver private data range for all of the submissions or one for each submission. 


### -field DmaBufferPrivateDataSize

[in] The size, in byte,s of the private driver data that <b>pDmaBufferPrivateData</b> points to.

Note that <b>DmaBufferPrivateDataSize</b> represents the entire length of the private driver data buffer; however, the portion that is associated with the current submission might be smaller. 


### -field DmaBufferPrivateDataSubmissionStartOffset

[in] The offset, in bytes, from the beginning of the DMA buffer private data that <b>pDmaBufferPrivateData</b> specifies to the start of the portion of the private data that is associated with the current submission. <b>DmaBufferPrivateDataSubmissionStartOffset</b> is always zero for a nonpaging request. 


### -field DmaBufferPrivateDataSubmissionEndOffset

[in] The offset, in bytes, from the beginning of the DMA buffer private data that <b>pDmaBufferPrivateData</b> specifies to the end of the portion of the private data that is associated with the current submission. 


### -field SubmissionFenceId

[in] A unique identifier that the driver can write into the fence command in the ring buffer, which is the buffer where DMA buffers are queued for the graphics processing unit (GPU) to run. For more information about these types of identifiers, see <a href="https://msdn.microsoft.com/0ec8a4eb-c441-47ae-b5de-d86e6065ffd4">Supplying Fence Identifiers</a>.


### -field VidPnSourceId

[in] The zero-based identification number of the video present source in a path of a video present network (VidPN) topology for a flip operation. This member is valid only when the <b>Flip</b> or <b>FlipWithNoWait</b> bit-field flag is set in the <b>Flags</b> member. 


### -field FlipInterval

[in] A <a href="..\d3dukmdt\ne-d3dukmdt-d3dddi_flipinterval_type.md">D3DDDI_FLIPINTERVAL_TYPE</a>-typed value that indicates the flip interval (that is, if the flip occurs after zero, one, two, three, or four vertical syncs). <b>FlipInterval</b> is valid only if the <b>Flip</b> bit-field flag is set (that is, <b>TRUE</b>) in the <b>Flags</b> member.


### -field Flags

[in] A <a href="..\d3dkmddi\ns-d3dkmddi-_dxgk_submitcommandflags.md">DXGK_SUBMITCOMMANDFLAGS</a> structure that identifies information about the DMA buffer to submit.


### -field EngineOrdinal

[in] Reserved for future use.


### -field DmaBufferVirtualAddress

This member is reserved and should be set to zero.

Supported starting with Windows 7.


### -field NodeOrdinal

The zero-based index of the node that the context is created for. Identifies the node when the context is <b>NULL</b>.

Supported starting with Windows 8.


#### - hDevice

[in] If the driver is not multiple-engine aware (that is, the driver does not support context creation), a handle to the display device (graphics context) that the submission request originated from. A device handle is supplied to the driver's <a href="..\d3dkmddi\nc-d3dkmddi-dxgkddi_submitcommand.md">DxgkDdiSubmitCommand</a> function in the union that DXGKARG_SUBMITCOMMAND contains.

For some paging operations, <b>hDevice</b> is <b>NULL</b> (for example, paging operations that evict the content of the entire frame buffer during power management). Paging operations are indicated by the <b>Paging</b> bit-field flag in the <b>Flags</b> member. 


#### - hContext

[in] If the driver is multiple-engine aware (that is, the driver supports context creation), a handle to the device context that the submission request originated from. A context handle is supplied to the driver's <a href="..\d3dkmddi\nc-d3dkmddi-dxgkddi_submitcommand.md">DxgkDdiSubmitCommand</a> function in the union that DXGKARG_SUBMITCOMMAND contains. 

For some paging operations, <b>hContext</b> is <b>NULL</b> (for example, paging operations that evict the content of the entire frame buffer during power management). Paging operations are indicated by the <b>Paging</b> bit-field flag in the <b>Flags</b> member.


## -remarks



The display miniport driver's <a href="..\d3dkmddi\nc-d3dkmddi-dxgkddi_submitcommand.md">DxgkDdiSubmitCommand</a> function must be aware that multiple processes can access the device object that the <b>hDevice</b> member specifies at the same time.




## -see-also

<a href="..\d3dkmddi\nc-d3dkmddi-dxgkddi_patch.md">DxgkDdiPatch</a>



<a href="..\d3dkmddi\ns-d3dkmddi-_dxgk_submitcommandflags.md">DXGK_SUBMITCOMMANDFLAGS</a>



<a href="..\d3dkmddi\nc-d3dkmddi-dxgkcb_notify_dpc.md">DxgkCbNotifyDpc</a>



<a href="..\d3dkmddi\nc-d3dkmddi-dxgkddi_render.md">DxgkDdiRender</a>



<a href="..\d3dukmdt\ne-d3dukmdt-d3dddi_flipinterval_type.md">D3DDDI_FLIPINTERVAL_TYPE</a>



<a href="..\d3dkmddi\nc-d3dkmddi-dxgkddi_present.md">DxgkDdiPresent</a>



<a href="..\d3dkmddi\ns-d3dkmddi-_dxgk_contextinfo.md">DXGK_CONTEXTINFO</a>



<a href="..\d3dkmddi\nc-d3dkmddi-dxgkcb_notify_interrupt.md">DxgkCbNotifyInterrupt</a>



<a href="..\d3dkmddi\nc-d3dkmddi-dxgkddi_createcontext.md">DxgkDdiCreateContext</a>



<a href="..\d3dkmddi\nc-d3dkmddi-dxgkddi_submitcommand.md">DxgkDdiSubmitCommand</a>



<a href="..\d3dkmddi\nc-d3dkmddi-dxgkddi_buildpagingbuffer.md">DxgkDdiBuildPagingBuffer</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20DXGKARG_SUBMITCOMMAND structure%20 RELEASE:%20(2/20/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

