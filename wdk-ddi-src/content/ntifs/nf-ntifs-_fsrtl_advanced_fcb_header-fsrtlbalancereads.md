---
UID: NF:ntifs.FsRtlBalanceReads
title: FsRtlBalanceReads function (ntifs.h)
description: The FsRtlBalanceReads routine signals to a fault-tolerant disk driver that it is now safe to start balancing reads from a mirrored drive.
old-location: ifsk\fsrtlbalancereads.htm
tech.root: ifsk
ms.date: 04/16/2018
keywords: ["FsRtlBalanceReads function"]
ms.keywords: FsRtlBalanceReads, FsRtlBalanceReads routine [Installable File System Drivers], fsrtlref_9785018d-4a2f-44e8-a533-85ab1878e855.xml, ifsk.fsrtlbalancereads, ntifs/FsRtlBalanceReads
req.header: ntifs.h
req.include-header: Ntifs.h
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
req.lib: NtosKrnl.lib
req.dll: NtosKrnl.exe
req.irql: PASSIVE_LEVEL
targetos: Windows
req.typenames: 
f1_keywords:
 - FsRtlBalanceReads
 - ntifs/FsRtlBalanceReads
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - DllExport
api_location:
 - NtosKrnl.exe
api_name:
 - FsRtlBalanceReads
---

# FsRtlBalanceReads function


## -description

The <b>FsRtlBalanceReads</b> routine signals to a fault-tolerant disk driver that it is now safe to start balancing reads from a mirrored drive.

## -parameters

### -param TargetDevice [in]


A pointer to the device object from which the device starts the balanced read.

## -returns

<b>FsRtlBalanceReads</b> returns STATUS_INVALID_DEVICE_REQUEST if the device is not a mirror.

## -remarks

<b>FsRtlBalanceReads</b> signals to a fault-tolerant disk driver that it is safe to start balancing reads from a mirrored drive. A file system typically calls <b>FsRtlBalanceReads</b> for a newly mounted volume once it has determined that the volume is clean.

## -see-also

<a href="/windows-hardware/drivers/ddi/ntifs/nf-ntifs-ccistheredirtydata">CcIsThereDirtyData</a>
