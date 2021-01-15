---
UID: NE:nfcsedev._SECURE_ELEMENT_CARD_EMULATION_MODE
title: _SECURE_ELEMENT_CARD_EMULATION_MODE (nfcsedev.h)
description: This enumeration indicates the card emulation mode of a secure element.
old-location: nfpdrivers\secure_element_set_card_emulation_mode.htm
tech.root: nfpdrivers
ms.date: 02/15/2018
keywords: ["SECURE_ELEMENT_CARD_EMULATION_MODE enumeration"]
ms.keywords: "*PSECURE_ELEMENT_CARD_EMULATION_MODE, EmulationOff, EmulationOnPowerDependent, EmulationOnPowerIndependent, SECURE_ELEMENT_CARD_EMULATION_MODE, SECURE_ELEMENT_CARD_EMULATION_MODE enumeration [Near-Field Proximity Drivers], _SECURE_ELEMENT_CARD_EMULATION_MODE, nfcsedev/EmulationOff, nfcsedev/EmulationOnPowerDependent, nfcsedev/EmulationOnPowerIndependent, nfcsedev/SECURE_ELEMENT_CARD_EMULATION_MODE, nfpdrivers.secure_element_set_card_emulation_mode"
req.header: nfcsedev.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: 
targetos: Windows
req.typenames: SECURE_ELEMENT_CARD_EMULATION_MODE, *PSECURE_ELEMENT_CARD_EMULATION_MODE
f1_keywords:
 - _SECURE_ELEMENT_CARD_EMULATION_MODE
 - nfcsedev/_SECURE_ELEMENT_CARD_EMULATION_MODE
 - PSECURE_ELEMENT_CARD_EMULATION_MODE
 - nfcsedev/PSECURE_ELEMENT_CARD_EMULATION_MODE
 - SECURE_ELEMENT_CARD_EMULATION_MODE
 - nfcsedev/SECURE_ELEMENT_CARD_EMULATION_MODE
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - nfcsedev.h
api_name:
 - _SECURE_ELEMENT_CARD_EMULATION_MODE
 - PSECURE_ELEMENT_CARD_EMULATION_MODE
 - SECURE_ELEMENT_CARD_EMULATION_MODE
---

# _SECURE_ELEMENT_CARD_EMULATION_MODE enumeration


## -description

This enumeration indicates the card emulation mode of a secure element.

## -enum-fields

### -field EmulationOff

The secure element is not exposed.

### -field EmulationOnPowerIndependent

The eSE secure element is exposed regardless of the power state of the device/battery and is the only secure element exposed. If the battery is removed, the device is powered off or otherwise power is not available. The secure element must remain exposed to the external reader.

### -field EmulationOnPowerDependent

The secure element is exposed only as long as the device is powered on, and is the only secure element exposed. If the battery is removed, the device is powered off, or if power is not available, the secure element must no longer be exposed to the external reader.

