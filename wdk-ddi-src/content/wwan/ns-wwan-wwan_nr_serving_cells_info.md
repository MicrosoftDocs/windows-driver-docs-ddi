---
UID: NS:wwan._WWAN_NR_SERVING_CELLS_INFO
tech.root: netvista
title: WWAN_NR_SERVING_CELLS_INFO
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
req.typenames: WWAN_NR_SERVING_CELLS_INFO, *PWWAN_NR_SERVING_CELLS_INFO
req.umdf-ver: 
req.unicode-ansi: 
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - wwan.h
api_name:
 - _WWAN_NR_SERVING_CELLS_INFO
 - PWWAN_NR_SERVING_CELLS_INFO
 - WWAN_NR_SERVING_CELLS_INFO
f1_keywords:
 - _WWAN_NR_SERVING_CELLS_INFO
 - wwan/_WWAN_NR_SERVING_CELLS_INFO
 - PWWAN_NR_SERVING_CELLS_INFO
 - wwan/PWWAN_NR_SERVING_CELLS_INFO
 - WWAN_NR_SERVING_CELLS_INFO
 - wwan/WWAN_NR_SERVING_CELLS_INFO
dev_langs:
 - c++
---

## -description

## -struct-fields

### -field ProviderIdOffset

The offset in bytes, calculated from the beginning of this structure, to a numeric (0-9) string called *ProviderId* that represents the network provider identity. This string is a concatenation of a three-digit Mobile Country Code (MCC) and a two or three-digit Mobile Network Code (MNC). This member can be NULL when no *ProviderId* information is returned.

### -field ProviderIdSize

The size, in bytes, used for *ProviderId*.

### -field NCI

### -field PhysicalCellID

### -field NRARFCN

### -field TAC

### -field RSRP

### -field RSRQ

### -field SINR

### -field NTimingAdvanceOffset

### -field Data

## -remarks

## -see-also

