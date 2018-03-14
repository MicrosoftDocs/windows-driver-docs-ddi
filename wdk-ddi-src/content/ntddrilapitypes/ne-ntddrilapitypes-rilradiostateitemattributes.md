---
UID: NE:ntddrilapitypes.RILRADIOSTATEITEMATTRIBUTES
title: RILRADIOSTATEITEMATTRIBUTES
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\rilradiostateitemattributes.htm
old-project: netvista
ms.assetid: 320ad6e2-0d11-4902-bfdb-8df201d4d5b7
ms.author: windowsdriverdev
ms.date: 2/27/2018
ms.keywords: RILRADIOSTATEITEMATTRIBUTES, RILRADIOSTATEITEMATTRIBUTES enumeration [Network Drivers Starting with Windows Vista], RIL_RADIOSTATE_ITEM_ATTRIBUTE_ALL, RIL_RADIOSTATE_ITEM_ATTRIBUTE_HAVEOPTIONS, RIL_RADIOSTATE_ITEM_ATTRIBUTE_ISDIRTY, RIL_RADIOSTATE_ITEM_ATTRIBUTE_ISWRITABLE, netvista.rilradiostateitemattributes, ntddrilapitypes/RILRADIOSTATEITEMATTRIBUTES, ntddrilapitypes/RIL_RADIOSTATE_ITEM_ATTRIBUTE_ALL, ntddrilapitypes/RIL_RADIOSTATE_ITEM_ATTRIBUTE_HAVEOPTIONS, ntddrilapitypes/RIL_RADIOSTATE_ITEM_ATTRIBUTE_ISDIRTY, ntddrilapitypes/RIL_RADIOSTATE_ITEM_ATTRIBUTE_ISWRITABLE
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
req.header: ntddrilapitypes.h
req.include-header: Rilapitypes.h
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
-	ntddrilapitypes.h
api_name:
-	RILRADIOSTATEITEMATTRIBUTES
product: Windows
targetos: Windows
req.typenames: RILRADIOSTATEITEMATTRIBUTES
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


### -field RIL_RADIOSTATE_ITEM_ATTRIBUTE_ISDIRTY


### -field RIL_RADIOSTATE_ITEM_ATTRIBUTE_ISWRITABLE


### -field RIL_RADIOSTATE_ITEM_ATTRIBUTE_HAVEOPTIONS


### -field RIL_RADIOSTATE_ITEM_ATTRIBUTE_ALL

