---
UID: NS:ntddrilapitypes.RILMSGBCGENERAL
title: RILMSGBCGENERAL
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\rilmsgbcgeneral.htm
old-project: netvista
ms.assetid: d1570dc0-1587-4d02-a655-724c999d10a2
ms.author: windowsdriverdev
ms.date: 1/11/2018
ms.keywords: RILMSGBCGENERAL, *LPRILMSGBCGENERAL, RILMSGBCGENERAL
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
req.alt-api: RILMSGBCGENERAL
req.alt-loc: ntddrilapitypes.h
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
req.typenames: *LPRILMSGBCGENERAL, RILMSGBCGENERAL
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


## -remarks
