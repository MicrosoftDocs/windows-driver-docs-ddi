---
UID: NS:ntddrilapitypes.RILRADIOSTATEITEMS
title: RILRADIOSTATEITEMS
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\rilradiostateitems.htm
old-project: netvista
ms.assetid: 26b2521c-7008-437d-aed3-3ed2be5d5959
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: ",  , *, *LPRILRADIOSTATEITEMS, ,, A, D, E, I, L, M, O, P, R, RILRADIOSTATEITEMS, RILRADIOSTATEITEMS structure [Network Drivers Starting with Windows Vista], S, T, netvista.rilradiostateitems, ntddrilapitypes/RILRADIOSTATEITEMS"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
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
-	RILRADIOSTATEITEMS
product: Windows
targetos: Windows
req.typenames: RILRADIOSTATEITEMS, *LPRILRADIOSTATEITEMS
---

# RILRADIOSTATEITEMS structure


## -description


This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.


## -syntax


````
typedef struct _RILRADIOSTATEITEMS {
  DWORD                 dwGroupId;
  DWORD                 dwCntItems;
  RILRADIOSTATEITEM [1] rilItems;
} RILRADIOSTATEITEMS, RILRADIOSTATEITEMS;
````


## -struct-fields




### -field dwGroupId


### -field dwCntItems


### -field rilItems

