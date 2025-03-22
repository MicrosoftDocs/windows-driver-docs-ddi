---
UID: NS:acpitabl._HMAT_ENTRY
title: HMAT_ENTRY (acpitabl.h)
description: The HMAT_ENTRY structure contains the Heterogeneous Memory Attribute Table (HMAT) information for the table.
ms.date: 09/27/2022
keywords: ["HMAT_ENTRY structure"]
ms.keywords: _HMAT_ENTRY, HMAT_ENTRY, *PHMAT_ENTRY,
req.header: acpitabl.h
req.construct-type: structure
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
targetos: Windows
tech.root: acpi
f1_keywords:
 - _HMAT_ENTRY
 - acpitabl/_HMAT_ENTRY
 - PHMAT_ENTRY
 - acpitabl/PHMAT_ENTRY
 - HMAT_ENTRY
 - acpitabl/HMAT_ENTRY
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - acpitabl.h
api_name:
 - _HMAT_ENTRY
 - PHMAT_ENTRY
 - HMAT_ENTRY
---

# HMAT_ENTRY structure (acpitabl.h)

## -description

The **HMAT_ENTRY** structure contains the Heterogeneous Memory Attribute Table (HMAT) information for the table. The structure can contain one of three HMAT types: Memory Subsystem Address Range (MSAR), System Locality Latency and Bandwidth Information (SLLBI), or Memory Side Cache Information (MSCI).

## -struct-fields

### -field Type

A **USHORT** value containing the HMAT table type.

### -field Reserved

Reserved for future use.

### -field Length

A **ULONG** value containing the size of the table.

### -field DUMMYUNIONNAME

Defines the **DUMMYUNIONNAME** union.

### -field DUMMYUNIONNAME.Msar

Defines the **Msar** structure.

### -field DUMMYUNIONNAME.Msar.Flags

Defines the **Flags** union.

### -field DUMMYUNIONNAME.Msar.Flags.DUMMYSTRUCTNAME

Defines the **DUMMYSTRUCTNAME** structure.

### -field DUMMYUNIONNAME.Msar.Flags.DUMMYSTRUCTNAME.ProcessorProximityDomainValid

Defines the **USHORT** member **ProcessorProximityDomainValid**.

### -field DUMMYUNIONNAME.Msar.Flags.DUMMYSTRUCTNAME.Reserved0

Reserved for future use.

### -field DUMMYUNIONNAME.Msar.Flags.DUMMYSTRUCTNAME.Reserved1

Reserved for future use.

### -field DUMMYUNIONNAME.Msar.Flags.DUMMYSTRUCTNAME.Reserved

Reserved for future use.

### -field DUMMYUNIONNAME.Msar.Flags.AsUSHort

Defines the **USHORT** member **AsUSHort**.

### -field DUMMYUNIONNAME.Msar.Reserved1

Reserved for future use.

### -field DUMMYUNIONNAME.Msar.ProcessorProximityDomain

Defines the **ULONG** member **ProcessorProximityDomain**.

### -field DUMMYUNIONNAME.Msar.MemoryProximityDomain

Defines the **ULONG** member **MemoryProximityDomain**.

### -field DUMMYUNIONNAME.Msar.Reserved2

Reserved for future use.

### -field DUMMYUNIONNAME.Msar.Reserved3

Reserved for future use.

### -field DUMMYUNIONNAME.Msar.Reserved4

Reserved for future use.

### -field DUMMYUNIONNAME.Sllbi

Defines the **Sllbi** union.

### -field DUMMYUNIONNAME.Sllbi.Flags

Defines the **Flags** union.

### -field DUMMYUNIONNAME.Sllbi.Flags.DUMMYSTRUCTNAME

Defines the **DUMMYSTRUCTNAME** structure.

### -field DUMMYUNIONNAME.Sllbi.Flags.DUMMYSTRUCTNAME.MemoryHierarchy

Defines the **UCHAR** member **MemoryHierarchy**.

### -field DUMMYUNIONNAME.Sllbi.Flags.DUMMYSTRUCTNAME.MinTransferSizeToAchieveValues

Defines the **UCHAR** member **MinTransferSizeToAchieveValues**.

### -field DUMMYUNIONNAME.Sllbi.Flags.DUMMYSTRUCTNAME.NonSequentialTransfers

Defines the **UCHAR** member **NonSequentialTransfers**.

### -field DUMMYUNIONNAME.Sllbi.Flags.DUMMYSTRUCTNAME.Reserved

Reserved for future use.

### -field DUMMYUNIONNAME.Sllbi.Flags.AsUChar

Defines the **UCHAR** member **AsUChar**.

### -field DUMMYUNIONNAME.Sllbi.DataType

Defines the **UCHAR** member **DataType**.

### -field DUMMYUNIONNAME.Sllbi.MinTransferSize

Defines the **UCHAR** member **MinTransferSize**.

### -field DUMMYUNIONNAME.Sllbi.Reserved1

Reserved for future use.

### -field DUMMYUNIONNAME.Sllbi.NumberOfInitiatorProximityDomains

Defines the **ULONG** member **NumberOfInitiatorProximityDomains**.

### -field DUMMYUNIONNAME.Sllbi.NumberOfTargetProximityDomains

Defines the **ULONG** member **NumberOfTargetProximityDomains**.

### -field DUMMYUNIONNAME.Sllbi.Reserved2

Reserved for future use.

### -field DUMMYUNIONNAME.Sllbi.EntryBaseUnit

Defines the **ULONGLONG** member **EntryBaseUnit**.

### -field DUMMYUNIONNAME.Msci

Defines the **Msci** union.

### -field DUMMYUNIONNAME.Msci.MemoryProximityDomain

Defines the **ULONG** member **MemoryProximityDomain**.

### -field DUMMYUNIONNAME.Msci.Reserved1

Reserved for future use.

### -field DUMMYUNIONNAME.Msci.MemorySideCacheSize

Defines the **ULONGLONG** member **MemorySideCacheSize**.

### -field DUMMYUNIONNAME.Msci.CacheAttributes

Defines the **CacheAttributes** union.

### -field DUMMYUNIONNAME.Msci.CacheAttributes.DUMMYSTRUCTNAME

Defines the **DUMMYSTRUCTNAME** structure.

### -field DUMMYUNIONNAME.Msci.CacheAttributes.DUMMYSTRUCTNAME.TotalCacheLevels

Defines the **ULONG** member **TotalCacheLevels**.

### -field DUMMYUNIONNAME.Msci.CacheAttributes.DUMMYSTRUCTNAME.CacheLevel

Defines the **ULONG** member **CacheLevel**.

### -field DUMMYUNIONNAME.Msci.CacheAttributes.DUMMYSTRUCTNAME.CacheAssociativity

Defines the ULONG member CacheAssociativity.

### -field DUMMYUNIONNAME.Msci.CacheAttributes.DUMMYSTRUCTNAME.WritePolicy

Defines the **ULONG** member **WritePolicy**.

### -field DUMMYUNIONNAME.Msci.CacheAttributes.DUMMYSTRUCTNAME.CacheLineSize

Defines the **ULONG** member **CacheLineSize**.

### -field DUMMYUNIONNAME.Msci.CacheAttributes.AsULong

Defines the **ULONG** member **AsULong**.

### -field DUMMYUNIONNAME.Msci.Reserved2

Reserved for future use.

### -field DUMMYUNIONNAME.Msci.NumberOfSmBiosHandles

Defines the **USHORT** member **NumberOfSmBiosHandles**.

## -remarks

## -see-also
