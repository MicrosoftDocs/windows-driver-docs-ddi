---
UID: NS:ntddrilapitypes.RILCALLRTT
title: RILCALLRTT
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\rilcallrtt.htm
old-project: netvista
ms.assetid: aa69cc11-66c7-4d23-b596-c37472af484a
ms.author: windowsdriverdev
ms.date: 1/18/2018
ms.keywords: RILCALLRTT structure [Network Drivers Starting with Windows Vista], *LPRILCALLRTT, RILCALLRTT, ntddrilapitypes/RILCALLRTT, netvista.rilcallrtt
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
-	RILCALLRTT
product: Windows
targetos: Windows
req.typenames: RILCALLRTT, *LPRILCALLRTT
---

# RILCALLRTT structure


## -description


This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.


## -syntax


````
typedef struct _RILCALLRTT {
  RILCALLRTTACTION  dwRTTAction;
  RILCALLRTTMODE    dwRTTModeType;
  RILCALLRTTCAP     stRTTCap;
} RILCALLRTT, RILCALLRTT;
````


## -struct-fields




### -field dwRTTAction



### -field dwRTTModeType



### -field stRTTCap


