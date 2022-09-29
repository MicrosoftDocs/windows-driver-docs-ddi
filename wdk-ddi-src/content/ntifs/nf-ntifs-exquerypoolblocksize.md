---
UID: NF:ntifs.ExQueryPoolBlockSize
title: ExQueryPoolBlockSize function (ntifs.h)
description: Obsolete.
old-location: ifsk\exquerypoolblocksize.htm
tech.root: ifsk
ms.date: 05/24/2022
keywords: ["ExQueryPoolBlockSize function"]
ms.keywords: ExQueryPoolBlockSize, ExQueryPoolBlockSize function [Installable File System Drivers], exref_c8686b81-2d69-4bbf-a1fb-143574579cff.xml, ifsk.exquerypoolblocksize, ntifs/ExQueryPoolBlockSize
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
f1_keywords:
 - ExQueryPoolBlockSize
 - ntifs/ExQueryPoolBlockSize
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - ntifs.h
api_name:
 - ExQueryPoolBlockSize
---

# ExQueryPoolBlockSize function

## -description

**ExQueryPoolBlockSize** is obsolete and has never been documented. This routine is exported only to support a small number of legacy drivers. If you call it in Microsoft Windows 2000 and the block is in special pool, the system will crash. Do not use this routine in your driver.

## -parameters

### -param PoolBlock

Reserved.

### -param QuotaCharged

Reserved.

## -returns

Reserved.
