---
UID: NF:wdm.IoUpdateLinkShareAccessEx
title: IoUpdateLinkShareAccessEx function
author: windows-driver-content
description: The IoUpdateLinkShareAccessEx routine updates the share access for the given file object, usually when the file is being opened.
tech.root: kernel
ms.assetid: c7670aa5-9deb-4337-be70-6116ed5c798f
ms.author: windowsdriverdev
ms.date: 03/12/2019
ms.topic: function
f1_keywords:
 - "wdm/IoUpdateLinkShareAccessEx"
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
topic_type: 
- apiref
api_type: 
- 
api_location: 
- NtosKrnl.exe
api_name: 
- IoUpdateLinkShareAccessEx
product: 
- Windows
targetos: Windows

ms.custom: 19H1
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

A pointer to the common link share-access data structure (<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdm/ns-wdm-_link_share_access">LINK_SHARE_ACCESS</a>) that is associated with <i>FileObject</i>. Drivers should treat this structure as opaque.

### -param IoShareAccessFlags

A bitmask of these flags:

IO_SHARE_ACCESS_NON_PRIMARY_STREAM         (0x00000080) specifies that the stream is neither the primary data stream nor a directory stream.


## -returns
This function returns VOID.

## -remarks

Before calling **IoUpdateLinkShareAccessEx**, the driver must successfully call [**IoCheckLinkShareAccess**](https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdm/nf-wdm-iochecklinkshareaccess) with the *Update* parameter set to **FALSE**.

## -see-also
