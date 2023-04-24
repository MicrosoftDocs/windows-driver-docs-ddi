---
UID: NF:ntddk.IoGetOplockKeyContextEx
title: IoGetOplockKeyContextEx function (ntddk.h)
description: The IoGetOplockKeyContextEx routine returns a dual oplock key context for a file object.
tech.root: ifsk
ms.date: 03/16/2023
keywords: ["IoGetOplockKeyContextEx function"]
ms.keywords: IoGetOplockKeyContext, IoGetOplockKeyContextEx, IoGetOplockKeyContextEx routine [Installable File System Drivers], ifsk.iogetoplockkeycontext, ntddk/IoGetOplockKeyContextEx
req.header: ntddk.h
req.include-header: 
req.target-type: Universal
req.target-min-winverclnt: The IoGetOplockKeyContextEx routine is available starting with Windows 8.
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
 - IoGetOplockKeyContextEx
 - ntddk/IoGetOplockKeyContextEx
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - LibDef
api_location:
 - ntoskrnl.lib
 - ntoskrnl.dll
api_name:
 - IoGetOplockKeyContextEx
---

## -description

The **IoGetOplockKeyContext** routine returns a dual oplock key context for a file object.

## -parameters

### -param FileObject

The file object to query for an oplock key context.

## -returns

An pointer to an [**OPLOCK_KEY_CONTEXT**](./ns-ntddk-_oplock_key_context.md) structure containing the parent and target oplock keys for *FileObject*. Otherwise, NULL if *FileObject* has no oplock keys.

## -remarks

On Windows 8 and later versions of Windows, use **IoGetOplockKeyContextEx** instead of [IoGetOplockKeyContext](./nf-ntddk-iogetoplockkeycontext.md), as the latter only returns a target oplock key context.

## -see-also

[IoGetOplockKeyContext](./nf-ntddk-iogetoplockkeycontext.md)

[**OPLOCK_KEY_CONTEXT**](./ns-ntddk-_oplock_key_context.md)

[**OPLOCK_KEY_ECP_CONTEXT**](/windows-hardware/drivers/ddi/ntifs/ns-ntifs-oplock_key_ecp_context)
