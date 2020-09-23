---
UID: NF:ntifs._FSRTL_ADVANCED_FCB_HEADER.FsRtlOplockGetAnyBreakOwnerProcess
title: FSRTL_ADVANCED_FCB_HEADER::FsRtlOplockGetAnyBreakOwnerProcess
author: windows-driver-content
description: FsRtlOplockGetAnyBreakOwnerProcess gets an owner of an allegedly breaking oplock.
tech.root: ifsk
ms.assetid: fed48308-d88a-40b1-acce-c9c627ce71ed
ms.author: windowsdriverdev
ms.date: 03/24/2020
ms.topic: method
ms.keywords: FSRTL_ADVANCED_FCB_HEADER::FsRtlOplockGetAnyBreakOwnerProcess, FsRtlOplockGetAnyBreakOwnerProcess, FSRTL_ADVANCED_FCB_HEADER.FsRtlOplockGetAnyBreakOwnerProcess, FSRTL_ADVANCED_FCB_HEADER::FsRtlOplockGetAnyBreakOwnerProcess, FSRTL_ADVANCED_FCB_HEADER.FsRtlOplockGetAnyBreakOwnerProcess
req.header: ntifs.h
f1_keywords:
 - "ntifs/FsRtlOplockGetAnyBreakOwnerProcess"
 - "FsRtlOplockGetAnyBreakOwnerProcess"
req.include-header:
req.target-type:
req.target-min-winverclnt: Windows 10, version 2004
req.target-min-winversvr:
req.kmdf-ver:
req.umdf-ver:
req.lib:
req.dll:
req.irql: 
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
- COM
api_location: 
- ntifs.h
api_name: 
- FSRTL_ADVANCED_FCB_HEADER.FsRtlOplockGetAnyBreakOwnerProcess
product: 
- Windows
targetos: Windows

---

# FSRTL_ADVANCED_FCB_HEADER::FsRtlOplockGetAnyBreakOwnerProcess

## -description

**FsRtlOplockGetAnyBreakOwnerProcess** returns an owner of an allegedly breaking opportunistic lock (oplock).

## -parameters

### -param Oplock

Pointer to the opaque oplock structure for the file. This pointer must have been initialized by a previous call to [**FsRtlInitializeOplock**](./nf-ntifs-_fsrtl_advanced_fcb_header-fsrtlinitializeoplock.md).

## -returns

This method returns **NULL** if no owner can be found; otherwise it returns a pointer to an owner's process object (PEPROCESS).

## -remarks

**FsRtlOplockGetAnyBreakOwnerProcess** selects an owner for the allegedly breaking oplock as follows:

- If the oplock has an exclusive owner, **FsRtlOplockGetAnyBreakOwnerProcess** returns a pointer to the exclusive owner's EPROCESS.

- If the oplock does not have an exclusive owner and the break queue is non-empty, **FsRtlOplockGetAnyBreakOwnerProcess** arbitrarily returns a pointer to the first EPROCESS in the queue.

- Otherwise, **FsRtlOplockGetAnyBreakOwnerProcess** returns NULL.

If **FsRtlOplockGetAnyBreakOwnerProcess** returns non-NULL, the caller is responsible for calling [**ObDeferenceObject**](../wdm/nf-wdm-obdereferenceobject.md) to release the reference acquired on its behalf.

**FsRtlOplockGetAnyBreakOwnerProcess** does not attempt to verify that a break is actually pending, or that the process it returns is indeed the owner.

## -see-also

[**FsRtlInitializeOplock**](./nf-ntifs-_fsrtl_advanced_fcb_header-fsrtlinitializeoplock.md)

[**ObDeferenceObject**](../wdm/nf-wdm-obdereferenceobject.md)