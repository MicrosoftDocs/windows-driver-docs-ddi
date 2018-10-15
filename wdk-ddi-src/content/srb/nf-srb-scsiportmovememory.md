---
UID: NF:srb.ScsiPortMoveMemory
title: ScsiPortMoveMemory function
author: windows-driver-content
description: The ScsiPortMoveMemory routine copies data from one location to another.Note  The SCSI port driver and SCSI miniport driver models may be altered or unavailable in the future.
old-location: storage\scsiportmovememory.htm
tech.root: storage
ms.assetid: c4ed9551-3dc8-4f76-9bcb-26030f76c244
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: ScsiPortMoveMemory, ScsiPortMoveMemory routine [Storage Devices], scsiprt_88a58a03-0663-4aad-b048-2a2d3641e94e.xml, srb/ScsiPortMoveMemory, storage.scsiportmovememory
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: srb.h
req.include-header: 
req.target-type: Universal
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
req.lib: Storport.lib
req.dll: 
req.irql: 
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	LibDef
api_location:
-	storport.lib
-	storport.dll
api_name:
-	ScsiPortMoveMemory
product:
- Windows
targetos: Windows
req.typenames: 
---

# ScsiPortMoveMemory function


## -description


The <b>ScsiPortMoveMemory</b> routine copies data from one location to another.
<div class="alert"><b>Note</b>  The SCSI port driver and SCSI miniport driver models may be altered or unavailable in the future. Instead, we recommend using the <a href="https://msdn.microsoft.com/windows/hardware/drivers/storage/storport-driver">Storport driver</a> and <a href="https://msdn.microsoft.com/windows/hardware/drivers/storage/storport-miniport-drivers">Storport miniport</a> driver models.</div><div> </div>

## -parameters




### -param WriteBuffer [in]

Pointer to the destination buffer.


### -param ReadBuffer [in]

Pointer to the source buffer.


### -param Length [in]

Specifies how many bytes to transfer from <i>ReadBuffer</i> to <i>WriteBuffer</i>.


## -returns



None




## -remarks



<b>ScsiPortMoveMemory</b> can be called if a miniport driver needs to copy data from one system-allocated area to another. For example, a miniport driver might call <b>ScsiPortMoveMemory</b> to copy pertinent SRB values into the driver's SRB extension.

The (<i>ReadBuffer</i> + <i>Length</i>) can overlap the area pointed to by <i>WriteBuffer</i>. 

Each of the given buffer areas must be at least <b>sizeof</b>(<i>Length</i>).



