---
UID: NS:ntddrilapitypes.RILMESSAGE
title: RILMESSAGE
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\rilmessage.htm
old-project: netvista
ms.assetid: b776b060-79bf-4848-807d-1999d38075ad
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: ntddrilapitypes/RILMESSAGE, RILMESSAGE, *LPRILMESSAGE, RILMESSAGE structure [Network Drivers Starting with Windows Vista], netvista.rilmessage
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
-	RILMESSAGE
product: Windows
targetos: Windows
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


### -field msgUnion


### -field RILMSGUNION


#### - unMsgBcGeneral


#### - unMsgCDMAInDeliver


#### - unMsgCDMAOutSubmit


#### - unMsgIS637InStatus


#### - unMsgInDeliver


#### - unMsgInStatus


#### - unMsgOutSubmit

