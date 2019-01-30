---
UID: NS:nfcsedev._SECURE_ELEMENT_SET_CARD_EMULATION_MODE_INFO
title: "_SECURE_ELEMENT_SET_CARD_EMULATION_MODE_INFO" (nfcsedev.h)
description: SECURE_ELEMENT_SET_CARD_EMULATION_MODE_INFO is the input parameter for IOCTL_NFCSE_SET_CARD_EMULATION_MODE.
old-location: nfpdrivers\secure_element_set_card_emulation_mode_info.htm
tech.root: nfpdrivers
ms.assetid: 64EE1896-DD19-42AD-92D7-3B3498A83E75
ms.date: 02/15/2018
ms.keywords: "*PSECURE_ELEMENT_SET_CARD_EMULATION_MODE_INFO, PSECURE_ELEMENT_SET_CARD_EMULATION_MODE_INFO, PSECURE_ELEMENT_SET_CARD_EMULATION_MODE_INFO structure pointer [Near-Field Proximity Drivers], SECURE_ELEMENT_SET_CARD_EMULATION_MODE_INFO, SECURE_ELEMENT_SET_CARD_EMULATION_MODE_INFO structure [Near-Field Proximity Drivers], _SECURE_ELEMENT_SET_CARD_EMULATION_MODE_INFO, nfcsedev/PSECURE_ELEMENT_SET_CARD_EMULATION_MODE_INFO, nfcsedev/SECURE_ELEMENT_SET_CARD_EMULATION_MODE_INFO, nfpdrivers.secure_element_set_card_emulation_mode_info"
ms.topic: struct
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	nfcsedev.h
api_name:
-	SECURE_ELEMENT_SET_CARD_EMULATION_MODE_INFO
product:
- Windows
targetos: Windows
req.typenames: SECURE_ELEMENT_SET_CARD_EMULATION_MODE_INFO, *PSECURE_ELEMENT_SET_CARD_EMULATION_MODE_INFO
---

# _SECURE_ELEMENT_SET_CARD_EMULATION_MODE_INFO structure


## -description


SECURE_ELEMENT_SET_CARD_EMULATION_MODE_INFO is the input parameter for  <a href="https://msdn.microsoft.com/library/windows/hardware/dn905512">IOCTL_NFCSE_SET_CARD_EMULATION_MODE</a>.


## -struct-fields




### -field guidSecureElementId

This is a unique identifier for the secure element.


### -field eMode

Card emulation mode: off, power dependent, or power-independent.


