---
UID: NS:compstui._OPTCOMBO
title: "_OPTCOMBO"
author: windows-driver-content
description: "."
old-location: print\optcombo.htm
old-project: print
ms.assetid: B1F5A79A-8F64-4B7B-ADB4-BDD8EC17F22E
ms.author: windowsdriverdev
ms.date: 2/2/2018
ms.keywords: OPTCOMBO structure [Print Devices], POPTCOMBO structure pointer [Print Devices], compstui/OPTCOMBO, *POPTCOMBO, print.optcombo, OPTCOMBO, POPTCOMBO, compstui/POPTCOMBO, _OPTCOMBO
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: compstui.h
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
-	Compstui.h
apiname:
-	OPTCOMBO
product: Windows
targetos: Windows
req.typenames: "*POPTCOMBO, OPTCOMBO"
---

# _OPTCOMBO structure


## -description





## -syntax


````
typedef struct _OPTCOMBO {
  WORD      cbSize;
  BYTE      Flags;
  WORD      cListItem;
  POPTPARAM pListItem;
  LONG      Sel;
  LONG      dwReserved[3];
} OPTCOMBO, *POPTCOMBO;
````


## -struct-fields




### -field cbSize


### -field Flags


### -field cListItem


### -field pListItem


### -field Sel


### -field dwReserved

