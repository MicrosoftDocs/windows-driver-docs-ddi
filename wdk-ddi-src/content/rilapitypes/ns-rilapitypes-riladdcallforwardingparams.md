---
UID: NS:rilapitypes.RILADDCALLFORWARDINGPARAMS
title: RILADDCALLFORWARDINGPARAMS
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\riladdcallforwardingparams_2.htm
old-project: netvista
ms.assetid: 96adad09-fe54-469a-b57d-4df68750968c
ms.author: windowsdriverdev
ms.date: 1/18/2018
ms.keywords: RILADDCALLFORWARDINGPARAMS, netvista.riladdcallforwardingparams_2, rilapitypes/RILADDCALLFORWARDINGPARAMS, RILADDCALLFORWARDINGPARAMS structure [Network Drivers Starting with Windows Vista], *LPRILADDCALLFORWARDINGPARAMS
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
-	RILADDCALLFORWARDINGPARAMS
product: Windows
targetos: Windows
req.typenames: RILADDCALLFORWARDINGPARAMS, *LPRILADDCALLFORWARDINGPARAMS
req.product: Windows 10 or later.
---

# RILADDCALLFORWARDINGPARAMS structure


## -description


This topic supports the Windows driver infrastructure and is not intended to be used directly from your code. 


## -syntax


````
typedef struct _RILADDCALLFORWARDINGPARAMS {
  DWORD                            dwExecutor;
  RILCALLFORWARDINGSETTINGSREASON  dwReason;
  RILCALLFORWARDINGSETTINGS        rcfsSettings;
} RILADDCALLFORWARDINGPARAMS, RILADDCALLFORWARDINGPARAMS;
````


## -struct-fields




### -field dwExecutor


### -field dwReason


### -field rcfsSettings

