---
UID: NS:ntddrilapitypes.RILSETCALLFORWARDINGSTATUSPARAMS
title: RILSETCALLFORWARDINGSTATUSPARAMS
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\rilsetcallforwardingstatusparams.htm
old-project: netvista
ms.assetid: 7863a72d-e3cc-4627-a956-7e5a080c4aad
ms.author: windowsdriverdev
ms.date: 1/18/2018
ms.keywords: ntddrilapitypes/RILSETCALLFORWARDINGSTATUSPARAMS, RILSETCALLFORWARDINGSTATUSPARAMS, netvista.rilsetcallforwardingstatusparams, RILSETCALLFORWARDINGSTATUSPARAMS structure [Network Drivers Starting with Windows Vista], *LPRILSETCALLFORWARDINGSTATUSPARAMS
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
-	RILSETCALLFORWARDINGSTATUSPARAMS
product: Windows
targetos: Windows
req.typenames: *LPRILSETCALLFORWARDINGSTATUSPARAMS, RILSETCALLFORWARDINGSTATUSPARAMS
---

# RILSETCALLFORWARDINGSTATUSPARAMS structure


## -description


This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.


## -syntax


````
typedef struct _RILSETCALLFORWARDINGSTATUSPARAMS {
  DWORD                            dwExecutor;
  RILCALLFORWARDINGSETTINGSREASON  dwReason;
  BOOL                             fAllClasses;
  DWORD                            dwInfoClasses;
  RILSERVICESETTINGSSTATUS         dwStatus;
} RILSETCALLFORWARDINGSTATUSPARAMS, RILSETCALLFORWARDINGSTATUSPARAMS;
````


## -struct-fields




### -field dwExecutor



### -field dwReason



### -field fAllClasses



### -field dwInfoClasses



### -field dwStatus


