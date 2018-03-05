---
UID: NS:rilapitypes.RILSENDMSGRESPONSE
title: RILSENDMSGRESPONSE
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\rilsendmsgresponse_2.htm
old-project: netvista
ms.assetid: 46fd1e3e-38de-460e-8bb8-ff7db2a16e1a
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: "*LPRILSENDMSGRESPONSE, RILSENDMSGRESPONSE, RILSENDMSGRESPONSE structure [Network Drivers Starting with Windows Vista], netvista.rilsendmsgresponse_2, rilapitypes/RILSENDMSGRESPONSE"
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
-	RILSENDMSGRESPONSE
product: Windows
targetos: Windows
req.typenames: RILSENDMSGRESPONSE, *LPRILSENDMSGRESPONSE
req.product: Windows 10 or later.
---

# RILSENDMSGRESPONSE structure


## -description


This topic supports the Windows driver infrastructure and is not intended to be used directly from your code. 


## -syntax


````
typedef struct _RILSENDMSGRESPONSE {
  DWORD    cbSize;
  DWORD    dwParams;
  HRESULT  hrReturn;
  DWORD    dwCDMACauseCode;
  DWORD    dwCDMAErrorClass;
  DWORD    dwGWLTransportCode;
  DWORD    dwGWLRelayCode;
  DWORD    dwMsgID;
} RILSENDMSGRESPONSE, RILSENDMSGRESPONSE;
````


## -struct-fields




### -field cbSize


### -field dwParams


### -field hrReturn


### -field dwCDMACauseCode


### -field dwCDMAErrorClass


### -field dwGWLTransportCode


### -field dwGWLRelayCode


### -field dwMsgID

