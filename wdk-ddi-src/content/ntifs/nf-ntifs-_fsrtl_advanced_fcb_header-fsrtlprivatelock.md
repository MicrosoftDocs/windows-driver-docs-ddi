---
UID: NF:ntifs.FsRtlPrivateLock
title: FsRtlPrivateLock function (ntifs.h)
description: Obsolete.
old-location: ifsk\fsrtlprivatelock.htm
tech.root: ifsk
ms.date: 04/16/2018
keywords: ["FsRtlPrivateLock function"]
ms.keywords: FsRtlPrivateLock, FsRtlPrivateLock function [Installable File System Drivers], fsrtlref_950e4ca4-4e7f-4158-8e1e-083af825488d.xml, ifsk.fsrtlprivatelock, ntifs/FsRtlPrivateLock
req.header: ntifs.h
req.include-header: Ntifs.h
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
targetos: Windows
req.typenames: 
ms.custom: RS5
f1_keywords:
 - FsRtlPrivateLock
 - ntifs/FsRtlPrivateLock
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - ntifs.h
api_name:
 - FsRtlPrivateLock
dev_langs:
 - c++
---

# FsRtlPrivateLock function


## -description

The <b>FsRtlPrivateLock</b> routine is obsolete, but is exported to support existing driver binaries. Use <a href="/windows-hardware/drivers/ddi/ntifs/nf-ntifs-fsrtlfastlock">FsRtlFastLock</a> instead.

## -parameters

### -param FileLock

<p>Reserved.</p>

### -param FileObject

Reserved.

### -param FileOffset

Reserved.

### -param Length

Reserved.

### -param ProcessId

Reserved.

### -param Key

Reserved.

### -param FailImmediately

Reserved.

### -param ExclusiveLock

Reserved.

### -param Iosb

Reserved.

### -param Irp

Reserved.

### -param Context

Reserved.

### -param AlreadySynchronized

Reserved.
