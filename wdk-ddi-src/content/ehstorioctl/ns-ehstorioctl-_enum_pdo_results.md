---
UID: NS:ehstorioctl._ENUM_PDO_RESULTS
title: _ENUM_PDO_RESULTS (ehstorioctl.h)
description: This structure describes a result set of Physical Device Objects (PDOs) that are enumerated with IOCTL_EHSTOR_DEVICE_ENUMERATE_PDOS.
old-location: storage\enum_pdo_results.htm
tech.root: storage
ms.assetid: 80553c9e-3e80-4219-8cc0-2bd4dd6fa76b
ms.date: 03/29/2018
ms.keywords: "*PENUM_PDO_RESULTS, ENUM_PDO_RESULTS, ENUM_PDO_RESULTS structure [Storage Devices], PENUM_PDO_RESULTS, PENUM_PDO_RESULTS structure pointer [Storage Devices], _ENUM_PDO_RESULTS, ehstorioctl/ENUM_PDO_RESULTS, ehstorioctl/PENUM_PDO_RESULTS, storage.enum_pdo_results, structs-silo_45277a1e-1ca6-4bce-a952-b26860796f51.xml"
f1_keywords:
 - "ehstorioctl/ENUM_PDO_RESULTS"
req.header: ehstorioctl.h
req.include-header: EhStorIoctl.h
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
- EhStorIoctl.h
api_name:
- ENUM_PDO_RESULTS
product:
- Windows
targetos: Windows
req.typenames: ENUM_PDO_RESULTS, *PENUM_PDO_RESULTS
---

# _ENUM_PDO_RESULTS structure


## -description


This structure describes a result set of Physical Device Objects (PDOs) that are enumerated with <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ehstorioctl/ni-ehstorioctl-ioctl_ehstor_device_enumerate_pdos">IOCTL_EHSTOR_DEVICE_ENUMERATE_PDOS</a>.


## -struct-fields




### -field cEntries

This member indicates the number of entries in the array of ENUM_PDO_ENTRY structures.


### -field rgEntries

This member contains the array of ENUM_PDO_ENTRY structures.


## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ehstorioctl/ni-ehstorioctl-ioctl_ehstor_device_enumerate_pdos">IOCTL_EHSTOR_DEVICE_ENUMERATE_PDOS</a>
 

 

