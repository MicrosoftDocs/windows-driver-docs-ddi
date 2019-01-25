---
UID: NE:wwan._WWAN_CONTEXT_LTE_ATTACH_ROAMING_CONTROL
title: _WWAN_CONTEXT_LTE_ATTACH_ROAMING_CONTROL (wwan.h)
description: The WWAN_CONTEXT_LTE_ATTACH_ROAMING_CONTROL enumeration specifies which roaming conditions apply to an LTE attach context in a mobile broadband (MBB) modem.
tech.root: netvista
ms.assetid: 1cd9acca-881e-4b93-a108-9b9376b5d7a1
ms.date: 08/22/2018
ms.topic: enum
ms.keywords: _WWAN_CONTEXT_LTE_ATTACH_ROAMING_CONTROL, WWAN_CONTEXT_LTE_ATTACH_ROAMING_CONTROL, *PWWAN_CONTEXT_LTE_ATTACH_ROAMING_CONTROL, 
req.header: wwan.h
req.include-header:
req.target-type:
req.target-min-winverclnt: Windows 10, version 1703
req.target-min-winversvr:
req.kmdf-ver:
req.umdf-ver:
req.ddi-compliance:
req.max-support:
req.typenames: WWAN_CONTEXT_LTE_ATTACH_ROAMING_CONTROL, *PWWAN_CONTEXT_LTE_ATTACH_ROAMING_CONTROL
topic_type: 
-	apiref
api_type: 
-	HeaderDef
api_location: 
-	wwan.h
api_name: 
-	_WWAN_CONTEXT_LTE_ATTACH_ROAMING_CONTROL
product: 
- Windows
targetos: Windows
ms.custom: RS5
---

# _WWAN_CONTEXT_LTE_ATTACH_ROAMING_CONTROL enumeration

## -description

The **WWAN_CONTEXT_LTE_ATTACH_ROAMING_CONTROL** enumeration specifies which roaming conditions apply to an LTE attach context in a mobile broadband (MBB) modem.

## -enum-fields

### -field WwanContextLteAttachRoamingControlHome 

Indicates whether this context is allowed to be used on the home network.

### -field WwanContextLteAttachRoamingControlPartner 

Indicates whether this context is allowed to be used on partner roaming networks.

### -field WwanContextLteAttachRoamingControlNonPartner 

Indicates whether this context is allowed to be used on non-partner roaming networks.

### -field WwanContextLteAttachRoamingControlMaximum 

The maximum value for this enumeration.

## -remarks

## -see-also

[MB LTE Attach Operations](https://docs.microsoft.com/windows-hardware/drivers/network/mb-lte-attach-operations)
