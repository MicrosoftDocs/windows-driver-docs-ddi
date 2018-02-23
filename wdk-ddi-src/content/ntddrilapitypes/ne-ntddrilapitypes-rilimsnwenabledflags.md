---
UID: NE:ntddrilapitypes.RILIMSNWENABLEDFLAGS
title: RILIMSNWENABLEDFLAGS
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\rilimsnwenabledflags.htm
old-project: netvista
ms.assetid: ae13790a-2442-4a8e-88cb-2cb6c8e02da6
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: ntddrilapitypes/RIL_IMS_NW_ENABLED_FLAG_VOICE, RIL_IMS_NW_ENABLED_FLAG_VOICE, RIL_IMS_NW_ENABLED_FLAG_PROVISION, ntddrilapitypes/RIL_IMS_NW_ENABLED_FLAG_VIDEO, ntddrilapitypes/RIL_IMS_NW_ENABLED_FLAG_EAB, RIL_IMS_NW_ENABLED_FLAG_EAB, RIL_IMS_NW_ENABLED_FLAG_ALL, RILIMSNWENABLEDFLAGS, ntddrilapitypes/RILIMSNWENABLEDFLAGS, netvista.rilimsnwenabledflags, ntddrilapitypes/RIL_IMS_NW_ENABLED_FLAG_ALL, ntddrilapitypes/RIL_IMS_NW_ENABLED_FLAG_PROVISION, RIL_IMS_NW_ENABLED_FLAG_VIDEO, RILIMSNWENABLEDFLAGS enumeration [Network Drivers Starting with Windows Vista]
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
-	RILIMSNWENABLEDFLAGS
product: Windows
targetos: Windows
req.typenames: RILIMSNWENABLEDFLAGS
---

# RILIMSNWENABLEDFLAGS enumeration


## -description


This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.


## -syntax


````
typedef enum _RILIMSNWENABLEDFLAGS { 
  RIL_IMS_NW_ENABLED_FLAG_PROVISION,
  RIL_IMS_NW_ENABLED_FLAG_VOICE,
  RIL_IMS_NW_ENABLED_FLAG_VIDEO,
  RIL_IMS_NW_ENABLED_FLAG_EAB,
  RIL_IMS_NW_ENABLED_FLAG_ALL
} RILIMSNWENABLEDFLAGS;
````


## -enum-fields




### -field RIL_IMS_NW_ENABLED_FLAG_NONE


### -field RIL_IMS_NW_ENABLED_FLAG_PROVISION


### -field RIL_IMS_NW_ENABLED_FLAG_VOICE


### -field RIL_IMS_NW_ENABLED_FLAG_VIDEO


### -field RIL_IMS_NW_ENABLED_FLAG_EAB


### -field RIL_IMS_NW_ENABLED_FLAG_ALL

