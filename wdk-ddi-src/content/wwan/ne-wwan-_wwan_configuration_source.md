---
UID: NE:wwan._WWAN_CONFIGURATION_SOURCE
title: _WWAN_CONFIGURATION_SOURCE (wwan.h)
description: The WWAN_CONFIGURATION_SOURCE enumeration specifies the creation source of a provisioned context.
tech.root: netvista
ms.date: 08/23/2018
keywords: ["WWAN_CONFIGURATION_SOURCE enumeration"]
ms.keywords: _WWAN_CONFIGURATION_SOURCE, WWAN_CONFIGURATION_SOURCE, *PWWAN_CONFIGURATION_SOURCE,
req.header: wwan.h
req.include-header: 
req.target-type: 
req.target-min-winverclnt: Windows 10, version 1703
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: 
req.max-support: 
req.typenames: WWAN_CONFIGURATION_SOURCE, *PWWAN_CONFIGURATION_SOURCE
targetos: Windows
ms.custom: RS5
f1_keywords:
 - _WWAN_CONFIGURATION_SOURCE
 - wwan/_WWAN_CONFIGURATION_SOURCE
 - PWWAN_CONFIGURATION_SOURCE
 - wwan/PWWAN_CONFIGURATION_SOURCE
 - WWAN_CONFIGURATION_SOURCE
 - wwan/WWAN_CONFIGURATION_SOURCE
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - wwan.h
api_name:
 - _WWAN_CONFIGURATION_SOURCE
 - PWWAN_CONFIGURATION_SOURCE
 - WWAN_CONFIGURATION_SOURCE
product:
 - Windows
---

# _WWAN_CONFIGURATION_SOURCE enumeration


## -description

The **WWAN_CONFIGURATION_SOURCE** enumeration specifies the creation source of a provisioned context.

## -enum-fields

### -field WwanUserProvisioned 

The context was created by an end user through the OS settings.

### -field WwanAdminProvisioned 

The context was created by an enterprise IT admin from the OS.

### -field WwanOperatorProvisioned 

The context was created by the mobile operator through OMA-DM or other channels.

### -field WwanDeviceProvisioned 

The context was created by the OS APN database.

### -field WwanModemProvisioned 

The context was created by the IHV or OEM.

### -field WwanMaxProvisionSource 

The maximum value for this enumeration.

## -remarks

This enum is used in the [**WWAN_CONTEXT_V2**](ns-wwan-_wwan_context_v2.md) and [**WWAN_SET_CONTEXT_V2**](ns-wwan-_wwan_set_context_v2.md) structures.

## -see-also

[**WWAN_CONTEXT_V2**](ns-wwan-_wwan_context_v2.md)

[**WWAN_SET_CONTEXT_V2**](ns-wwan-_wwan_set_context_v2.md)

