---
UID: NS:acpitabl._PROC_TOPOLOGY_NODE
tech.root: acpi
title: PROC_TOPOLOGY_NODE (acpitabl.h)
ms.date: 03/01/2022
targetos: Windows
description: Defines the processor topology node structure.
prerelease: false
req.construct-type: structure
req.ddi-compliance: 
req.dll: 
req.header: acpitabl.h
req.include-header: Acpitabl.h
req.kmdf-ver: 
req.lib: 
req.max-support: 
req.redist: 
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.target-type: Windows
req.typenames: PROC_TOPOLOGY_NODE, *PPROC_TOPOLOGY_NODE
req.umdf-ver: 
req.unicode-ansi: 
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - acpitabl.h
api_name:
 - _PROC_TOPOLOGY_NODE
 - PPROC_TOPOLOGY_NODE
 - PROC_TOPOLOGY_NODE
f1_keywords:
 - _PROC_TOPOLOGY_NODE
 - acpitabl/_PROC_TOPOLOGY_NODE
 - PPROC_TOPOLOGY_NODE
 - acpitabl/PPROC_TOPOLOGY_NODE
 - PROC_TOPOLOGY_NODE
 - acpitabl/PROC_TOPOLOGY_NODE
dev_langs:
 - c++
helpviewer_keywords:
 - _PROC_TOPOLOGY_NODE
---

## -description

Defines the processor topology node structure.

## -struct-fields

### -field Type

Defines the **UCHAR** member **Type**.

### -field Length

Defines the **UCHAR** member **Length**.

### -field Reserved

Reserved for future use.

### -field HierarchyNode

Defines the **HierarchyNode** member structure.

### -field HierarchyNode.Flags

Defines the **PROC_TOPOLOGY_NODE_FLAGS** member **Flags**.

### -field HierarchyNode.Parent

Defines the **ULONG** member **Parent**.

### -field HierarchyNode.ACPIProcessorId

Defines the **ULONG** member **ACPIProcessorId**.

### -field HierarchyNode.NumberPrivateResources

Defines the **ULONG** member **NumberPrivateResources**.

### -field HierarchyNode.PrivateResources

Defines the **ULONG** member **PrivateResources**.

### -field CacheNode

Defines the **CacheNode** member structure.

### -field CacheNode.Flags

Defines the **PROC_TOPOLOGY_CACHE_FLAGS** member Flags.

### -field CacheNode.NextLevelCacheOffset

Defines the ULONG member NextLevelCacheOffset.

### -field CacheNode.Size

Defines the ULONG member Size.

### -field CacheNode.Sets

Defines the ULONG member Sets.

### -field CacheNode.Associativity

Defines the UCHAR member Associativity.

### -field CacheNode.Attributes

Defines the PROC_TOPOLOGY_CACHE_ATTRIBUTES member Attributes.

### -field CacheNode.LineSize

Defines the USHORT member LineSize.

### -field IdNode

Defines the **IdNode** member structure.

### -field IdNode.Vendor

Defines the **ULONG** member **Vendor**.

### -field IdNode.Level1

Defines the **ULONG64** member **Level1**.

### -field IdNode.Level2

Defines the **ULONG64** member **Level2**.

### -field IdNode.Major

Defines the **USHORT** member **Major**.

### -field IdNode.Minor

Defines the **USHORT** member **Minor**.

### -field IdNode.Spin

Defines the **USHORT** member **Spin**.

## -remarks

## -see-also
