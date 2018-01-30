---
UID: NS:d3dkmddi._DXGKARG_SUBMITCOMMANDVIRTUAL
title: "_DXGKARG_SUBMITCOMMANDVIRTUAL"
author: windows-driver-content
description: DXGKARG_SUBMITCOMMANDVIRTUAL is used to submit a direct memory access (DMA) buffer to a context that supports virtual addressing with the DxgkDdiSubmitCommandVirtualdevice driver interface (DDI).
old-location: display\dxgkarg_submitcommandvirtual.htm
old-project: display
ms.assetid: 7BBB4BEC-82F1-44B9-A0C2-1073517A4116
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: "_DXGKARG_SUBMITCOMMANDVIRTUAL, display.dxgkarg_submitcommandvirtual, d3dkmddi/DXGKARG_SUBMITCOMMANDVIRTUAL, DXGKARG_SUBMITCOMMANDVIRTUAL, DXGKARG_SUBMITCOMMANDVIRTUAL structure [Display Devices]"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: d3dkmddi.h
req.include-header: D3dkmddi.h
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
req.irql: PASSIVE_LEVEL
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	d3dkmddi.h
apiname:
-	DXGKARG_SUBMITCOMMANDVIRTUAL
product: Windows
targetos: Windows
req.typenames: DXGKARG_SUBMITCOMMANDVIRTUAL
---

# _DXGKARG_SUBMITCOMMANDVIRTUAL structure


## -description


<b>DXGKARG_SUBMITCOMMANDVIRTUAL</b> is used to submit a direct memory access (DMA) buffer to a context that supports virtual addressing with the  <a href="..\d3dkmddi\nc-d3dkmddi-dxgkddi_submitcommandvirtual.md">DxgkDdiSubmitCommandVirtual</a>device driver interface (DDI).




## -syntax


````
typedef struct _DXGKARG_SUBMITCOMMANDVIRTUAL {
  HANDLE                         hContext;
  D3DGPU_VIRTUAL_ADDRESS         DmaBufferVirtualAddress;
  UINT                           DmaBufferSize;
  VOID                           *pDmaBufferPrivateData;
  UINT                           DmaBufferPrivateDataSize;
  UINT                           DmaBufferUmdPrivateDataSize;
  UINT                           SubmissionFenceId;
  D3DDDI_VIDEO_PRESENT_SOURCE_ID VidPnSourceId;
  D3DDDI_FLIPINTERVAL_TYPE       FlipInterval;
  DXGK_SUBMITCOMMANDFLAGS        Flags;
  UINT                           EngineOrdinal;
  UINT                           NodeOrdinal;
} DXGKARG_SUBMITCOMMANDVIRTUAL;
````


## -struct-fields




### -field hContext

The handle returned from <a href="..\d3dkmddi\nc-d3dkmddi-dxgkddi_createcontext.md">DxgkDdiCreateContext</a>.


### -field DmaBufferVirtualAddress

The virtual address for the DMA buffer in the context of the submitting process.


### -field DmaBufferSize

The size of the DMA buffer in bytes.


### -field pDmaBufferPrivateData

A pointer to the driver-private data buffer.


### -field DmaBufferPrivateDataSize

The size of the driver-private data buffer in bytes.


### -field DmaBufferUmdPrivateDataSize

Size of the private driver data, in bytes, that was set by the user mode driver in <b>SubmitCommandCb</b>. When <b>SubmitCommandCb</b> is called, the DirectX graphics kernel allocates a buffer for the private driver data with the size equal to <a href="..\d3dkmddi\ns-d3dkmddi-_dxgk_contextinfo.md">DXGK_CONTEXTINFO</a>::<b>DmaBufferPrivateDataSize</b>. This size was reported by the kernel mode driver in the <a href="..\d3dkmddi\nc-d3dkmddi-dxgkddi_createcontext.md">DxgkDdiCreateContext</a> call. The DirectX graphics kernel copies the driver private data from the <b>SubmitCommandCb</b> to the allocated buffer.


### -field SubmissionFenceId

A unique identifier that the driver can write into the fence command in the ring buffer, which is the buffer where DMA buffers are queued for the GPU to run. For more information about these types of identifiers, see <a href="https://msdn.microsoft.com/0ec8a4eb-c441-47ae-b5de-d86e6065ffd4">Supplying Fence Identifiers</a>.


### -field VidPnSourceId

The zero-based identification number of the video present source in a path of a video present network (VidPN) topology for a flip operation. This member is valid only when the <b>Flip</b> or <b>FlipWithNoWait</b> bit-field flag is set in the <b>Flags</b> member.


### -field FlipInterval

A <a href="..\d3dukmdt\ne-d3dukmdt-d3dddi_flipinterval_type.md">D3DDDI_FLIPINTERVAL_TYPE</a>-typed value that indicates the flip interval (that is, if the flip occurs after zero, one, two, three, or four vertical syncs). <b>FlipInterval</b> is valid only if the <b>Flip</b> bit-field flag is set (that is, <b>TRUE</b>) in the <b>Flags</b> member.


### -field Flags

A <a href="..\d3dkmddi\ns-d3dkmddi-_dxgk_submitcommandflags.md">DXGK_SUBMITCOMMANDFLAGS</a> structure that identifies information about the DMA buffer to submit.


### -field EngineOrdinal

Reserved for future use.


### -field NodeOrdinal

The zero-based index of the node that the context is created for. Identifies the node when the context is <b>NULL</b>.


## -see-also

<a href="..\d3dukmdt\ne-d3dukmdt-d3dddi_flipinterval_type.md">D3DDDI_FLIPINTERVAL_TYPE</a>

<a href="https://msdn.microsoft.com/0ec8a4eb-c441-47ae-b5de-d86e6065ffd4">Supplying Fence Identifiers</a>

<a href="..\d3dkmddi\nc-d3dkmddi-dxgkddi_createcontext.md">DxgkDdiCreateContext</a>

<a href="..\d3dkmddi\nc-d3dkmddi-dxgkddi_submitcommandvirtual.md">DxgkDdiSubmitCommandVirtual</a>

<a href="..\d3dkmddi\ns-d3dkmddi-_dxgk_contextinfo.md">DXGK_CONTEXTINFO</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20DXGKARG_SUBMITCOMMANDVIRTUAL structure%20 RELEASE:%20(12/29/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

