---
UID: NS:rilapitypes.RILCALLINFO_V4
title: RILCALLINFO_V4
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\rilcallinfo_v4_2.htm
old-project: netvista
ms.assetid: c369a79d-2f54-4a00-9442-0d96c714d726
ms.author: windowsdriverdev
ms.date: 1/18/2018
ms.keywords: rilapitypes/RILCALLINFO_V4, RILCALLINFO_V4 structure [Network Drivers Starting with Windows Vista], *LPRILCALLINFO_V4, netvista.rilcallinfo_v4_2, RILCALLINFO_V4
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
-	RILCALLINFO_V4
product: Windows
targetos: Windows
req.typenames: "*LPRILCALLINFO_V4, RILCALLINFO_V4"
req.product: Windows 10 or later.
---

# RILCALLINFO_V4 structure


## -description


This topic supports the Windows driver infrastructure and is not intended to be used directly from your code. 


## -syntax


````
typedef struct _RILCALLINFO_V4 {
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
  DWORD                           dwFlags;
  RILCALLINFODISCONNECTINITIATOR  dwDisconnectInitiator;
  RILCALLINFODISCONNECTREASON     dwDisconnectReason;
  RILCALLDISCONNECTDETAILS        stDisconnectDetails;
  RILCALLMEDIAOFFERANSWERSET      rcmOfferAnswer;
  RILCALLHANDOVERSTATE            rchsHandoverState;
  RILCALLMODIFICATIONCAUSECODE    dwCallModificationCauseCode;
} RILCALLINFO_V4, RILCALLINFO_V4;
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



#### - dwFlags



#### - dwDisconnectInitiator



#### - dwDisconnectReason



#### - stDisconnectDetails



#### - rcmOfferAnswer



#### - rchsHandoverState



#### - dwCallModificationCauseCode


