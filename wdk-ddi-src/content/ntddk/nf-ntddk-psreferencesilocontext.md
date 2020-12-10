---
UID: NF:ntddk.PsReferenceSiloContext
title: PsReferenceSiloContext function (ntddk.h)
description: This routine increments the reference count on the object.
old-location: kernel\psreferencesilocontext.htm
tech.root: kernel
ms.date: 04/30/2018
keywords: ["PsReferenceSiloContext function"]
ms.keywords: PsReferenceSiloContext, PsReferenceSiloContext routine [Kernel-Mode Driver Architecture], kernel.psreferencesilocontext, ntddk/PsReferenceSiloContext
req.header: ntddk.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: Windows 10, version 1607
req.target-min-winversvr: Windows Server 2016
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
req.irql: _IRQL_requires_max_(DISPATCH_LEVEL)
targetos: Windows
req.typenames: 
f1_keywords:
 - PsReferenceSiloContext
 - ntddk/PsReferenceSiloContext
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - ntddk.h
api_name:
 - PsReferenceSiloContext
---

# PsReferenceSiloContext function


## -description

This routine increments the reference count on the object.

## -parameters

### -param SiloContext 

[in]
A pointer to the object created by the <a href="/windows-hardware/drivers/ddi/ntddk/nf-ntddk-pscreatesilocontext">PsCreateSiloContext</a> routine. This parameter is required and it cannot be <b>NULL</b>.

## -see-also

<a href="/windows-hardware/drivers/ddi/ntddk/nf-ntddk-pscreatesilocontext">PsCreateSiloContext</a>
