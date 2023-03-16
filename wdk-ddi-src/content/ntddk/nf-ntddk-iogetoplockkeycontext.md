---
UID: NF:ntddk.IoGetOplockKeyContext
title: IoGetOplockKeyContext function (ntddk.h)
description: The IoGetOplockKeyContext routine returns a target oplock key context for a file object.
tech.root: ifsk
ms.date: 03/16/2023
keywords: ["IoGetOplockKeyContext function"]
ms.keywords: IoGetOplockKeyContext, IoGetOplockKeyContextEx, IoGetOplockKeyContextEx routine [Installable File System Drivers], ifsk.iogetoplockkeycontext, ntddk/IoGetOplockKeyContextEx
req.header: ntddk.h
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
req.lib: Ntoskrnl.lib
req.dll: 
req.irql: <= DISPATCH_LEVEL
targetos: Windows
req.typenames: 
f1_keywords:
 - IoGetOplockKeyContext
 - ntddk/IoGetOplockKeyContext
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - LibDef
api_location:
 - ntoskrnl.lib
 - ntoskrnl.dll
api_name:
 - IoGetOplockKeyContext
---

## -description

The **IoGetOplockKeyContext** routine returns a target oplock key context for a file object.

## -parameters

### -param FileObject

The file object to query for an oplock key context.

## -returns

An pointer to an [**OPLOCK_KEY_ECP_CONTEXT**](/windows-hardware/drivers/ddi/ntifs/ns-ntifs-oplock_key_ecp_context) structure containing the target oplock key for *FileObject*. Otherwise, NULL if *FileObject*  has no target oplock key.

## -remarks

Use the **IoGetOplockKeyContext** routine only in Windows 7. Because  [IoGetOplockKeyContextEx](./nf-ntddk-iogetoplockkeycontextex.md) returns a dual oplock key context, it should be used in Windows 8 and later versions of Windows.

## -see-also

[IoGetOplockKeyContextEx](./nf-ntddk-iogetoplockkeycontextex.md)

[**OPLOCK_KEY_CONTEXT**](./ns-ntddk-_oplock_key_context.md)

[**OPLOCK_KEY_ECP_CONTEXT**](/windows-hardware/drivers/ddi/ntifs/ns-ntifs-oplock_key_ecp_context)
