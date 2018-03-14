---
UID: NS:ntddrilapitypes.RILMSGBCGENERAL
title: RILMSGBCGENERAL
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\rilmsgbcgeneral.htm
old-project: netvista
ms.assetid: d1570dc0-1587-4d02-a655-724c999d10a2
ms.author: windowsdriverdev
ms.date: 2/27/2018
ms.keywords: "*LPRILMSGBCGENERAL, RILMSGBCGENERAL, RILMSGBCGENERAL structure [Network Drivers Starting with Windows Vista], netvista.rilmsgbcgeneral, ntddrilapitypes/RILMSGBCGENERAL"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: ntddrilapitypes.h
req.include-header: Rilapitypes.h
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
-	ntddrilapitypes.h
api_name:
-	RILMSGBCGENERAL
product: Windows
targetos: Windows
req.typenames: RILMSGBCGENERAL, *LPRILMSGBCGENERAL
---

# RILMSGBCGENERAL structure


## -description


This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.


## -syntax


````
typedef struct _RILMSGBCGENERAL {
  RILGEOSCOPE                 dwGeoScope;
  DWORD                       dwMsgCode;
  DWORD                       dwUpdateNumber;
  DWORD                       dwID;
  DWORD                       dwSerialNumber;
  RILMSGDCS                   rmdDataCoding;
  DWORD                       dwTotalPages;
  DWORD                       dwPageNumber;
  RILMSGBCGENERALWARNINGTYPE  dwWarningType;
  BOOL                        bEmergencyUserAlert;
  BOOL                        bMessagePopup;
  RILSYSTEMTIME               stSCReceiveTime;
  BYTE [43]                   digSig;
  DWORD                       cchMsgLength;
  BYTE [512]                  rgbMsg;
} RILMSGBCGENERAL, RILMSGBCGENERAL;
````


## -struct-fields




### -field dwGeoScope


### -field dwMsgCode


### -field dwUpdateNumber


### -field dwID


### -field dwSerialNumber


### -field rmdDataCoding


### -field dwTotalPages


### -field dwPageNumber


### -field dwWarningType


### -field bEmergencyUserAlert


### -field bMessagePopup


### -field stSCReceiveTime


### -field digSig


### -field cchMsgLength


### -field rgbMsg

