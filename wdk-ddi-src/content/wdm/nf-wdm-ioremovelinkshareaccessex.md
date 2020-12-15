---
UID: NF:wdm.IoRemoveLinkShareAccessEx
title: IoRemoveLinkShareAccessEx function
description: The IoRemoveLinkShareAccessEx routine removes the access and share access information in a file system Share Access structure for a given open instance.
tech.root: ifsk
ms.date: 03/12/2019
keywords: ["IoRemoveLinkShareAccessEx function"]
ms.keywords: IoRemoveLinkShareAccessEx, IoRemoveLinkShareAccessEx function [Kernel-Mode Driver Architecture], kernel.IoRemoveLinkShareAccessEx, wdm/IoRemoveLinkShareAccessEx
req.header: wdm.h
req.include-header: 
req.target-type: Universal
req.target-min-winverclnt: Windows 10, version 1903
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.lib: NtosKrnl.lib
req.dll: NtosKrnl.exe
req.irql: PASSIVE_LEVEL
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
targetos: Windows
ms.custom: 19H1
f1_keywords:
 - IoRemoveLinkShareAccessEx
 - wdm/IoRemoveLinkShareAccessEx
topic_type:
 - apiref
api_type:
 - DllExport
api_location:
 - NtosKrnl.exe
api_name:
 - IoRemoveLinkShareAccessEx
product:
 - Windows
---

# IoRemoveLinkShareAccessEx function


## -description

The <b>IoRemoveLinkShareAccessEx</b> routine removes the access and share access information in a file system Share Access structure for a given open instance.

## -parameters

### -param FileObject 

[in]
Pointer to the file object, which usually is being closed by the current thread.

### -param ShareAccess 

[in, out]
A pointer to the common share-access data structure that is associated with <i>FileObject</i>. Drivers should treat this structure as opaque.

### -param LinkShareAccess 

[in, out, optional]
A pointer to the common link share-access data structure (<a href="/windows-hardware/drivers/ddi/wdm/ns-wdm-_link_share_access">LINK_SHARE_ACCESS</a>) that is associated with <i>FileObject</i>. Drivers should treat this structure as opaque.

### -param IoShareAccessFlags

A bitmask of these flags:

IO_SHARE_ACCESS_NON_PRIMARY_STREAM         (0x00000080) specifies that the stream is neither the primary data stream nor a directory stream.

## -remarks

## -see-also
