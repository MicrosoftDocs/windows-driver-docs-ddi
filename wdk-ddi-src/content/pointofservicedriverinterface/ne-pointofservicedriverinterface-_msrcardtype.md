---
UID: NE:pointofservicedriverinterface._MsrCardType
title: "_MsrCardType"
author: windows-driver-content
description: This enumeration defines the kinds of magnetic stripe cards.
old-location: pos\msrcardtype.htm
old-project: pos
ms.assetid: aa7af210-fb5e-49a1-911f-cb1e90c2ac26
ms.author: windowsdriverdev
ms.date: 2/23/2018
ms.keywords: ",  , ,, C, M, MsrCardType, MsrCardType enumeration, MsrCardType_Aamva, MsrCardType_Bank, MsrCardType_ExtendedBase, MsrCardType_Unknown, T, _, _MsrCardType, a, d, e, p, pointofservicedriverinterface/MsrCardType, pointofservicedriverinterface/MsrCardType_Aamva, pointofservicedriverinterface/MsrCardType_Bank, pointofservicedriverinterface/MsrCardType_ExtendedBase, pointofservicedriverinterface/MsrCardType_Unknown, pos.msrcardtype, r, s, y"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
req.header: pointofservicedriverinterface.h
req.include-header: Pointofservicedriverinterface.h
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
req.irql: Called at PASSIVE_LEVEL.
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	pointofservicedriverinterface.h
apiname:
-	MsrCardType
product: Windows
targetos: Windows
req.typenames: MsrCardType
---

# _MsrCardType enumeration


## -description


This enumeration defines the kinds of magnetic stripe cards.


## -syntax


````
typedef enum _MsrCardType { 
  MsrCardType_Unknown,
  MsrCardType_Bank,
  MsrCardType_Aamva,
  MsrCardType_ExtendedBase
} MsrCardType;
````


## -enum-fields




### -field MsrCardType_Unknown

Unknown card type.


### -field MsrCardType_Bank

Bank card.


### -field MsrCardType_Aamva

American Association of Motor Vehicle Administrators (AAMVA) card.


### -field MsrCardType_ExtendedBase

Vendor-specific card.

