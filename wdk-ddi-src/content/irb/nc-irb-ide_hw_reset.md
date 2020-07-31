---
UID: NC:irb.IDE_HW_RESET
title: IDE_HW_RESET (irb.h)
description: The IdeHwReset miniport driver routine resets the channel.Note  The ATA port driver and ATA miniport driver models may be altered or unavailable in the future.
old-location: storage\idehwreset.htm
tech.root: storage
ms.assetid: 722810c8-ddf2-4910-8cf3-af3511d8c167
ms.date: 03/29/2018
keywords: ["IDE_HW_RESET callback function"]
ms.keywords: IDE_HW_RESET, IdeHwReset, IdeHwReset routine [Storage Devices], atartns_c3c999ac-3737-48ab-be9b-99c83013b878.xml, irb/IdeHwReset, storage.idehwreset
f1_keywords:
 - "irb/IdeHwReset"
 - "IdeHwReset"
req.header: irb.h
req.include-header: Irb.h
req.target-type: Desktop
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
- APIRef
- kbSyntax
api_type:
- UserDefined
api_location:
- irb.h
api_name:
- IdeHwReset
targetos: Windows
req.typenames: 
---

# IDE_HW_RESET callback function


## -description


The <b><i>IdeHwReset</i></b> miniport driver routine resets the channel.
<div class="alert"><b>Note</b>  The ATA port driver and ATA miniport driver models may be altered or unavailable in the future. Instead, we recommend using the <a href="https://docs.microsoft.com/windows-hardware/drivers/storage/storport-driver">Storport driver</a> and <a href="https://docs.microsoft.com/windows-hardware/drivers/storage/storport-miniport-drivers">Storport miniport</a> driver models.</div><div> </div>

## -parameters




### -param ChannelExtension [in]

A pointer to the channel extension.


## -returns



<b><i>IdeHwReset</i></b> returns <b>TRUE</b> if the reset operation succeeded.  Otherwise, it returns <b>FALSE</b>. 




## -remarks



The <b><i>IdeHwReset</i></b> routine should complete all pending requests and reset the indicated channel.

<b><i>IdeHwReset</i></b> can be called even if the miniport driver is not ready for another request.



