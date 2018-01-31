---
UID: NE:rilapitypes.RILRADIOSTATEITEMATTRIBUTES
title: RILRADIOSTATEITEMATTRIBUTES
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\rilradiostateitemattributes_2.htm
old-project: netvista
ms.assetid: d13c1946-1283-4ed6-953e-626fda91a782
ms.author: windowsdriverdev
ms.date: 1/18/2018
ms.keywords: rilapitypes/RIL_RADIOSTATE_ITEM_ATTRIBUTE_HAVEOPTIONS, rilapitypes/RIL_RADIOSTATE_ITEM_ATTRIBUTE_ALL, rilapitypes/RILRADIOSTATEITEMATTRIBUTES, rilapitypes/RIL_RADIOSTATE_ITEM_ATTRIBUTE_ISDIRTY, RILRADIOSTATEITEMATTRIBUTES, RIL_RADIOSTATE_ITEM_ATTRIBUTE_HAVEOPTIONS, RIL_RADIOSTATE_ITEM_ATTRIBUTE_ISWRITABLE, RIL_RADIOSTATE_ITEM_ATTRIBUTE_ALL, netvista.rilradiostateitemattributes_2, rilapitypes/RIL_RADIOSTATE_ITEM_ATTRIBUTE_ISWRITABLE, RIL_RADIOSTATE_ITEM_ATTRIBUTE_ISDIRTY, RILRADIOSTATEITEMATTRIBUTES enumeration [Network Drivers Starting with Windows Vista]
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
-	RILRADIOSTATEITEMATTRIBUTES
product: Windows
targetos: Windows
req.typenames: RILRADIOSTATEITEMATTRIBUTES
req.product: Windows 10 or later.
---

# RILRADIOSTATEITEMATTRIBUTES enumeration


## -description


This topic supports the Windows driver infrastructure and is not intended to be used directly from your code. 


## -syntax


````
typedef enum _RILRADIOSTATEITEMATTRIBUTES { 
  RIL_RADIOSTATE_ITEM_ATTRIBUTE_ISDIRTY,
  RIL_RADIOSTATE_ITEM_ATTRIBUTE_ISWRITABLE,
  RIL_RADIOSTATE_ITEM_ATTRIBUTE_HAVEOPTIONS,
  RIL_RADIOSTATE_ITEM_ATTRIBUTE_ALL
} RILRADIOSTATEITEMATTRIBUTES;
````


## -enum-fields




### -field RIL_RADIOSTATE_ITEM_ATTRIBUTE_NO_ATTRIBUTE



#### - RIL_RADIOSTATE_ITEM_ATTRIBUTE_ISDIRTY



#### - RIL_RADIOSTATE_ITEM_ATTRIBUTE_ISWRITABLE



#### - RIL_RADIOSTATE_ITEM_ATTRIBUTE_HAVEOPTIONS



#### - RIL_RADIOSTATE_ITEM_ATTRIBUTE_ALL


