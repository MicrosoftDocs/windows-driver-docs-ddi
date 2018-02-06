---
UID: NS:rilapitypes.RILSMSREADYSTATUS
title: RILSMSREADYSTATUS
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\rilsmsreadystatus_2.htm
old-project: netvista
ms.assetid: a7039749-3f7d-4eca-919c-db27f9e62bf2
ms.author: windowsdriverdev
ms.date: 1/18/2018
ms.keywords: RILSMSREADYSTATUS, netvista.rilsmsreadystatus_2, *LPRILSMSREADYSTATUS, RILSMSREADYSTATUS structure [Network Drivers Starting with Windows Vista], rilapitypes/RILSMSREADYSTATUS
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
-	RILSMSREADYSTATUS
product: Windows
targetos: Windows
req.typenames: "*LPRILSMSREADYSTATUS, RILSMSREADYSTATUS"
req.product: Windows 10 or later.
---

# RILSMSREADYSTATUS structure


## -description


This topic supports the Windows driver infrastructure and is not intended to be used directly from your code. 


## -syntax


````
typedef struct _RILSMSREADYSTATUS {
  DWORD             cbSize;
  DWORD             dwParams;
  DWORD             dwExecutor;
  RILSMSREADYSTATE  dwReadyState;
} RILSMSREADYSTATUS, RILSMSREADYSTATUS;
````


## -struct-fields




### -field cbSize



### -field dwParams



### -field dwExecutor



### -field dwReadyState


