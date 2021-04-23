---
UID: NS:wwan._WWAN_NR_NEIGHBOR_CELLS_INFO
tech.root: netvista
title: WWAN_NR_NEIGHBOR_CELLS_INFO
ms.date: 05/13/2021
ms.topic: language-reference
targetos: Windows
description: 
req.construct-type: structure
req.ddi-compliance: 
req.dll: 
req.header: wwan.h
req.include-header: 
req.kmdf-ver: 
req.lib: 
req.max-support: 
req.redist: 
req.target-min-winverclnt: 
req.target-min-winversvr: Windows Server 2022
req.target-type: 
req.typenames: WWAN_NR_NEIGHBOR_CELLS_INFO, *PWWAN_NR_NEIGHBOR_CELLS_INFO
req.umdf-ver: 
req.unicode-ansi: 
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - wwan.h
api_name:
 - _WWAN_NR_NEIGHBOR_CELLS_INFO
 - PWWAN_NR_NEIGHBOR_CELLS_INFO
 - WWAN_NR_NEIGHBOR_CELLS_INFO
f1_keywords:
 - _WWAN_NR_NEIGHBOR_CELLS_INFO
 - wwan/_WWAN_NR_NEIGHBOR_CELLS_INFO
 - PWWAN_NR_NEIGHBOR_CELLS_INFO
 - wwan/PWWAN_NR_NEIGHBOR_CELLS_INFO
 - WWAN_NR_NEIGHBOR_CELLS_INFO
 - wwan/WWAN_NR_NEIGHBOR_CELLS_INFO
dev_langs:
 - c++
---

## -description

The **WWAN_NR_NEIGHBOR_CELLS_INFO** structure represents information about the NR neighbor cells.

## -struct-fields

### -field SystemSubType

Indicates the system type for which a neighbor cell information is valid. This is applicable for indicating whether a neighbor cell is either an NR or EUTRA cell corresponding to the WWAN data subclasses. For a detailed list of values, see the **dataSubclass** member of [**IS_5G_5GC_PRESENT**](nf-wwan-is_5g_5gc_present.md). 

### -field ProviderIdOffset

The offset in bytes, calculated from the beginning of this structure, to a numeric (0-9) string called *ProviderId* that represents the network provider identity. This string is a concatenation of a three-digit Mobile Country Code (MCC) and a two or three-digit Mobile Network Code (MNC). This member can be NULL when no *ProviderId* information is returned.

### -field ProviderIdSize

The size, in bytes, used for *ProviderId*.

### -field CellIDOffset

The offset of the CellID in bytes, calculated from beginning of structure. This member can be NULL when no CellID information is available.

### -field CellIDSize

The size used for the CellID.

### -field PhysicalCellID

The pysical Cell ID (0..1007). Use 0xFFFFFFFF when this information is not available

### -field TAC

### -field RSRP

### -field RSRQ

### -field SINR

### -field Data

## -remarks

## -see-also

