---
UID: NS:rilapitypes.RILCALLINFO_V1
title: RILCALLINFO_V1
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\rilcallinfo_v1_2.htm
old-project: netvista
ms.assetid: f630afff-d3ca-4ada-aa8c-5062893f2de5
ms.author: windowsdriverdev
ms.date: 1/18/2018
ms.keywords: RILCALLINFO_V1, *LPRILCALLINFO_V1, rilapitypes/RILCALLINFO_V1, netvista.rilcallinfo_v1_2, RILCALLINFO_V1 structure [Network Drivers Starting with Windows Vista]
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
-	RILCALLINFO_V1
product: Windows
targetos: Windows
req.typenames: RILCALLINFO_V1, *LPRILCALLINFO_V1
req.product: Windows 10 or later.
---

# RILCALLINFO_V1 structure


## -description


This topic supports the Windows driver infrastructure and is not intended to be used directly from your code. 


## -syntax


````
typedef struct _RILCALLINFO_V1 {
  DWORD                           cbSize;
  DWORD                           dwParams;
  DWORD                           dwExecutor;
  DWORD                           dwID;
  RILCALLINFODIRECTION            dwDirection;
  RILCALLINFOSTATUS               dwStatus;
  RILCALLTYPE                     dwType;
  RILCALLINFOMULTIPARTY           dwMultiparty;
  RILADDRESS                      raAddress;
  RILSUBADDRESS                   rsaSubAddress;
  WCHAR [MAXLENGTH_DESCRIPTION]   wszDescription;
  RILREMOTEPARTYINFOVALUE         dwNumberPresentationIndicator;
  RILREMOTEPARTYINFOVALUE         dwNamePresentationIndicator;
  BOOL                            fAlienCall;
  RILCALLINFODISCONNECTINITIATOR  dwDisconnectInitiator;
  RILCALLINFODISCONNECTREASON     dwDisconnectReason;
  RILCALLDISCONNECTDETAILS        stDisconnectDetails;
} RILCALLINFO_V1, RILCALLINFO_V1;
````


## -struct-fields




#### - cbSize



#### - dwParams



#### - dwExecutor



#### - dwID



#### - dwDirection



#### - dwStatus



#### - dwType



#### - dwMultiparty



#### - raAddress



#### - rsaSubAddress



#### - wszDescription



#### - dwNumberPresentationIndicator



#### - dwNamePresentationIndicator



#### - fAlienCall



#### - dwDisconnectInitiator



#### - dwDisconnectReason



#### - stDisconnectDetails


