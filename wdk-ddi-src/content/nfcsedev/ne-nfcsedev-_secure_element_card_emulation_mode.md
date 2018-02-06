---
UID: NE:nfcsedev._SECURE_ELEMENT_CARD_EMULATION_MODE
title: "_SECURE_ELEMENT_CARD_EMULATION_MODE"
author: windows-driver-content
description: This enumeration indicates the card emulation mode of a secure element.
old-location: nfpdrivers\secure_element_set_card_emulation_mode.htm
old-project: nfpdrivers
ms.assetid: E8A53836-95D1-4CE4-AF55-5AD732211A55
ms.author: windowsdriverdev
ms.date: 12/18/2017
ms.keywords: EmulationOff, *PSECURE_ELEMENT_CARD_EMULATION_MODE, SECURE_ELEMENT_CARD_EMULATION_MODE, nfcsedev/EmulationOnPowerIndependent, nfcsedev/SECURE_ELEMENT_CARD_EMULATION_MODE, nfcsedev/EmulationOnPowerDependent, _SECURE_ELEMENT_CARD_EMULATION_MODE, SECURE_ELEMENT_CARD_EMULATION_MODE enumeration [Near-Field Proximity Drivers], nfpdrivers.secure_element_set_card_emulation_mode, EmulationOnPowerDependent, nfcsedev/EmulationOff, EmulationOnPowerIndependent
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	nfcsedev.h
apiname:
-	SECURE_ELEMENT_CARD_EMULATION_MODE
product: Windows
targetos: Windows
req.typenames: "*PSECURE_ELEMENT_CARD_EMULATION_MODE, SECURE_ELEMENT_CARD_EMULATION_MODE"
---

# _SECURE_ELEMENT_CARD_EMULATION_MODE enumeration


## -description


This enumeration indicates the card emulation mode of a secure element.


## -syntax


````
typedef enum _SECURE_ELEMENT_SET_CARD_EMULATION_MODE { 
  EmulationOff                 = 0,
  EmulationOnPowerIndependent  = 1,
  EmulationOnPowerDependent    = 2
} SECURE_ELEMENT_CARD_EMULATION_MODE;
````


## -enum-fields




### -field EmulationOff

The secure element is not exposed.


### -field EmulationOnPowerIndependent

The eSE secure element is exposed regardless of the power state of the device/battery and is the only secure element exposed. If the battery is removed, the device is powered off or otherwise power is not available. The secure element must remain exposed to the external reader.


### -field EmulationOnPowerDependent

The secure element is exposed only as long as the device is powered on, and is the only secure element exposed. If the battery is removed, the device is powered off, or if power is not available, the secure element must no longer be exposed to the external reader.

