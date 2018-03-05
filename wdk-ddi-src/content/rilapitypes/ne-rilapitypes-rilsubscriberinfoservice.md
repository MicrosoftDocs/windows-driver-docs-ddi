---
UID: NE:rilapitypes.RILSUBSCRIBERINFOSERVICE
title: RILSUBSCRIBERINFOSERVICE
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\rilsubscriberinfoservice_2.htm
old-project: netvista
ms.assetid: 32ae6058-586d-44b4-b2b1-be61875e2f9f
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: RILSUBSCRIBERINFOSERVICE, RILSUBSCRIBERINFOSERVICE enumeration [Network Drivers Starting with Windows Vista], RIL_SERVICE_FAX, RIL_SERVICE_MAX, RIL_SERVICE_OTHER, RIL_SERVICE_VOICE, netvista.rilsubscriberinfoservice_2, rilapitypes/RILSUBSCRIBERINFOSERVICE, rilapitypes/RIL_SERVICE_FAX, rilapitypes/RIL_SERVICE_MAX, rilapitypes/RIL_SERVICE_OTHER, rilapitypes/RIL_SERVICE_VOICE
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
-	RILSUBSCRIBERINFOSERVICE
product: Windows
targetos: Windows
req.typenames: RILSUBSCRIBERINFOSERVICE
req.product: Windows 10 or later.
---

# RILSUBSCRIBERINFOSERVICE enumeration


## -description


This topic supports the Windows driver infrastructure and is not intended to be used directly from your code. 


## -syntax


````
typedef enum _RILSUBSCRIBERINFOSERVICE { 
  RIL_SERVICE_VOICE,
  RIL_SERVICE_FAX,
  RIL_SERVICE_OTHER,
  RIL_SERVICE_MAX
} RILSUBSCRIBERINFOSERVICE;
````


## -enum-fields




### -field RIL_SERVICE_UNKNOWN


### -field RIL_SERVICE_VOICE


### -field RIL_SERVICE_FAX


### -field RIL_SERVICE_OTHER


### -field RIL_SERVICE_MAX

