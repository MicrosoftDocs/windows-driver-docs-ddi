---
UID: NE:ntddrilapitypes.RILVOICEDOMAIN
title: RILVOICEDOMAIN
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\rilvoicedomain.htm
old-project: netvista
ms.assetid: a7154c32-bca6-482d-b1f9-7c090a7ce432
ms.author: windowsdriverdev
ms.date: 1/18/2018
ms.keywords: RIL_VOICE_DOMAIN_3GPP, ntddrilapitypes/RIL_VOICE_DOMAIN_3GPP, RIL_VOICE_DOMAIN_IMS, ntddrilapitypes/RILVOICEDOMAIN, RILVOICEDOMAIN enumeration [Network Drivers Starting with Windows Vista], netvista.rilvoicedomain, ntddrilapitypes/RIL_VOICE_DOMAIN_IMS, RIL_VOICE_DOMAIN_3GPP2, ntddrilapitypes/RIL_VOICE_DOMAIN_3GPP2, RILVOICEDOMAIN, ntddrilapitypes/RIL_VOICE_DOMAIN_MAX, RIL_VOICE_DOMAIN_MAX
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
req.header: ntddrilapitypes.h
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
-	ntddrilapitypes.h
apiname:
-	RILVOICEDOMAIN
product: Windows
targetos: Windows
req.typenames: RILVOICEDOMAIN
---

# RILVOICEDOMAIN enumeration


## -description


This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.


## -syntax


````
typedef enum _RILVOICEDOMAIN { 
  RIL_VOICE_DOMAIN_3GPP,
  RIL_VOICE_DOMAIN_3GPP2,
  RIL_VOICE_DOMAIN_IMS,
  RIL_VOICE_DOMAIN_MAX
} RILVOICEDOMAIN;
````


## -enum-fields




### -field RIL_VOICE_DOMAIN_NONE



### -field RIL_VOICE_DOMAIN_3GPP



### -field RIL_VOICE_DOMAIN_3GPP2



### -field RIL_VOICE_DOMAIN_IMS



### -field RIL_VOICE_DOMAIN_MAX


