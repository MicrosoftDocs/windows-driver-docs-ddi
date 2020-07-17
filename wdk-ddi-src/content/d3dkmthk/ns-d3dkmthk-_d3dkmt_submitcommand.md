---
UID: NS:d3dkmthk._D3DKMT_SUBMITCOMMAND
title: _D3DKMT_SUBMITCOMMAND (d3dkmthk.h)
description: The D3DKMT_SUBMITCOMMAND structure is used to submit command buffers on contexts that support graphics processing unit (GPU) virtual addressing.
old-location: display\d3dkmt_submitcommand.htm
ms.assetid: FA6EA2BA-938C-4377-A85A-2168C4C1F3C6
ms.date: 05/10/2018
keywords: ["_D3DKMT_SUBMITCOMMAND structure"]
ms.keywords: D3DKMT_SUBMITCOMMAND, D3DKMT_SUBMITCOMMAND structure [Display Devices], _D3DKMT_SUBMITCOMMAND, d3dkmthk/D3DKMT_SUBMITCOMMAND, display.d3dkmt_submitcommand
f1_keywords:
 - "d3dkmthk/D3DKMT_SUBMITCOMMAND"
 - "D3DKMT_SUBMITCOMMAND"
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
- D3DKMT_SUBMITCOMMAND
product:
- Windows
targetos: Windows
tech.root: display
req.typenames: D3DKMT_SUBMITCOMMAND
---

# _D3DKMT_SUBMITCOMMAND structure


## -description


The <b>D3DKMT_SUBMITCOMMAND</b> structure is used to submit command buffers on contexts that support graphics processing unit (GPU) virtual addressing.


## -struct-fields




### -field Commands

The GPU virtual address for the commands being submitted to the context for execution. This information is provided to the driver during command submission and is also used for debugging purposes.


### -field CommandLength

Specifies the length, in bytes, of the commands being submitted to the GPU. 


### -field Flags

An instance of the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dumddi/ns-d3dumddi-_d3dddicb_submitcommandflags">D3DDDICB_SUBMITCOMMANDFLAGS</a> structure.


### -field PresentHistoryToken

This member is reserved for future use.


### -field BroadcastContextCount

Specifies the number of context these command should be submitted to. This count must be at least 1.


### -field BroadcastContext

Specifies the handle of the context to execute the specified commands.


### -field pPrivateDriverData

Pointer to the driver private data to submitted by the user mode driver.


### -field PrivateDriverDataSize

Size of the private driver data information being passed. This size must be smaller than the size requested by the kernel mode  driver for submission private driver data or the call will fail.


### -field NumPrimaries

Specifies the number of primaries and swapchain back buffers being written to by the submitted commands. This is equal to the number of allocations in the <b>WrittenPrimaries</b> array.


### -field WrittenPrimaries

Arrays of handle to the primaries and swapchain back buffers being written to by the submitted commands.


### -field NumHistoryBuffers

This member is reserved for future use.


### -field HistoryBufferArray

This member is reserved for future use.


## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dumddi/ns-d3dumddi-_d3dddicb_submitcommandflags">D3DDDICB_SUBMITCOMMANDFLAGS</a>
 

 

