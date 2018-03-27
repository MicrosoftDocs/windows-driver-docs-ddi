---
UID: NS:d3dkmthk._D3DKMT_SUBMITCOMMANDTOHWQUEUE
title: "_D3DKMT_SUBMITCOMMANDTOHWQUEUE"
author: windows-driver-content
description: A structure that holds information to submit a command to the hardware queue.
old-location: display\d3dkmt_submitcommandtohwqueue.htm
old-project: display
ms.assetid: 3807BD27-FAE4-4E12-A825-A9FAFB7A6ACA
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: D3DKMT_SUBMITCOMMANDTOHWQUEUE, D3DKMT_SUBMITCOMMANDTOHWQUEUE structure [Display Devices], _D3DKMT_SUBMITCOMMANDTOHWQUEUE, d3dkmthk/D3DKMT_SUBMITCOMMANDTOHWQUEUE, display.d3dkmt_submitcommandtohwqueue
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: d3dkmthk.h
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
-	d3dkmthk.h
api_name:
-	D3DKMT_SUBMITCOMMANDTOHWQUEUE
product: Windows
targetos: Windows
req.typenames: D3DKMT_SUBMITCOMMANDTOHWQUEUE
---

# _D3DKMT_SUBMITCOMMANDTOHWQUEUE structure


## -description


A structure that holds information to submit a command to the hardware queue.


## -struct-fields




### -field hHwQueue

Context queue to submit the command to.



### -field HwQueueProgressFenceId

Hardware queue progress fence value that will be signaled once the command is finished.


### -field CommandBuffer

GPU VA of the command buffer to be executed on the GPU.



### -field CommandLength

Length in bytes of the command buffer.




### -field PrivateDriverDataSize

Size of private driver data in bytes.




### -field pPrivateDriverData

Pointer to the private driver data.



### -field NumPrimaries

The number of primaries written by this command buffer.



### -field WrittenPrimaries

The array of primaries written by this command buffer.


