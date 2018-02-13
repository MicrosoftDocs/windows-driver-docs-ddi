---
UID: NS:ntddrilapitypes.RILMSGDCS
title: RILMSGDCS
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\rilmsgdcs.htm
old-project: netvista
ms.assetid: b9d37683-fd3d-42fd-9ec2-128b76325868
ms.author: windowsdriverdev
ms.date: 1/18/2018
ms.keywords: RILMSGDCS, *LPRILMSGDCS, netvista.rilmsgdcs, ntddrilapitypes/RILMSGDCS, RILMSGDCS structure [Network Drivers Starting with Windows Vista]
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
-	RILMSGDCS
product: Windows
targetos: Windows
req.typenames: "*LPRILMSGDCS, RILMSGDCS"
---

# RILMSGDCS structure


## -description


This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.


## -syntax


````
typedef struct _RILMSGDCS {
  DWORD                cbSize;
  DWORD                dwParams;
  RILMSGDCSTYPE        dwType;
  DWORD                dwFlags;
  RILMSGDCSMSGCLASS    dwMsgClass;
  RILMSGDCSALPHABET    dwAlphabet;
  RILMSGDCSINDICATION  dwIndication;
  DWORD                dwLanguage;
} RILMSGDCS, RILMSGDCS;
````


## -struct-fields




### -field cbSize


### -field dwParams


### -field dwType


### -field dwFlags


### -field dwMsgClass


### -field dwAlphabet


### -field dwIndication


### -field dwLanguage

