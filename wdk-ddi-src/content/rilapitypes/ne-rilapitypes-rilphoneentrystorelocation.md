---
UID: NE:rilapitypes.RILPHONEENTRYSTORELOCATION
title: RILPHONEENTRYSTORELOCATION
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\rilphoneentrystorelocation_2.htm
old-project: netvista
ms.assetid: f9166dfa-e895-4aca-8080-af3cfe9c143f
ms.author: windowsdriverdev
ms.date: 1/18/2018
ms.keywords: rilapitypes/RILPHONEENTRYSTORELOCATION, RIL_PBLOC_ALL, rilapitypes/RIL_PBLOC_UICCSERVICEDIALING, rilapitypes/RIL_PBLOC_ALL, RILPHONEENTRYSTORELOCATION, RILPHONEENTRYSTORELOCATION enumeration [Network Drivers Starting with Windows Vista], RIL_PBLOC_UICCFIXDIALING, rilapitypes/RIL_PBLOC_UICCPHONEBOOK, rilapitypes/RIL_PBLOC_OWNNUMBERS, RIL_PBLOC_UICCPHONEBOOK, RIL_PBLOC_UICCSERVICEDIALING, netvista.rilphoneentrystorelocation_2, RIL_PBLOC_OWNNUMBERS, rilapitypes/RIL_PBLOC_UICCFIXDIALING
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	rilapitypes.h
apiname:
-	RILPHONEENTRYSTORELOCATION
product: Windows
targetos: Windows
req.typenames: RILPHONEENTRYSTORELOCATION
req.product: Windows 10 or later.
---

# RILPHONEENTRYSTORELOCATION enumeration


## -description


This topic supports the Windows driver infrastructure and is not intended to be used directly from your code. 


## -syntax


````
typedef enum _RILPHONEENTRYSTORELOCATION { 
  RIL_PBLOC_UICCFIXDIALING,
  RIL_PBLOC_OWNNUMBERS,
  RIL_PBLOC_UICCPHONEBOOK,
  RIL_PBLOC_UICCSERVICEDIALING,
  RIL_PBLOC_ALL
} RILPHONEENTRYSTORELOCATION;
````


## -enum-fields




### -field RIL_PBLOC_UNKNOWN



#### - RIL_PBLOC_UICCFIXDIALING



#### - RIL_PBLOC_OWNNUMBERS



#### - RIL_PBLOC_UICCPHONEBOOK



#### - RIL_PBLOC_UICCSERVICEDIALING



#### - RIL_PBLOC_ALL


