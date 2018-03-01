---
UID: NE:rilapitypes.RILMSGBCGENERALWARNINGTYPE
title: RILMSGBCGENERALWARNINGTYPE
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\rilmsgbcgeneralwarningtype_2.htm
old-project: netvista
ms.assetid: 0e556cab-87af-4b3d-8c8c-d0815323a002
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: RILMSGBCGENERALWARNINGTYPE, RILMSGBCGENERALWARNINGTYPE enumeration [Network Drivers Starting with Windows Vista], RIL_WARNINGTYPE_EARTHQUAKETSUNAMI, RIL_WARNINGTYPE_MAX, RIL_WARNINGTYPE_OTHER, RIL_WARNINGTYPE_RESERVED, RIL_WARNINGTYPE_TEST, RIL_WARNINGTYPE_TSUNAMI, netvista.rilmsgbcgeneralwarningtype_2, rilapitypes/RILMSGBCGENERALWARNINGTYPE, rilapitypes/RIL_WARNINGTYPE_EARTHQUAKETSUNAMI, rilapitypes/RIL_WARNINGTYPE_MAX, rilapitypes/RIL_WARNINGTYPE_OTHER, rilapitypes/RIL_WARNINGTYPE_RESERVED, rilapitypes/RIL_WARNINGTYPE_TEST, rilapitypes/RIL_WARNINGTYPE_TSUNAMI
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
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
req.lib: NtosKrnl.exe
req.dll: 
req.irql: 
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	rilapitypes.h
api_name:
-	RILMSGBCGENERALWARNINGTYPE
product: Windows
targetos: Windows
req.typenames: RILMSGBCGENERALWARNINGTYPE
req.product: Windows 10 or later.
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




### -field RIL_WARNINGTYPE_EARTHQUAKE


### -field RIL_WARNINGTYPE_TSUNAMI


### -field RIL_WARNINGTYPE_EARTHQUAKETSUNAMI


### -field RIL_WARNINGTYPE_TEST


### -field RIL_WARNINGTYPE_OTHER


### -field RIL_WARNINGTYPE_RESERVED


### -field RIL_WARNINGTYPE_MAX

