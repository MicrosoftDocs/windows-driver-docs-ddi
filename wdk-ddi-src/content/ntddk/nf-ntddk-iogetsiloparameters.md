---
UID: NF:ntddk.IoGetSiloParameters
title: IoGetSiloParameters function (ntddk.h)
description: This routine indicates if a file is within a Container context.
old-location: ifsk\iogetsiloparameters.htm
tech.root: ifsk
ms.date: 04/16/2018
keywords: ["IoGetSiloParameters function"]
ms.keywords: IoGetSiloParameters, IoGetSiloParameters function [Installable File System Drivers], PIO_FOEXT_SILO_PARAMETERS, ifsk.iogetsiloparameters, ntddk/IoGetSiloParameters
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
req.lib: NtosKrnl.lib
req.dll: NtosKrnl.exe
req.irql: 
targetos: Windows
req.typenames: 
f1_keywords:
 - IoGetSiloParameters
 - ntddk/IoGetSiloParameters
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - DllExport
api_location:
 - NtosKrnl.exe
api_name:
 - IoGetSiloParameters
---

# IoGetSiloParameters function


## -description

This routine indicates if a file is within a Container context.

## -parameters

### -param FileObject 

[in]
The file in question.

## -returns

If <b>null</b>, the file is not in a container context. Otherwise, a non-null value of type <a href="/windows-hardware/drivers/ddi/ntddk/ns-ntddk-_io_foext_silo_parameters">IO_FOEXT_SILO_PARAMETERS</a> indicates that the file is within a Container context.
