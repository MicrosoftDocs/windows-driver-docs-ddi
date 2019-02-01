---
UID: NS:acpitabl._HMAT_ENTRY
title: _HMAT_ENTRY (acpitabl.h)
description: The HMAT_ENTRY structure contains the Heterogeneous Memory Attribute Table (HMAT) information for the table.
ms.assetid: e37fa3c2-99c2-478f-9d00-3bba73cbc7d5
ms.date: 09/28/2018
ms.topic: struct
ms.keywords: _HMAT_ENTRY, HMAT_ENTRY, *PHMAT_ENTRY, 
req.header: acpitabl.h
req.include-header:
req.target-type:
req.target-min-winverclnt:
req.target-min-winversvr:
req.kmdf-ver:
req.umdf-ver:
req.lib:
req.dll:
req.ddi-compliance:
req.unicode-ansi:
req.max-support:
req.typenames: HMAT_ENTRY, *PHMAT_ENTRY
topic_type: 
-	apiref
api_type: 
-	HeaderDef
api_location: 
-	acpitabl.h
api_name: 
-	_HMAT_ENTRY
product:
-	Windows
targetos: Windows
ms.custom: RS5
---

# _HMAT_ENTRY structure

## -description

The HMAT_ENTRY structure contains the Heterogeneous Memory Attribute Table (HMAT) information for the table. The structure can contain one of three HMAT types: Memory Subsystem Address Range (MSAR), System Locality Latency and Bandwidth Information (SLLBI), or Memory Side Cache Information (MSCI).

## -struct-fields

### -field Type

A USHORT value containing the HMAT table type.
 
### -field Reserved

Reserved for future use.

### -field Length

A ULONG value containing the size of the table.
 
### -field DUMMYUNIONNAME
 
### -field DUMMYUNIONNAME.Msar
 
### -field DUMMYUNIONNAME.Msar.Flags
 
### -field DUMMYUNIONNAME.Msar.Flags.DUMMYSTRUCTNAME
 
### -field DUMMYUNIONNAME.Msar.Flags.DUMMYSTRUCTNAME.ProcessorProximityDomainValid
 
### -field DUMMYUNIONNAME.Msar.Flags.DUMMYSTRUCTNAME.MemoryProximityDomainValid
 
### -field DUMMYUNIONNAME.Msar.Flags.DUMMYSTRUCTNAME.ReservationHint
 
### -field DUMMYUNIONNAME.Msar.Flags.DUMMYSTRUCTNAME.Reserved
 
### -field DUMMYUNIONNAME.Msar.Flags.AsUSHort
 
### -field DUMMYUNIONNAME.Msar.Reserved1
 
### -field DUMMYUNIONNAME.Msar.ProcessorProximityDomain
 
### -field DUMMYUNIONNAME.Msar.MemoryProximityDomain
 
### -field DUMMYUNIONNAME.Msar.Reserved2
 
### -field DUMMYUNIONNAME.Msar.SystemPhysicalAddressRangeBase
 
### -field DUMMYUNIONNAME.Msar.SystemPhysicalAddressRangeLength
 
### -field DUMMYUNIONNAME.Sllbi
 
### -field DUMMYUNIONNAME.Sllbi.Flags
 
### -field DUMMYUNIONNAME.Sllbi.Flags.DUMMYSTRUCTNAME
 
### -field DUMMYUNIONNAME.Sllbi.Flags.DUMMYSTRUCTNAME.Memory
 
### -field DUMMYUNIONNAME.Sllbi.Flags.DUMMYSTRUCTNAME.LastLevelMemory
 
### -field DUMMYUNIONNAME.Sllbi.Flags.DUMMYSTRUCTNAME.FirstLevelMemorySideCache
 
### -field DUMMYUNIONNAME.Sllbi.Flags.DUMMYSTRUCTNAME.SecondLevelMemorySideCache
 
### -field DUMMYUNIONNAME.Sllbi.Flags.DUMMYSTRUCTNAME.ThirdLevelMemorySideCache
 
### -field DUMMYUNIONNAME.Sllbi.Flags.DUMMYSTRUCTNAME.Reserved
 
### -field DUMMYUNIONNAME.Sllbi.Flags.AsUChar
 
### -field DUMMYUNIONNAME.Sllbi.DataType
 
### -field DUMMYUNIONNAME.Sllbi.Reserved1
 
### -field DUMMYUNIONNAME.Sllbi.NumberOfInitiatorProximityDomains
 
### -field DUMMYUNIONNAME.Sllbi.NumberOfTargetProximityDomains
 
### -field DUMMYUNIONNAME.Sllbi.Reserved2
 
### -field DUMMYUNIONNAME.Sllbi.EntryBaseUnit
 
### -field DUMMYUNIONNAME.Msci
 
### -field DUMMYUNIONNAME.Msci.MemoryProximityDomain
 
### -field DUMMYUNIONNAME.Msci.Reserved1
 
### -field DUMMYUNIONNAME.Msci.MemorySideCacheSize
 
### -field DUMMYUNIONNAME.Msci.CacheAttributes
 
### -field DUMMYUNIONNAME.Msci.CacheAttributes.DUMMYSTRUCTNAME
 
### -field DUMMYUNIONNAME.Msci.CacheAttributes.DUMMYSTRUCTNAME.TotalCacheLevels
 
### -field DUMMYUNIONNAME.Msci.CacheAttributes.DUMMYSTRUCTNAME.CacheLevel
 
### -field DUMMYUNIONNAME.Msci.CacheAttributes.DUMMYSTRUCTNAME.CacheAssociativity
 
### -field DUMMYUNIONNAME.Msci.CacheAttributes.DUMMYSTRUCTNAME.WritePolicy
 
### -field DUMMYUNIONNAME.Msci.CacheAttributes.DUMMYSTRUCTNAME.CacheLineSize
 
### -field DUMMYUNIONNAME.Msci.CacheAttributes.AsULong
 
### -field DUMMYUNIONNAME.Msci.Reserved2
 
### -field DUMMYUNIONNAME.Msci.NumberOfSmBiosHandles
 

## -remarks

## -see-also
