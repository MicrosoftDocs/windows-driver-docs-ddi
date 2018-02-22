---
UID: NS:rilapitypes.RILMSGMWISUMMARYLIST
title: RILMSGMWISUMMARYLIST
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\rilmsgmwisummarylist_2.htm
old-project: netvista
ms.assetid: 85f07ef4-6306-4995-9c95-9bbae775af1c
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: "*LPRILMSGMWISUMMARYLIST, RILMSGMWISUMMARYLIST structure [Network Drivers Starting with Windows Vista], netvista.rilmsgmwisummarylist_2, RILMSGMWISUMMARYLIST, rilapitypes/RILMSGMWISUMMARYLIST"
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
-	RILMSGMWISUMMARYLIST
product: Windows
targetos: Windows
req.typenames: RILMSGMWISUMMARYLIST, *LPRILMSGMWISUMMARYLIST
req.product: Windows 10 or later.
---

# RILMSGMWISUMMARYLIST structure


## -description


This topic supports the Windows driver infrastructure and is not intended to be used directly from your code. 


## -syntax


````
typedef struct _RILMSGMWISUMMARYLIST {
  DWORD                cbSize;
  DWORD                dwParams;
  DWORD                dwExecutor;
  DWORD                dwReferenceNumber;
  RILADDRESS           stAccountAddress;
  DWORD                dwTotalNumberOfDetailItems;
  DWORD                dwNumberOfSummaryItems;
  RILMSGMWISUMMARY [1] stMwiSummary;
} RILMSGMWISUMMARYLIST, RILMSGMWISUMMARYLIST;
````


## -struct-fields




### -field cbSize


### -field dwParams


### -field dwExecutor


### -field dwReferenceNumber


### -field stAccountAddress


### -field dwTotalNumberOfDetailItems


### -field dwNumberOfSummaryItems


### -field stMwiSummary

