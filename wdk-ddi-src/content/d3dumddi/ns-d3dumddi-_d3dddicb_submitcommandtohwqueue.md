---
UID: NS:d3dumddi._D3DDDICB_SUBMITCOMMANDTOHWQUEUE
title: "_D3DDDICB_SUBMITCOMMANDTOHWQUEUE"
author: windows-driver-content
description: A structure that holds information to queue hardware.
old-location: display\d3dddicb_submitcommandtohwqueue.htm
tech.root: display
ms.assetid: 5B650831-7AD7-4FEA-AC31-82F2B351BAD6
ms.date: 05/10/2018
ms.keywords: D3DDDICB_SUBMITCOMMANDTOHWQUEUE, D3DDDICB_SUBMITCOMMANDTOHWQUEUE structure [Display Devices], _D3DDDICB_SUBMITCOMMANDTOHWQUEUE, d3dumddi/D3DDDICB_SUBMITCOMMANDTOHWQUEUE, display.d3dddicb_submitcommandtohwqueue
ms.topic: struct
req.header: d3dumddi.h
req.include-header:
req.target-type: Windows
req.target-min-winverclnt:
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
-	d3dumddi.h
api_name:
-	D3DDDICB_SUBMITCOMMANDTOHWQUEUE
product:
- Windows
targetos: Windows
req.typenames: D3DDDICB_SUBMITCOMMANDTOHWQUEUE
---

# _D3DDDICB_SUBMITCOMMANDTOHWQUEUE structure


## -description


A structure that holds information to queue hardware.


## -struct-fields




### -field hHwQueue

[in] Hardware queue being submitted to.

### -field HwQueueProgressFenceId

Hardware queue progress fence ID that will be signaled when the Present Blt is done on the GPU.

### -field Commands

GPU VA of the command buffer to be executed on the GPU.


### -field CommandLength

Length in bytes of the command buffer.

### -field Flags

Flags.


### -field PrivateDriverDataSize

The size of pPrivateDriverData.

### -field pPrivateDriverData

Private driver data to pass to [Present](nc-d3dumddi-pfnd3dddi_present.md).

### -field NumPrimaries

The number of primaries written by this command buffer.


### -field WrittenPrimaries

The array of primaries written by this command buffer.



