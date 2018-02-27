---
UID: NE:rilapitypes.RILMSGDCSTYPE
title: RILMSGDCSTYPE
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\rilmsgdcstype_2.htm
old-project: netvista
ms.assetid: 5eabc972-f372-4d70-ab38-8830f7907a7a
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: RILMSGDCSTYPE, RILMSGDCSTYPE enumeration [Network Drivers Starting with Windows Vista], RIL_DCSTYPE_LANGUAGE, RIL_DCSTYPE_MAX, RIL_DCSTYPE_MSGCLASS, RIL_DCSTYPE_MSGWAIT, netvista.rilmsgdcstype_2, rilapitypes/RILMSGDCSTYPE, rilapitypes/RIL_DCSTYPE_LANGUAGE, rilapitypes/RIL_DCSTYPE_MAX, rilapitypes/RIL_DCSTYPE_MSGCLASS, rilapitypes/RIL_DCSTYPE_MSGWAIT
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
-	RILMSGDCSTYPE
product: Windows
targetos: Windows
req.typenames: RILMSGDCSTYPE
req.product: Windows 10 or later.
---

# RILMSGDCSTYPE enumeration


## -description


This topic supports the Windows driver infrastructure and is not intended to be used directly from your code. 


## -syntax


````
typedef enum _RILMSGDCSTYPE { 
  RIL_DCSTYPE_MSGWAIT,
  RIL_DCSTYPE_MSGCLASS,
  RIL_DCSTYPE_LANGUAGE,
  RIL_DCSTYPE_MAX
} RILMSGDCSTYPE;
````


## -enum-fields




### -field RIL_DCSTYPE_GENERAL


### -field RIL_DCSTYPE_MSGWAIT


### -field RIL_DCSTYPE_MSGCLASS


### -field RIL_DCSTYPE_LANGUAGE


### -field RIL_DCSTYPE_MAX

