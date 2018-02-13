---
UID: NS:rilapitypes.RILMSGMWIDETAIL
title: RILMSGMWIDETAIL
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\rilmsgmwidetail_2.htm
old-project: netvista
ms.assetid: 58b0c3bc-f63a-4db7-a5e1-767f12b7655a
ms.author: windowsdriverdev
ms.date: 1/18/2018
ms.keywords: netvista.rilmsgmwidetail_2, RILMSGMWIDETAIL, RILMSGMWIDETAIL structure [Network Drivers Starting with Windows Vista], rilapitypes/RILMSGMWIDETAIL, *LPRILMSGMWIDETAIL
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
-	RILMSGMWIDETAIL
product: Windows
targetos: Windows
req.typenames: RILMSGMWIDETAIL, *LPRILMSGMWIDETAIL
req.product: Windows 10 or later.
---

# RILMSGMWIDETAIL structure


## -description


This topic supports the Windows driver infrastructure and is not intended to be used directly from your code. 


## -syntax


````
typedef struct _RILMSGMWIDETAIL {
  RILMSGMWITYPE                dwMwiType;
  RILMSGMWIPRIORITY            dwMwiPriority;
  RILADDRESS                   raToAddress;
  RILADDRESS                   raFromAddress;
  RILSYSTEMTIME                stDateSent;
  WCHAR [MAXLENGTH_MWISUBJECT] wszSubject;
  WCHAR [MAXLENGTH_ADDRESS]    wszMessageId;
} RILMSGMWIDETAIL, RILMSGMWIDETAIL;
````


## -struct-fields




### -field dwMwiType


### -field dwMwiPriority


### -field raToAddress


### -field raFromAddress


### -field stDateSent


### -field wszSubject


### -field wszMessageId

