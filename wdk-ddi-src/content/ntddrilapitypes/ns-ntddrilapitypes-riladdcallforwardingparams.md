---
UID: NS:ntddrilapitypes.RILADDCALLFORWARDINGPARAMS
title: RILADDCALLFORWARDINGPARAMS
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\riladdcallforwardingparams.htm
old-project: netvista
ms.assetid: 8918552d-6a7b-414a-ab0c-a5690f109db4
ms.author: windowsdriverdev
ms.date: 1/18/2018
ms.keywords: ntddrilapitypes/RILADDCALLFORWARDINGPARAMS, RILADDCALLFORWARDINGPARAMS, *LPRILADDCALLFORWARDINGPARAMS, netvista.riladdcallforwardingparams, RILADDCALLFORWARDINGPARAMS structure [Network Drivers Starting with Windows Vista]
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
-	RILADDCALLFORWARDINGPARAMS
product: Windows
targetos: Windows
req.typenames: "*LPRILADDCALLFORWARDINGPARAMS, RILADDCALLFORWARDINGPARAMS"
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


