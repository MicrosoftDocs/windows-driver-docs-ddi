---
UID: NS:ntddrilapitypes.RILMESSAGE
title: RILMESSAGE
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\rilmessage.htm
old-project: netvista
ms.assetid: b776b060-79bf-4848-807d-1999d38075ad
ms.author: windowsdriverdev
ms.date: 1/11/2018
ms.keywords: RILMESSAGE, RILMESSAGE, *LPRILMESSAGE
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
req.alt-api: RILMESSAGE
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
req.typenames: RILMESSAGE, *LPRILMESSAGE
---

# RILMESSAGE structure



## -description
This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.



## -syntax

````
typedef struct _RILMESSAGE {
  DWORD                cbSize;
  DWORD                dwParams;
  RILADDRESS           raSvcCtrAddress;
  RILMESSAGETYPE       dwType;
  DWORD                dwFlags;
  NULL                 RILMSGUNION;
  RILMSGUNION          msgUnion;
  RILMSGINDELIVER      unMsgInDeliver;
  RILMSGINSTATUS       unMsgInStatus;
  RILMSGOUTSUBMIT      unMsgOutSubmit;
  RILMSGBCGENERAL      unMsgBcGeneral;
  RILMSGIS637INSTATUS  unMsgIS637InStatus;
  RILMSGCDMAINDELIVER  unMsgCDMAInDeliver;
  RILMSGCDMAOUTSUBMIT  unMsgCDMAOutSubmit;
} RILMESSAGE, RILMESSAGE;
````


## -struct-fields

### -field cbSize


### -field dwParams


### -field raSvcCtrAddress


### -field dwType


### -field dwFlags


### -field RILMSGUNION


### -field msgUnion


### -field unMsgInDeliver


### -field unMsgInStatus


### -field unMsgOutSubmit


### -field unMsgBcGeneral


### -field unMsgIS637InStatus


### -field unMsgCDMAInDeliver


### -field unMsgCDMAOutSubmit


## -remarks
