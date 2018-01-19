---
UID: NS:d3dumddi._D3DDDICB_SUBMITCOMMAND
title: _D3DDDICB_SUBMITCOMMAND
author: windows-driver-content
description: The D3DDDICB_SUBMITCOMMAND structure is used to submit command buffers on contexts that support graphics processing unit (GPU) virtual addressing.
old-location: display\d3dddicb_submitcommand.htm
old-project: display
ms.assetid: 53D4890A-D075-4DF7-97E6-A8E8A174866B
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: _D3DDDICB_SUBMITCOMMAND, D3DDDICB_SUBMITCOMMAND
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
req.alt-api: D3DDDICB_SUBMITCOMMAND
req.alt-loc: d3dumddi.h
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
req.typenames: D3DDDICB_SUBMITCOMMAND
---

# _D3DDDICB_SUBMITCOMMAND structure



## -description
The <b>D3DDDICB_SUBMITCOMMAND</b> structure is used to submit command buffers on contexts that support graphics processing unit (GPU) virtual addressing.



## -syntax

````
typedef struct _D3DDDICB_SUBMITCOMMAND {
  D3DGPU_VIRTUAL_ADDRESS      Commands;
  UINT                        CommandLength;
  D3DDDICB_SUBMITCOMMANDFLAGS Flags;
  UINT                        BroadcastContextCount;
  HANDLE                      BroadcastContext[D3DDDI_MAX_BROADCAST_CONTEXT];
  VOID                        *pPrivateDriverData;
  UINT                        PrivateDriverDataSize;
  UINT                        NumPrimaries;
  D3DKMT_HANDLE               WrittenPrimaries[D3DDDI_MAX_WRITTEN_PRIMARIES];
  D3DDDI_MARKERLOGTYPE        MarkerLogType;
  UINT                        RenderCBSequence;
  UINT                        FirstAPISequenceNumberHigh;
  UINT                        CompletedAPISequenceNumberLow0Size;
  UINT                        CompletedAPISequenceNumberLow1Size;
  UINT                        BegunAPISequenceNumberLow0Size;
  UINT                        BegunAPISequenceNumberLow1Size;
  const UINT                  *pCompletedAPISequenceNumberLow0;
  const  UINT                 *pCompletedAPISequenceNumberLow1;
  const  UINT                 *pBegunAPISequenceNumberLow0;
  const  UINT                 *pBegunAPISequenceNumberLow1;
  UINT                        Reserved;
  UINT                        NumHistoryBuffers;
  D3DKMT_HANDLE               *HistoryBufferArray;
} D3DDDICB_SUBMITCOMMAND;
````


## -struct-fields

### -field Commands

GPU virtual address to the commands being submitted to the context for execution. This information is provided to the kernel mode driver during command submission and is also used for debugging purposes.


### -field CommandLength

Specifies the length, in bytes, of the commands being submitted to the GPU. This information is provided to the kernel  mode driver during command submission and is also used for debugging purposes.


### -field Flags

An instance of the <a href="..\d3dumddi\ns-d3dumddi-_d3dddicb_submitcommandflags.md">D3DDDICB_SUBMITCOMMANDFLAGS</a> structure.


### -field BroadcastContextCount

Specifies the number of context these command should be submitted to. This count must be at least 1.


### -field BroadcastContext

Specifies the handle of the context to execute the specified commands.


### -field pPrivateDriverData

Pointer to driver private data to be passed to the kernel mode driver as part of this submission.


### -field PrivateDriverDataSize

Size of the private driver data information being passed. This size must be smaller than the size requested by the kernel mode driver for submission private driver data.


### -field NumPrimaries

Specifies the number of primaries and swapchain back buffers being written to by the submitted commands. This is equal to the number of allocations in the <b>WrittenPrimaries</b> array.


### -field WrittenPrimaries

Arrays of handle to the primaries and swapchain back buffers being written to by the submitted commands.


### -field MarkerLogType

A <a href="..\d3dumddi\ne-d3dumddi-d3dddi_markerlogtype.md">D3DDDI_MARKERLOGTYPE</a> enumeration that indicates the type of marker in the Event Tracing for Windows (ETW) log that the user-mode display driver supports.


### -field RenderCBSequence

A unique identifier for each <a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_rendercb.md">pfnRenderCb</a> function call. Starts at a value of 1 for contexts associated with single-threaded user-mode DDIs and ranges to a value of 0x80000001 for contexts associated with free-threaded user mode DDIs. The user-mode display driver must increment the value for each <i>pfnRenderCb</i> call it makes on any engine.


### -field FirstAPISequenceNumberHigh

Used by the driver to pass the context's API sequence number.


### -field CompletedAPISequenceNumberLow0Size

Used by the driver to pass the context's API sequence number.


### -field CompletedAPISequenceNumberLow1Size

Used by the driver to pass the context's API sequence number.


### -field BegunAPISequenceNumberLow0Size

Used by the driver to pass the context's API sequence number.


### -field BegunAPISequenceNumberLow1Size

Used by the driver to pass the context's API sequence number.


### -field pCompletedAPISequenceNumberLow0

A pointer used by the driver to pass the context's API sequence number.


### -field pCompletedAPISequenceNumberLow1

A pointer used by the driver to pass the context's API sequence number.


### -field pBegunAPISequenceNumberLow0

A pointer used by the driver to pass the context's API sequence number.


### -field pBegunAPISequenceNumberLow1

A pointer used by the driver to pass the context's API sequence number.


### -field Reserved

This member is reserved and should be set to zero.


### -field NumHistoryBuffers

The number of history buffers.


### -field HistoryBufferArray

A pointer to the array of history buffers.


## -remarks
The <a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_submitcommandcb.md">pfnSubmitCommandCb</a> code path no longer provides an allocation list for the user mode driver to provide a list of allocations that will be read and written to during this command. However, it is necessary to synchronize some writes that would not normally be known without the allocation list. For this, a new small allocation list specifically for surfaces which will be written to and used for displaying content. The <b>WrittenPrimaries</b> array should be used to provide such allocations.


Despite the name, <b>WrittenPrimaries</b> must contain allocations that are considered <i>SwapChainBackBuffer</i> allocations according to the runtime in addition to the primaries. This is exposed to the user mode driver by a new flag in <a href="..\d3d10umddi\ne-d3d10umddi-d3d10_ddi_resource_misc_flag.md">D3D10_DDI_RESOURCE_MISC_FLAG</a>. The runtime will provide the <b>D3DWDDM2_0DDI_RESOURCE_MISC_DISPLAYABLE_SURFACE</b> flag to the user mode driver during calls to create a resource or heap that is created as a <i>FlipEx swapchain</i> or <i>primary</i>. The driver may use this flag to determine all allocations that should be put in the <b>WrittenPrimaries</b> list for Microsoft Direct3D 11. Other runtimes have not changed.


If the driver receives a call to <a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_createresource.md">CreateResource</a> that has this flag, the allocation should be added to this list on every <a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_submitcommandcb.md">pfnSubmitCommandCb</a> call that writes to the surface.


## -see-also
<dl>
<dt>
<a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_rendercb.md">pfnRenderCb</a>
</dt>
<dt>
<a href="..\d3d10umddi\ne-d3d10umddi-d3d10_ddi_resource_misc_flag.md">D3D10_DDI_RESOURCE_MISC_FLAG</a>
</dt>
<dt>
<a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_submitcommandcb.md">pfnSubmitCommandCb</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20D3DDDICB_SUBMITCOMMAND structure%20 RELEASE:%20(12/29/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

