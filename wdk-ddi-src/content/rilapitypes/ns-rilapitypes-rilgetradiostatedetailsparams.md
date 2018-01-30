---
UID: NS:rilapitypes.RILGETRADIOSTATEDETAILSPARAMS
title: RILGETRADIOSTATEDETAILSPARAMS
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\rilgetradiostatedetailsparams_2.htm
old-project: netvista
ms.assetid: 35379f40-6440-4f03-8e14-81aed1e85883
ms.author: windowsdriverdev
ms.date: 1/18/2018
ms.keywords: rilapitypes/RILGETRADIOSTATEDETAILSPARAMS, *LPRILGETRADIOSTATEDETAILSPARAMS, netvista.rilgetradiostatedetailsparams_2, RILGETRADIOSTATEDETAILSPARAMS structure [Network Drivers Starting with Windows Vista], RILGETRADIOSTATEDETAILSPARAMS
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
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
req.lib: 
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
-	RILGETRADIOSTATEDETAILSPARAMS
product: Windows
targetos: Windows
req.typenames: RILGETRADIOSTATEDETAILSPARAMS, *LPRILGETRADIOSTATEDETAILSPARAMS
req.product: Windows 10 or later.
---

# RILGETRADIOSTATEDETAILSPARAMS structure


## -description


This topic supports the Windows driver infrastructure and is not intended to be used directly from your code. 


## -syntax


````
typedef struct _RILGETRADIOSTATEDETAILSPARAMS {
  DWORD  dwGroupId;
  DWORD  dwItemId;
} RILGETRADIOSTATEDETAILSPARAMS, RILGETRADIOSTATEDETAILSPARAMS;
````


## -struct-fields




### -field dwGroupId



### -field dwItemId


