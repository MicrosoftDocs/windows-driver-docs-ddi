---
UID: NS:rilapitypes.RILCALLRTTCAP
title: RILCALLRTTCAP
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\rilcallrttcap_2.htm
old-project: netvista
ms.assetid: e1652bc1-e15d-4018-8f4c-2514958ffd27
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: "*LPRILCALLRTTCAP, RILCALLRTTCAP, RILCALLRTTCAP structure [Network Drivers Starting with Windows Vista], netvista.rilcallrttcap_2, rilapitypes/RILCALLRTTCAP"
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
-	RILCALLRTTCAP
product: Windows
targetos: Windows
req.typenames: RILCALLRTTCAP, *LPRILCALLRTTCAP
req.product: Windows 10 or later.
---

# RILCALLRTTCAP structure


## -description


This topic supports the Windows driver infrastructure and is not intended to be used directly from your code. 


## -syntax


````
typedef struct _RILCALLRTTCAP {
  RILCALLRTTMODE  dwLocalRTTCap;
  RILCALLRTTMODE  dwPeerRTTCap;
} RILCALLRTTCAP, RILCALLRTTCAP;
````


## -struct-fields




### -field dwLocalRTTCap


### -field dwPeerRTTCap

