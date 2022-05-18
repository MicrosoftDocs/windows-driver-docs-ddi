---
UID: NE:wwan._WWAN_ACTIVATION_OPTION
tech.root: netvista
title: WWAN_ACTIVATION_OPTION
ms.date: 01/12/2022
targetos: Windows
description: The WWAN_ACTIVATION_OPTION enum lists the Packet Data Protocol (PDP) activation options that the MB device supports.
prerelease: true
req.construct-type: enumeration
req.ddi-compliance: 
req.header: wwan.h
req.include-header: 
req.kmdf-ver: 
req.max-support: 
req.target-min-winverclnt: Windows 11, version 22H2
req.target-min-winversvr: 
req.target-type: 
req.typenames: 
req.umdf-ver: 
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - wwan.h
api_name:
 - _WWAN_ACTIVATION_OPTION
 - PWWAN_ACTIVATION_OPTION
 - WWAN_ACTIVATION_OPTION
f1_keywords:
 - _WWAN_ACTIVATION_OPTION
 - wwan/_WWAN_ACTIVATION_OPTION
 - PWWAN_ACTIVATION_OPTION
 - wwan/PWWAN_ACTIVATION_OPTION
 - WWAN_ACTIVATION_OPTION
 - wwan/WWAN_ACTIVATION_OPTION
dev_langs:
 - c++
helpviewer_keywords:
 - _WWAN_ACTIVATION_OPTION
---

## -description

The **WWAN_ACTIVATION_OPTION** enumeration lists the Packet Data Protocol (PDP) activation options that the MB device supports.

## -enum-fields

### -field WwanActivationOptionDefault:0

All PDU session attributes for activation are provided.

### -field WwanActivationOptionPerNonDefaultURSPRules:1

Use matching non-default URSP rules to activate.

### -field WwanActivationOptionPerDefaultURSPRule:2

Use the default URSP rule to activate.

### -field WwanActivationOptionPerURSPRules:3

Use matching non-default URSPs rules and the default URSP rule to activate.

### -field WwanActivationOptionMax:4

The total number of supported activation options.

## -remarks

## -see-also

