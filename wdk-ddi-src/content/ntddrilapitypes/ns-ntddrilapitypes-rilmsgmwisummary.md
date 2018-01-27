---
UID: NS:ntddrilapitypes.RILMSGMWISUMMARY
title: RILMSGMWISUMMARY
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\rilmsgmwisummary.htm
old-project: netvista
ms.assetid: 5a718c4d-21c9-4dfd-844a-0053a379196d
ms.author: windowsdriverdev
ms.date: 1/18/2018
ms.keywords: RILMSGMWISUMMARY, ntddrilapitypes/RILMSGMWISUMMARY, netvista.rilmsgmwisummary, RILMSGMWISUMMARY structure [Network Drivers Starting with Windows Vista], *LPRILMSGMWISUMMARY
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
-	RILMSGMWISUMMARY
product: Windows
targetos: Windows
req.typenames: *LPRILMSGMWISUMMARY, RILMSGMWISUMMARY
---

# RILMSGMWISUMMARY structure


## -description


This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.


## -syntax


````
typedef struct _RILMSGMWISUMMARY {
  RILMSGMWITYPE  dwMwiType;
  DWORD          dwNumberOfNewMessages;
  DWORD          dwNumberOfOldMessages;
  DWORD          dwNumberOfNewUrgentMessages;
  DWORD          dwNumberOfOldUrgentMessages;
} RILMSGMWISUMMARY, RILMSGMWISUMMARY;
````


## -struct-fields




### -field dwMwiType



### -field dwNumberOfNewMessages



### -field dwNumberOfOldMessages



### -field dwNumberOfNewUrgentMessages



### -field dwNumberOfOldUrgentMessages


