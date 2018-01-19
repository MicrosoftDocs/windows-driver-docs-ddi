---
UID: NC:irb.IDE_HW_RESET
title: IDE_HW_RESET
author: windows-driver-content
description: The IdeHwReset miniport driver routine resets the channel.Note  The ATA port driver and ATA miniport driver models may be altered or unavailable in the future.
old-location: storage\idehwreset.htm
old-project: storage
ms.assetid: 722810c8-ddf2-4910-8cf3-af3511d8c167
ms.author: windowsdriverdev
ms.date: 1/10/2018
ms.keywords: WdmlibIoGetAffinityInterrupt
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: irb.h
req.include-header: Irb.h
req.target-type: Desktop
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: IdeHwReset
req.alt-loc: irb.h
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
req.typenames: LUID
---

# IDE_HW_RESET callback



## -description
The <b><i>IdeHwReset</i></b> miniport driver routine resets the channel.



## -prototype

````
IDE_HW_RESET IdeHwReset;

BOOLEAN IdeHwReset(
  _In_ PVOID ChannelExtension
)
{ ... }
````


## -parameters

### -param ChannelExtension [in]

A pointer to the channel extension.


## -returns
<b><i>IdeHwReset</i></b> returns <b>TRUE</b> if the reset operation succeeded.  Otherwise, it returns <b>FALSE</b>. 


## -remarks
The <b><i>IdeHwReset</i></b> routine should complete all pending requests and reset the indicated channel.

<b><i>IdeHwReset</i></b> can be called even if the miniport driver is not ready for another request.</p>