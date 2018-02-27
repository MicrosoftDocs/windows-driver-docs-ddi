---
UID: NS:rilapitypes.RILIMSSIPCAUSE
title: RILIMSSIPCAUSE
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\rilimssipcause_2.htm
old-project: netvista
ms.assetid: ae98e9e7-7001-43dd-9735-e90bb998694c
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: "*LPRILIMSSIPCAUSE, RILIMSSIPCAUSE, RILIMSSIPCAUSE structure [Network Drivers Starting with Windows Vista], netvista.rilimssipcause_2, rilapitypes/RILIMSSIPCAUSE"
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	rilapitypes.h
api_name:
-	RILIMSSIPCAUSE
product: Windows
targetos: Windows
req.typenames: RILIMSSIPCAUSE, *LPRILIMSSIPCAUSE
req.product: Windows 10 or later.
---

# RILIMSSIPCAUSE structure


## -description


This topic supports the Windows driver infrastructure and is not intended to be used directly from your code. 


## -syntax


````
typedef struct _RILIMSSIPCAUSE {
  DWORD  dwCauseValue;
  DWORD  dwReasonValue;
} RILIMSSIPCAUSE, RILIMSSIPCAUSE;
````


## -struct-fields




### -field dwCauseValue


### -field dwReasonValue

