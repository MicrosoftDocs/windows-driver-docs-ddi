---
UID: NS:ntddrilapitypes.RILSUPSVCINFO
title: RILSUPSVCINFO
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\rilsupsvcinfo.htm
old-project: netvista
ms.assetid: 1f8f7c8c-f09a-4bf5-a15b-42f210122b54
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: "*LPRILSUPSVCINFO, RILSUPSVCINFO, RILSUPSVCINFO structure [Network Drivers Starting with Windows Vista], netvista.rilsupsvcinfo, ntddrilapitypes/RILSUPSVCINFO"
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
-	RILSUPSVCINFO
product: Windows
targetos: Windows
req.typenames: RILSUPSVCINFO, *LPRILSUPSVCINFO
---

# RILSUPSVCINFO structure


## -description


This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.


## -syntax


````
typedef struct _RILSUPSVCINFO {
  DWORD                            cbSize;
  DWORD                            dwParams;
  DWORD                            dwExecutor;
  DWORD                            fFromNetwork;
  DWORD                            dwFailureReason;
  RILSUPSVCACTION                  dwSupSvcAction;
  RILCALLFORWARDINGSETTINGSREASON  dwCallForwardingReason;
  RILCALLBARRINGSTATUSPARAMSTYPE   dwCallBarringType;
  RILSUPSVCTYPE                    dwSupSvcType;
  DWORD                            dwInfoClasses;
  RILALPHAIDENTIFIER               aiIdentifier;
  char [256]                       szCallBarringPassword;
  char [256]                       szNewCallBarringPassword;
  RILCALLFORWARDINGSETTINGS        callForwardSettings;
  RILCALLERIDSETTINGS              callerIdSettings;
  RILDIALEDIDSETTINGS              dialedIdSettings;
  RILHIDEIDSETTINGS                hideIdSettings;
  RILHIDECONNECTEDIDSETTINGS       hideConnectedIdSettings;
  RILSUPSERVICEDATA                supServiceData;
} RILSUPSVCINFO, RILSUPSVCINFO;
````


## -struct-fields




### -field cbSize


### -field dwParams


### -field dwExecutor


### -field fFromNetwork


### -field dwFailureReason


### -field dwSupSvcAction


### -field dwCallForwardingReason


### -field dwCallBarringType


### -field dwSupSvcType


### -field dwInfoClasses


### -field aiIdentifier


### -field szCallBarringPassword


### -field szNewCallBarringPassword


### -field callForwardSettings


### -field callerIdSettings


### -field dialedIdSettings


### -field hideIdSettings


### -field hideConnectedIdSettings


### -field supServiceData

