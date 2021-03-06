---
UID: NS:ntddk._IO_FOEXT_SILO_PARAMETERS
title: _IO_FOEXT_SILO_PARAMETERS (ntddk.h)
description: This structure describes the Container context that's identified by the IoGetSiloParameters routine.
old-location: ifsk\io_foext_silo_parameters.htm
tech.root: ifsk
ms.date: 04/16/2018
keywords: ["IO_FOEXT_SILO_PARAMETERS structure"]
ms.keywords: "*PIO_FOEXT_SILO_PARAMETERS, IO_FOEXT_SILO_PARAMETERS, IO_FOEXT_SILO_PARAMETERS structure [Installable File System Drivers], PIO_FOEXT_SILO_PARAMETERS, PIO_FOEXT_SILO_PARAMETERS structure pointer [Installable File System Drivers], _IO_FOEXT_SILO_PARAMETERS, ifsk.io_foext_silo_parameters, ntddk/IO_FOEXT_SILO_PARAMETERS, ntddk/PIO_FOEXT_SILO_PARAMETERS"
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
req.irql: 
targetos: Windows
req.typenames: IO_FOEXT_SILO_PARAMETERS, *PIO_FOEXT_SILO_PARAMETERS
f1_keywords:
 - _IO_FOEXT_SILO_PARAMETERS
 - ntddk/_IO_FOEXT_SILO_PARAMETERS
 - PIO_FOEXT_SILO_PARAMETERS
 - ntddk/PIO_FOEXT_SILO_PARAMETERS
 - IO_FOEXT_SILO_PARAMETERS
 - ntddk/IO_FOEXT_SILO_PARAMETERS
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - ntddk.h
api_name:
 - _IO_FOEXT_SILO_PARAMETERS
 - PIO_FOEXT_SILO_PARAMETERS
 - IO_FOEXT_SILO_PARAMETERS
---

# _IO_FOEXT_SILO_PARAMETERS structure


## -description

This structure describes the Container context that's identified by the <a href="/windows-hardware/drivers/ddi/ntddk/nf-ntddk-iogetsiloparameters">IoGetSiloParameters</a> routine.

## -struct-fields

### -field Length

The length of the structure. This also serves as the structure version.

### -field HasHardReference

### -field SpareFlags

### -field Flags

### -field SiloContext

The container context.

