---
UID: NS:storport._MEMORY_REGION
title: _MEMORY_REGION (storport.h)
description: The MEMORY_REGION structure describes a region of physically contiguous memory.
old-location: storage\memory_region.htm
tech.root: storage
ms.assetid: b8dbc3d4-7a70-4ec6-b7b0-2b0877fb9722
ms.date: 03/29/2018
keywords: ["_MEMORY_REGION structure"]
ms.keywords: "*PMEMORY_REGION, MEMORY_REGION, MEMORY_REGION structure [Storage Devices], PMEMORY_REGION, PMEMORY_REGION structure pointer [Storage Devices], _MEMORY_REGION, storage.memory_region, storport/MEMORY_REGION, storport/PMEMORY_REGION, structs-storport_4ed10515-f1ce-4767-bbdc-239ac00a5cbe.xml"
f1_keywords:
 - "storport/MEMORY_REGION"
 - "MEMORY_REGION"
req.header: storport.h
req.include-header: Storport.h
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
- storport.h
api_name:
- MEMORY_REGION
targetos: Windows
req.typenames: MEMORY_REGION, *PMEMORY_REGION
---

# _MEMORY_REGION structure

## -description

The MEMORY_REGION structure describes a region of physically contiguous memory.

## -struct-fields

### -field VirtualBase

The beginning virtual address of the memory region.

### -field PhysicalBase

The beginning physical address of the memory region.

### -field Length

The size, in bytes, of the memory region.

## -remarks

The **DumpRegion** member of the [**PORT_CONFIGURATION_INFORMATION**](ns-storport-_port_configuration_information.md) structure holds a MEMORY_REGION structure that describes a region of physically contiguous memory that a miniport driver can use during a crash dump.

## -see-also

[**PORT_CONFIGURATION_INFORMATION**](ns-storport-_port_configuration_information.md)
