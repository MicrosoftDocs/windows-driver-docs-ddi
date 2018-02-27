---
UID: NS:rilapitypes.RILMSGINDELIVER
title: RILMSGINDELIVER
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\rilmsgindeliver_2.htm
old-project: netvista
ms.assetid: 1565ee10-044f-4557-8a49-777eae7c44e3
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: "*LPRILMSGINDELIVER, RILMSGINDELIVER, RILMSGINDELIVER structure [Network Drivers Starting with Windows Vista], netvista.rilmsgindeliver_2, rilapitypes/RILMSGINDELIVER"
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
-	RILMSGINDELIVER
product: Windows
targetos: Windows
req.typenames: RILMSGINDELIVER, *LPRILMSGINDELIVER
req.product: Windows 10 or later.
---

# RILMSGINDELIVER structure


## -description


This topic supports the Windows driver infrastructure and is not intended to be used directly from your code. 


## -syntax


````
typedef struct _RILMSGINDELIVER {
  RILADDRESS           raOrigAddress;
  RILMSGPROTOCOLID     dwProtocolID;
  RILMSGDCS            rmdDataCoding;
  RILSYSTEMTIME        stSCReceiveTime;
  DWORD                dwMsgID;
  DWORD                cbHdrLength;
  DWORD                cchMsgLength;
  BYTE [MAXLENGTH_HDR] rgbHdr;
  BYTE [MAXLENGTH_MSG] rgbMsg;
} RILMSGINDELIVER, RILMSGINDELIVER;
````


## -struct-fields




### -field raOrigAddress


### -field dwProtocolID


### -field rmdDataCoding


### -field stSCReceiveTime


### -field dwMsgID


### -field cbHdrLength


### -field cchMsgLength


### -field rgbHdr


### -field rgbMsg

