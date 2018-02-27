---
UID: NE:rilapitypes.RILMSGDCSINDICATION
title: RILMSGDCSINDICATION
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\rilmsgdcsindication_2.htm
old-project: netvista
ms.assetid: 292f54d6-0555-47d0-97b9-b76e9e08bf78
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: RILMSGDCSINDICATION, RILMSGDCSINDICATION enumeration [Network Drivers Starting with Windows Vista], RIL_DCSINDICATION_EMAIL, RIL_DCSINDICATION_FAX, RIL_DCSINDICATION_MAX, RIL_DCSINDICATION_OTHER, netvista.rilmsgdcsindication_2, rilapitypes/RILMSGDCSINDICATION, rilapitypes/RIL_DCSINDICATION_EMAIL, rilapitypes/RIL_DCSINDICATION_FAX, rilapitypes/RIL_DCSINDICATION_MAX, rilapitypes/RIL_DCSINDICATION_OTHER
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
-	RILMSGDCSINDICATION
product: Windows
targetos: Windows
req.typenames: RILMSGDCSINDICATION
req.product: Windows 10 or later.
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


### -field RIL_DCSINDICATION_FAX


### -field RIL_DCSINDICATION_EMAIL


### -field RIL_DCSINDICATION_OTHER


### -field RIL_DCSINDICATION_MAX

