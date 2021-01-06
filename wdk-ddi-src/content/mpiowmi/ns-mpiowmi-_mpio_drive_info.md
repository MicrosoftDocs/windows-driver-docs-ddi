---
UID: NS:mpiowmi._MPIO_DRIVE_INFO
title: _MPIO_DRIVE_INFO (mpiowmi.h)
description: The MPIO_DRIVE_INFO structure represents a multi-path disk in the system.
old-location: storage\mpio_drive_info.htm
tech.root: storage
ms.date: 03/29/2018
keywords: ["MPIO_DRIVE_INFO structure"]
ms.keywords: "*PMPIO_DRIVE_INFO, MPIO_DRIVE_INFO, MPIO_DRIVE_INFO structure [Storage Devices], PMPIO_DRIVE_INFO, PMPIO_DRIVE_INFO structure pointer [Storage Devices], _MPIO_DRIVE_INFO, mpiowmi/MPIO_DRIVE_INFO, mpiowmi/PMPIO_DRIVE_INFO, storage.mpio_drive_info, structs-scsibus_307e7c06-15cc-4d25-9cd6-115370e20036.xml"
req.header: mpiowmi.h
req.include-header: Mpiowmi.h
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
req.typenames: MPIO_DRIVE_INFO, *PMPIO_DRIVE_INFO
f1_keywords:
 - _MPIO_DRIVE_INFO
 - mpiowmi/_MPIO_DRIVE_INFO
 - PMPIO_DRIVE_INFO
 - mpiowmi/PMPIO_DRIVE_INFO
 - MPIO_DRIVE_INFO
 - mpiowmi/MPIO_DRIVE_INFO
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - mpiowmi.h
api_name:
 - MPIO_DRIVE_INFO
---

# _MPIO_DRIVE_INFO structure


## -description

The MPIO_DRIVE_INFO structure represents a multi-path disk in the system.

## -struct-fields

### -field NumberPaths

An unsigned 32-bitfield that represents the number of paths to the LUN.

### -field Name

A string field (of maximum length 63 characters) that returns the device name that was created by MPIO for the LUN.

### -field SerialNumber

A string field (of maximum length 63 characters) that returns the serial number that was created for the LUN by either the DSM or by MPIO itself.

### -field DsmName

A string field (of maximum length 63 characters) that returns the friendly name of the controlling DSM for the device.

