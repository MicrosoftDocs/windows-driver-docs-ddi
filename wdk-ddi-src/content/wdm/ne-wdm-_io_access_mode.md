---
UID: NE:wdm._IO_ACCESS_MODE
title: _IO_ACCESS_MODE (wdm.h)
description: Defines the types of access mode for Scheduled File I/O (SFIO).
old-location: kernel\io_access_mode.htm
tech.root: kernel
ms.assetid: E48BDF14-5B56-45AF-9DD2-F019C8B7D7E5
ms.date: 04/30/2018
keywords: ["_IO_ACCESS_MODE enumeration"]
ms.keywords: IO_ACCESS_MODE, IO_ACCESS_MODE enumeration [Kernel-Mode Driver Architecture], RandomAccess, SequentialAccess, _IO_ACCESS_MODE, kernel.io_access_mode, wdm/IO_ACCESS_MODE, wdm/RandomAccess, wdm/SequentialAccess
f1_keywords:
 - "wdm/IO_ACCESS_MODE"
 - "IO_ACCESS_MODE"
req.header: wdm.h
req.include-header: Wdm.h, Ntddsfio.h
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
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- wdm.h
api_name:
- IO_ACCESS_MODE
product:
- Windows
targetos: Windows
req.typenames: IO_ACCESS_MODE
---

# _IO_ACCESS_MODE enumeration


## -description


Defines the types of access mode for Scheduled File I/O (SFIO).


## -enum-fields




### -field SequentialAccess

Indicates that the input/output will be sent down in a sequential order.


### -field RandomAccess

Indicates that the input/output might not be in a predictable order.

