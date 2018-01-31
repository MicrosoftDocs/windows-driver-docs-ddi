---
UID: NS:ntddrilapitypes.RILGETRADIOSTATEDETAILSPARAMS
title: RILGETRADIOSTATEDETAILSPARAMS
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\rilgetradiostatedetailsparams.htm
old-project: netvista
ms.assetid: faee1991-a183-4285-af14-402094dc6694
ms.author: windowsdriverdev
ms.date: 1/18/2018
ms.keywords: RILGETRADIOSTATEDETAILSPARAMS, RILGETRADIOSTATEDETAILSPARAMS structure [Network Drivers Starting with Windows Vista], *LPRILGETRADIOSTATEDETAILSPARAMS, ntddrilapitypes/RILGETRADIOSTATEDETAILSPARAMS, netvista.rilgetradiostatedetailsparams
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
-	RILGETRADIOSTATEDETAILSPARAMS
product: Windows
targetos: Windows
req.typenames: "*LPRILGETRADIOSTATEDETAILSPARAMS, RILGETRADIOSTATEDETAILSPARAMS"
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




#### - dwGroupId



#### - dwItemId


