---
UID: NS:ntddrilapitypes.RILMSGMWISUMMARYLIST
title: RILMSGMWISUMMARYLIST
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\rilmsgmwisummarylist.htm
old-project: netvista
ms.assetid: b698f9df-5a67-4ddf-9956-21fbd4f6f385
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: "*LPRILMSGMWISUMMARYLIST, RILMSGMWISUMMARYLIST, RILMSGMWISUMMARYLIST structure [Network Drivers Starting with Windows Vista], netvista.rilmsgmwisummarylist, ntddrilapitypes/RILMSGMWISUMMARYLIST"
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
-	RILMSGMWISUMMARYLIST
product: Windows
targetos: Windows
req.typenames: RILMSGMWISUMMARYLIST, *LPRILMSGMWISUMMARYLIST
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

