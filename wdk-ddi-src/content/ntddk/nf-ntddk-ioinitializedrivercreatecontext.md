---
UID: NF:ntddk.IoInitializeDriverCreateContext
title: IoInitializeDriverCreateContext function (ntddk.h)
description: The IoInitializeDriverCreateContext routine initializes a caller-allocated variable of type IO_DRIVER_CREATE_CONTEXT.
old-location: ifsk\ioinitializedrivercreatecontext.htm
tech.root: ifsk
ms.assetid: 1d35ed3e-d14f-43ad-9c11-38aa37e76492
ms.date: 04/16/2018
keywords: ["IoInitializeDriverCreateContext function"]
ms.keywords: IoInitializeDriverCreateContext, IoInitializeDriverCreateContext routine [Installable File System Drivers], ifsk.ioinitializedrivercreatecontext, ioref_d9c833b9-0246-49b7-83c5-ef02ef562e17.xml, ntddk/IoInitializeDriverCreateContext
req.header: ntddk.h
req.include-header: Ntddk.h, Ntifs.h, Fltkernel.h
req.target-type: Desktop
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
req.irql: See Remarks section.
targetos: Windows
req.typenames: 
f1_keywords:
 - IoInitializeDriverCreateContext
 - ntddk/IoInitializeDriverCreateContext
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - ntddk.h
api_name:
 - IoInitializeDriverCreateContext
---

# IoInitializeDriverCreateContext function


## -description

The <b>IoInitializeDriverCreateContext</b> routine initializes a caller-allocated variable of type <a href="/windows-hardware/drivers/ddi/ntddk/ns-ntddk-_io_driver_create_context">IO_DRIVER_CREATE_CONTEXT</a>.

## -parameters

### -param DriverContext

A pointer to a caller-allocated variable of type IO_DRIVER_CREATE_CONTEXT.

## -remarks

The <b>IoInitializeDriverCreateContext</b> routine initializes a caller-allocated IO_DRIVER_CREATE_CONTEXT structure used in passing additional create parameters to the <a href="/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltcreatefileex2">FltCreateFileEx2</a> and <a href="/windows-hardware/drivers/ddi/ntddk/nf-ntddk-iocreatefileex">IoCreateFileEx</a> routines.

Callers of <b>IoInitializeDriverCreateContext</b> can be running at any IRQL if the <i>DriverContext</i> block is in nonpaged pool. Otherwise, the caller must be running at IRQL <= APC_LEVEL.

Starting in Windows 10, version 1607, this routine sets the <b>SiloContext</b> member of <a href="/windows-hardware/drivers/ddi/ntddk/ns-ntddk-_io_driver_create_context">IO_DRIVER_CREATE_CONTEXT</a> to <b>IO_USE_AMBIENT_SILO</b>.

## -see-also

<a href="/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltcreatefileex2">FltCreateFileEx2</a>



<a href="/windows-hardware/drivers/ddi/ntddk/nf-ntddk-iocreatefileex">IoCreateFileEx</a>