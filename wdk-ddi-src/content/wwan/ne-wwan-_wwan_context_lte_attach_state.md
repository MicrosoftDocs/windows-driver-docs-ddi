---
UID: NE:wwan._WWAN_CONTEXT_LTE_ATTACH_STATE
title: _WWAN_CONTEXT_LTE_ATTACH_STATE (wwan.h)
description: The WWAN_CONTEXT_LTE_ATTACH_STATE enumeration indicates whether a mobile broadband (MBB) device is currently attached to an LTE network or not.
tech.root: netvista
ms.date: 08/23/2018
keywords: ["WWAN_CONTEXT_LTE_ATTACH_STATE enumeration"]
ms.keywords: _WWAN_CONTEXT_LTE_ATTACH_STATE, WWAN_CONTEXT_LTE_ATTACH_STATE, *PWWAN_CONTEXT_LTE_ATTACH_STATE,
req.header: wwan.h
req.include-header: 
req.target-type: 
req.target-min-winverclnt: Windows 10, version 1703
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: 
req.max-support: 
req.typenames: WWAN_CONTEXT_LTE_ATTACH_STATE, *PWWAN_CONTEXT_LTE_ATTACH_STATE
targetos: Windows
ms.custom: RS5
f1_keywords:
 - _WWAN_CONTEXT_LTE_ATTACH_STATE
 - wwan/_WWAN_CONTEXT_LTE_ATTACH_STATE
 - PWWAN_CONTEXT_LTE_ATTACH_STATE
 - wwan/PWWAN_CONTEXT_LTE_ATTACH_STATE
 - WWAN_CONTEXT_LTE_ATTACH_STATE
 - wwan/WWAN_CONTEXT_LTE_ATTACH_STATE
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - wwan.h
api_name:
 - _WWAN_CONTEXT_LTE_ATTACH_STATE
product:
 - Windows
---

# _WWAN_CONTEXT_LTE_ATTACH_STATE enumeration


## -description

The **WWAN_CONTEXT_LTE_ATTACH_STATE** enumeration indicates whether a mobile broadband (MBB) device is currently attached to an LTE network or not.

## -enum-fields

### -field WwanContextLteAttachStateDetached 

The device is not attached to an LTE network.

### -field WwanContextLteAttachStateAttached 

The device is attached to an LTE network.

### -field WwanContextLteAttachStateMaximum 

The maximum value for this enumeration.

## -remarks

This enumeration is used in the [**WWAN_LTE_ATTACH_STATUS**](ns-wwan-_wwan_lte_attach_status.md) structure.

## -see-also

[MB LTE Attach Operations](/windows-hardware/drivers/network/mb-lte-attach-operations)

[**WWAN_LTE_ATTACH_STATUS**](ns-wwan-_wwan_lte_attach_status.md)
