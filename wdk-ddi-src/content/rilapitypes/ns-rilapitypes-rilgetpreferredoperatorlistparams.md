---
UID: NS:rilapitypes.RILGETPREFERREDOPERATORLISTPARAMS
title: RILGETPREFERREDOPERATORLISTPARAMS
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\rilgetpreferredoperatorlistparams_2.htm
old-project: netvista
ms.assetid: bca0f1a1-2951-40c3-85b4-6009176ea574
ms.author: windowsdriverdev
ms.date: 1/18/2018
ms.keywords: rilapitypes/RILGETPREFERREDOPERATORLISTPARAMS, netvista.rilgetpreferredoperatorlistparams_2, RILGETPREFERREDOPERATORLISTPARAMS structure [Network Drivers Starting with Windows Vista], RILGETPREFERREDOPERATORLISTPARAMS, *LPRILGETPREFERREDOPERATORLISTPARAMS
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
-	RILGETPREFERREDOPERATORLISTPARAMS
product: Windows
targetos: Windows
req.typenames: RILGETPREFERREDOPERATORLISTPARAMS, *LPRILGETPREFERREDOPERATORLISTPARAMS
req.product: Windows 10 or later.
---

# RILGETPREFERREDOPERATORLISTPARAMS structure


## -description


This topic supports the Windows driver infrastructure and is not intended to be used directly from your code. 


## -syntax


````
typedef struct _RILGETPREFERREDOPERATORLISTPARAMS {
  HUICCAPP                             hUiccApp;
  RILGETPREFERENCEDOPERATORLISTFORMAT  dwFormat;
} RILGETPREFERREDOPERATORLISTPARAMS, RILGETPREFERREDOPERATORLISTPARAMS;
````


## -struct-fields




### -field hUiccApp


### -field dwFormat

