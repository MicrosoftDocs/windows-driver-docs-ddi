---
UID: NE:rilapitypes.RILPHONEBOOKLOCATIONCAPS
title: RILPHONEBOOKLOCATIONCAPS
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\rilphonebooklocationcaps_2.htm
old-project: netvista
ms.assetid: 6fe1077d-3b12-4cb6-b2ed-675b19b034c4
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: RILPHONEBOOKLOCATIONCAPS, RILPHONEBOOKLOCATIONCAPS enumeration [Network Drivers Starting with Windows Vista], RIL_CAPS_PBLOC_ALL, RIL_CAPS_PBLOC_OWNNUMBERS, RIL_CAPS_PBLOC_UICCFIXDIALING, RIL_CAPS_PBLOC_UICCPHONEBOOK, RIL_CAPS_PBLOC_UICCSERVICEDIALING, netvista.rilphonebooklocationcaps_2, rilapitypes/RILPHONEBOOKLOCATIONCAPS, rilapitypes/RIL_CAPS_PBLOC_ALL, rilapitypes/RIL_CAPS_PBLOC_OWNNUMBERS, rilapitypes/RIL_CAPS_PBLOC_UICCFIXDIALING, rilapitypes/RIL_CAPS_PBLOC_UICCPHONEBOOK, rilapitypes/RIL_CAPS_PBLOC_UICCSERVICEDIALING
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
req.header: rilapitypes.h
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
req.lib: NtosKrnl.exe
req.dll: 
req.irql: 
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	rilapitypes.h
api_name:
-	RILPHONEBOOKLOCATIONCAPS
product: Windows
targetos: Windows
req.typenames: RILPHONEBOOKLOCATIONCAPS
req.product: Windows 10 or later.
---

# RILPHONEBOOKLOCATIONCAPS enumeration


## -description


This topic supports the Windows driver infrastructure and is not intended to be used directly from your code. 


## -syntax


````
typedef enum _RILPHONEBOOKLOCATIONCAPS { 
  RIL_CAPS_PBLOC_UICCFIXDIALING,
  RIL_CAPS_PBLOC_OWNNUMBERS,
  RIL_CAPS_PBLOC_UICCPHONEBOOK,
  RIL_CAPS_PBLOC_UICCSERVICEDIALING,
  RIL_CAPS_PBLOC_ALL
} RILPHONEBOOKLOCATIONCAPS;
````


## -enum-fields




### -field RIL_CAPS_PBLOC_UNKOWN


### -field RIL_CAPS_PBLOC_UICCFIXDIALING


### -field RIL_CAPS_PBLOC_OWNNUMBERS


### -field RIL_CAPS_PBLOC_UICCPHONEBOOK


### -field RIL_CAPS_PBLOC_UICCSERVICEDIALING


### -field RIL_CAPS_PBLOC_ALL

