---
UID: NS:wwan._WWAN_NR_NEIGHBOR_CELLS
tech.root: netvista
title: WWAN_NR_NEIGHBOR_CELLS
ms.date: 05/13/2021
ms.topic: language-reference
targetos: Windows
description: The WWAN_NR_NEIGHBOR_CELLS structure represents the measured results list of neighboring NR cells.
req.construct-type: structure
req.ddi-compliance: 
req.dll: 
req.header: wwan.h
req.include-header: 
req.kmdf-ver: 
req.lib: 
req.max-support: 
req.redist: 
req.target-min-winverclnt: Windows 11
req.target-min-winversvr: Windows Server 2022
req.target-type: 
req.typenames: WWAN_NR_NEIGHBOR_CELLS, *PWWAN_NR_NEIGHBOR_CELLS
req.umdf-ver: 
req.unicode-ansi: 
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - wwan.h
api_name:
 - _WWAN_NR_NEIGHBOR_CELLS
 - PWWAN_NR_NEIGHBOR_CELLS
 - WWAN_NR_NEIGHBOR_CELLS
f1_keywords:
 - _WWAN_NR_NEIGHBOR_CELLS
 - wwan/_WWAN_NR_NEIGHBOR_CELLS
 - PWWAN_NR_NEIGHBOR_CELLS
 - wwan/PWWAN_NR_NEIGHBOR_CELLS
 - WWAN_NR_NEIGHBOR_CELLS
 - wwan/WWAN_NR_NEIGHBOR_CELLS
dev_langs:
 - c++
---

## -description

The **WWAN_NR_NEIGHBOR_CELLS** structure represents the measured results list of neighboring NR cells.

## -struct-fields

### -field ElementCount

The count of neighbor cell entries following this element, with a maximum of 8 best NR or EUTRA neighbor cells.

### -field NRNeighborCells

The array of NR neighbor cell records, each specified as a [**WWAN_NR_NEIGHBOR_CELLS_INFO**](ns-wwan-wwan_nr_neighbor_cells_info.md) structure.

## -remarks

## -see-also

[**WWAN_BASE_STATIONS_INFO**](ns-wwan-_wwan_base_stations_info.md)

[**WWAN_NR_NEIGHBOR_CELLS_INFO**](ns-wwan-wwan_nr_neighbor_cells_info.md)

[**WWAN_NR_SERVING_CELLS**](ns-wwan-wwan_nr_serving_cells.md)

[**WWAN_NR_SERVING_CELLS_INFO**](ns-wwan-wwan_nr_serving_cells_info.md)