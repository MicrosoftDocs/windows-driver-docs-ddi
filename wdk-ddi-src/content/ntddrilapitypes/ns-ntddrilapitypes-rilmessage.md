---
UID: NS:ntddrilapitypes.RILMESSAGE
title: RILMESSAGE
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\rilmessage.htm
old-project: netvista
ms.assetid: b776b060-79bf-4848-807d-1999d38075ad
ms.author: windowsdriverdev
ms.date: 1/18/2018
ms.keywords: "*LPRILMESSAGE, netvista.rilmessage, ntddrilapitypes/RILMESSAGE, RILMESSAGE, RILMESSAGE structure [Network Drivers Starting with Windows Vista]"
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




### -field msgUnion



### -field msgUnion.unMsgInDeliver

 


### -field msgUnion.unMsgInStatus

 


### -field msgUnion.unMsgOutSubmit

 


### -field msgUnion.unMsgBcGeneral

 


### -field msgUnion.unMsgIS637InStatus

 


### -field msgUnion.unMsgCDMAInDeliver

 


### -field msgUnion.unMsgCDMAOutSubmit

 


### -field RILMSGUNION



### -field cbSize



### -field dwParams



### -field raSvcCtrAddress



### -field dwType



### -field dwFlags



#### - unMsgInDeliver



#### - unMsgInStatus



#### - unMsgOutSubmit



#### - unMsgBcGeneral



#### - unMsgIS637InStatus



#### - unMsgCDMAInDeliver



#### - unMsgCDMAOutSubmit


