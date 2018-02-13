---
UID: NS:ntddrilapitypes.RILMSGINSTATUS
title: RILMSGINSTATUS
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\rilmsginstatus.htm
old-project: netvista
ms.assetid: 383ed544-c8c8-42a0-a7de-57f0f4072611
ms.author: windowsdriverdev
ms.date: 1/18/2018
ms.keywords: ntddrilapitypes/RILMSGINSTATUS, RILMSGINSTATUS, *LPRILMSGINSTATUS, netvista.rilmsginstatus, RILMSGINSTATUS structure [Network Drivers Starting with Windows Vista]
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
-	RILMSGINSTATUS
product: Windows
targetos: Windows
req.typenames: "*LPRILMSGINSTATUS, RILMSGINSTATUS"
---

# RILMSGINSTATUS structure


## -description


This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.


## -syntax


````
typedef struct _RILMSGINSTATUS {
  DWORD                       dwMsgID;
  RILADDRESS                  raTgtRecipAddress;
  RILSYSTEMTIME               stTgtSCReceiveTime;
  RILSYSTEMTIME               stTgtDischargeTime;
  DWORD                       dwReserved;
  RILMSGINSTATUSTGTDLVSTATUS  dwTgtDlvStatus;
  RILMSGPROTOCOLID            dwProtocolID;
  RILMSGDCS                   rmdDataCoding;
  DWORD                       cbHdrLength;
  DWORD                       cchMsgLength;
  BYTE [256]                  rgbHdr;
  BYTE [512]                  rgbMsg;
} RILMSGINSTATUS, RILMSGINSTATUS;
````


## -struct-fields




### -field dwMsgID


### -field raTgtRecipAddress


### -field stTgtSCReceiveTime


### -field stTgtDischargeTime


### -field dwReserved


### -field dwTgtDlvStatus


### -field dwProtocolID


### -field rmdDataCoding


### -field cbHdrLength


### -field cchMsgLength


### -field rgbHdr


### -field rgbMsg

