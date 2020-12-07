---
UID: NF:ntddndis.NDIS_SWITCH_NIC_AT_ARRAY_INDEX
title: NDIS_SWITCH_NIC_AT_ARRAY_INDEX macro (ntddndis.h)
description: Hyper-V extensible switch extensions use the NDIS_SWITCH_NIC_AT_ARRAY_INDEX macro to access an NDIS_SWITCH_NIC_PARAMETERS element inside an NDIS_SWITCH_NIC_ARRAY structure.
tech.root: netvista
ms.date: 04/17/2018
keywords: ["NDIS_SWITCH_NIC_AT_ARRAY_INDEX macro"]
ms.keywords: NDIS_SWITCH_NIC_AT_ARRAY_INDEX
req.header: ntddndis.h
req.include-header: ndis.h
req.target-type: Desktop
req.target-min-winverclnt: Supported in NDIS 6.30 and later.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.lib: 
req.dll: 
req.irql: 
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
targetos: Windows
f1_keywords:
 - NDIS_SWITCH_NIC_AT_ARRAY_INDEX
 - ntddndis/NDIS_SWITCH_NIC_AT_ARRAY_INDEX
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - ntddndis.h
api_name:
 - NDIS_SWITCH_NIC_AT_ARRAY_INDEX
---

# NDIS_SWITCH_NIC_AT_ARRAY_INDEX macro


## -description

Hyper-V extensible switch extensions use the **NDIS_SWITCH_NIC_AT_ARRAY_INDEX** macro to access an [**NDIS_SWITCH_NIC_PARAMETERS**](ns-ntddndis-_ndis_switch_nic_parameters.md) element inside an [**NDIS_SWITCH_NIC_ARRAY**](ns-ntddndis-_ndis_switch_nic_array.md) structure.

## -parameters

### -param _NicArray_

A pointer to an **NDIS_SWITCH_NIC_ARRAY** structure.

### -param _Index_

A USHORT value that specifies the zero-based index of the **NDIS_SWITCH_NIC_PARAMETERS** element inside the **NDIS_SWITCH_NIC_ARRAY**.

> [!NOTE]
> This value must be less than the value of the **NumElements** member of the **NDIS_SWITCH_NIC_ARRAY** structure.

## -returns

The **NDIS_SWITCH_NIC_AT_ARRAY_INDEX** macro returns a pointer to the specified [**NDIS_SWITCH_NIC_PARAMETERS**](ns-ntddndis-_ndis_switch_nic_parameters.md) element inside the [**NDIS_SWITCH_NIC_ARRAY**](ns-ntddndis-_ndis_switch_nic_array.md).

## -remarks

## -see-also

[**NDIS_SWITCH_NIC_PARAMETERS**](ns-ntddndis-_ndis_switch_nic_parameters.md)

[**NDIS_SWITCH_NIC_ARRAY**](ns-ntddndis-_ndis_switch_nic_array.md)

