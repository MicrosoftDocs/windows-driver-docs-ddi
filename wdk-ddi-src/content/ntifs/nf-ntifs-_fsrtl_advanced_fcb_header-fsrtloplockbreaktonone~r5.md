---
UID: NF:ntifs.FsRtlOplockBreakToNone~r5
title: FsRtlOplockBreakToNone function (ntifs.h)
description: Obsolete.
old-location: ifsk\fsrtloplockbreaktonone.htm
tech.root: ifsk
ms.date: 03/29/2018
keywords: ["FsRtlOplockBreakToNone function"]
ms.keywords: FsRtlOplockBreakToNone, FsRtlOplockBreakToNone function [Installable File System Drivers], fsrtlref_8d6206fb-3cc8-4f43-83b1-266c398f933e.xml, ifsk.fsrtloplockbreaktonone, ntifs/FsRtlOplockBreakToNone
f1_keywords:
 - "ntifs/FsRtlOplockBreakToNone"
 - "FsRtlOplockBreakToNone"
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
topic_type:
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- ntifs.h
api_name:
- FsRtlOplockBreakToNone
targetos: Windows
req.typenames: TOKEN_TYPE
---

# FsRtlOplockBreakToNone function


## -description


The <b>FsRtlOplockBreakToNone</b> routine is obsolete, but is exported to support existing driver binaries. Use <a href="/windows-hardware/drivers/ddi/ntifs/nf-ntifs-_fsrtl_advanced_fcb_header-fsrtloplockbreaktononeex">FsRtlOplockBreakToNoneEx</a> instead.


## -parameters




### -param Oplock

<p>Reserved.</p>


### -param IrpSp

TBD


### -param Irp

TBD


### -param Context

TBD


### -param CompletionRoutine

TBD


### -param PostIrpRoutine

TBD
