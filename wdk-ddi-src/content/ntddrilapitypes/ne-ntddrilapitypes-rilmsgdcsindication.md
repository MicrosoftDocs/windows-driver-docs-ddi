---
UID: NE:ntddrilapitypes.RILMSGDCSINDICATION
title: RILMSGDCSINDICATION
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\rilmsgdcsindication.htm
old-project: netvista
ms.assetid: 709980c8-e13f-48a7-9af7-26f0bb79e699
ms.author: windowsdriverdev
ms.date: 1/18/2018
ms.keywords: RIL_DCSINDICATION_FAX, ntddrilapitypes/RIL_DCSINDICATION_OTHER, ntddrilapitypes/RILMSGDCSINDICATION, ntddrilapitypes/RIL_DCSINDICATION_MAX, ntddrilapitypes/RIL_DCSINDICATION_EMAIL, RIL_DCSINDICATION_EMAIL, netvista.rilmsgdcsindication, ntddrilapitypes/RIL_DCSINDICATION_FAX, RIL_DCSINDICATION_OTHER, RIL_DCSINDICATION_MAX, RILMSGDCSINDICATION enumeration [Network Drivers Starting with Windows Vista], RILMSGDCSINDICATION
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
-	RILMSGDCSINDICATION
product: Windows
targetos: Windows
req.typenames: RILMSGDCSINDICATION
---

# RILMSGDCSINDICATION enumeration


## -description


This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.


## -syntax


````
typedef enum _RILMSGDCSINDICATION { 
  RIL_DCSINDICATION_FAX,
  RIL_DCSINDICATION_EMAIL,
  RIL_DCSINDICATION_OTHER,
  RIL_DCSINDICATION_MAX
} RILMSGDCSINDICATION;
````


## -enum-fields




### -field RIL_DCSINDICATION_VOICEMAIL



#### - RIL_DCSINDICATION_FAX



#### - RIL_DCSINDICATION_EMAIL



#### - RIL_DCSINDICATION_OTHER



#### - RIL_DCSINDICATION_MAX


