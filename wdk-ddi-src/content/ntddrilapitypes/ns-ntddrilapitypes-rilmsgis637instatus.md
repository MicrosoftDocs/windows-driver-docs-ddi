---
UID: NS:ntddrilapitypes.RILMSGIS637INSTATUS
title: RILMSGIS637INSTATUS
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\rilmsgis637instatus.htm
old-project: netvista
ms.assetid: ba87baa2-7d96-4418-bfbc-411bb4cda3fb
ms.author: windowsdriverdev
ms.date: 1/18/2018
ms.keywords: ntddrilapitypes/RILMSGIS637INSTATUS, *LPRILMSGIS637INSTATUS, netvista.rilmsgis637instatus, RILMSGIS637INSTATUS structure [Network Drivers Starting with Windows Vista], RILMSGIS637INSTATUS
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
-	RILMSGIS637INSTATUS
product: Windows
targetos: Windows
req.typenames: "*LPRILMSGIS637INSTATUS, RILMSGIS637INSTATUS"
---

# RILMSGIS637INSTATUS structure


## -description


This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.


## -syntax


````
typedef struct _RILMSGIS637INSTATUS {
  RILADDRESS               raOrigAddress;
  RILSUBADDRESS            rsaOrigSubaddr;
  RILSYSTEMTIME            stSCReceiveTime;
  DWORD                    dwCauseCode;
  DWORD                    dwReplySeqNumber;
  DWORD                    dwUserResponseCode;
  RILMSGCDMAMSGSTATUSTYPE  dwMsgStatusType;
  DWORD                    dwMsgID;
  RILMSGCDMALANGUAGE       dwMsgLang;
  RILMSGCDMAMSGENCODING    dwMsgEncoding;
  DWORD                    cchMsgLength;
  BYTE [512]               rgbMsg;
} RILMSGIS637INSTATUS, RILMSGIS637INSTATUS;
````


## -struct-fields




### -field raOrigAddress


### -field rsaOrigSubaddr


### -field stSCReceiveTime


### -field dwCauseCode


### -field dwReplySeqNumber


### -field dwUserResponseCode


### -field dwMsgStatusType


### -field dwMsgID


### -field dwMsgLang


### -field dwMsgEncoding


### -field cchMsgLength


### -field rgbMsg

