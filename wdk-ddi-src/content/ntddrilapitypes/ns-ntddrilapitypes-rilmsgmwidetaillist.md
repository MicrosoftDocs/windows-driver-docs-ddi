---
UID: NS:ntddrilapitypes.RILMSGMWIDETAILLIST
title: RILMSGMWIDETAILLIST
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\rilmsgmwidetaillist.htm
old-project: netvista
ms.assetid: 026cf4d6-2f34-4911-8ec6-0b4170463e4d
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: ntddrilapitypes/RILMSGMWIDETAILLIST, RILMSGMWIDETAILLIST structure [Network Drivers Starting with Windows Vista], netvista.rilmsgmwidetaillist, *LPRILMSGMWIDETAILLIST, RILMSGMWIDETAILLIST
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
-	RILMSGMWIDETAILLIST
product: Windows
targetos: Windows
req.typenames: RILMSGMWIDETAILLIST, *LPRILMSGMWIDETAILLIST
---

# RILMSGMWIDETAILLIST structure


## -description


This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.


## -syntax


````
typedef struct _RILMSGMWIDETAILLIST {
  DWORD               cbSize;
  DWORD               dwParams;
  DWORD               dwExecutor;
  DWORD               dwReferenceNumber;
  DWORD               dwNumberOfDetailItems;
  RILMSGMWIDETAIL [1] stMwiDetail;
} RILMSGMWIDETAILLIST, RILMSGMWIDETAILLIST;
````


## -struct-fields




### -field cbSize


### -field dwParams


### -field dwExecutor


### -field dwReferenceNumber


### -field dwNumberOfDetailItems


### -field stMwiDetail

