---
UID: NF:wdm.IoUpdateLinkShareAccessEx
title: IoUpdateLinkShareAccessEx function
description: The IoUpdateLinkShareAccessEx routine updates the share access for the given file object, usually when the file is being opened.
tech.root: kernel
ms.date: 03/12/2019
keywords: ["IoUpdateLinkShareAccessEx function"]
ms.keywords: IoUpdateLinkShareAccessEx, IoUpdateLinkShareAccessEx function [Kernel-Mode Driver Architecture], kernel.IoUpdateLinkShareAccessEx, wdm/IoUpdateLinkShareAccessEx
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
 - IoUpdateLinkShareAccessEx
 - wdm/IoUpdateLinkShareAccessEx
topic_type:
 - apiref
api_type:
 - DllExport
api_location:
 - NtosKrnl.exe
api_name:
 - IoUpdateLinkShareAccessEx
---

# IoUpdateLinkShareAccessEx function


## -description

The <b>IoUpdateLinkShareAccessEx</b> routine updates the access and share access for the given file object.

## -parameters

### -param FileObject

Pointer to the file object, which usually is being closed by the current thread.

### -param ShareAccess

A pointer to the common share-access data structure that is associated with <i>FileObject</i>. Drivers should treat this structure as opaque.

### -param LinkShareAccess

A pointer to the common link share-access data structure (<a href="/windows-hardware/drivers/ddi/wdm/ns-wdm-_link_share_access">LINK_SHARE_ACCESS</a>) that is associated with <i>FileObject</i>. Drivers should treat this structure as opaque.

### -param IoShareAccessFlags

A bitmask of these flags:

IO_SHARE_ACCESS_NON_PRIMARY_STREAM         (0x00000080) specifies that the stream is neither the primary data stream nor a directory stream.

## -remarks

Before calling **IoUpdateLinkShareAccessEx**, the driver must successfully call [**IoCheckLinkShareAccess**](./nf-wdm-iochecklinkshareaccess.md) with the *Update* parameter set to **FALSE**.

## -see-also
