---
UID: NE:ntddrilapitypes.RILMSGBCGENERALWARNINGTYPE
title: RILMSGBCGENERALWARNINGTYPE
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\rilmsgbcgeneralwarningtype.htm
old-project: netvista
ms.assetid: c9d1a52e-e133-4fb5-a7a1-75699fe35cac
ms.author: windowsdriverdev
ms.date: 1/11/2018
ms.keywords: RILMSGBCGENERALWARNINGTYPE, RILMSGBCGENERALWARNINGTYPE
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
req.header: ntddrilapitypes.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: RILMSGBCGENERALWARNINGTYPE
req.alt-loc: ntddrilapitypes.h
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
req.typenames: RILMSGBCGENERALWARNINGTYPE
---

# RILMSGBCGENERALWARNINGTYPE enumeration



## -description
This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.



## -syntax

````
typedef enum _RILMSGBCGENERALWARNINGTYPE { 
  RIL_WARNINGTYPE_TSUNAMI,
  RIL_WARNINGTYPE_EARTHQUAKETSUNAMI,
  RIL_WARNINGTYPE_TEST,
  RIL_WARNINGTYPE_OTHER,
  RIL_WARNINGTYPE_RESERVED,
  RIL_WARNINGTYPE_MAX
} RILMSGBCGENERALWARNINGTYPE;
````


## -enum-fields

### -field RIL_WARNINGTYPE_TSUNAMI


### -field RIL_WARNINGTYPE_EARTHQUAKETSUNAMI


### -field RIL_WARNINGTYPE_TEST


### -field RIL_WARNINGTYPE_OTHER


### -field RIL_WARNINGTYPE_RESERVED


### -field RIL_WARNINGTYPE_MAX


## -remarks
