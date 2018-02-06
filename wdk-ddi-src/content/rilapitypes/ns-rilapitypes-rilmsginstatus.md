---
UID: NS:rilapitypes.RILMSGINSTATUS
title: RILMSGINSTATUS
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\rilmsginstatus_2.htm
old-project: netvista
ms.assetid: 4dcc198f-5e42-4c60-bfec-19702c9ab674
ms.author: windowsdriverdev
ms.date: 1/18/2018
ms.keywords: RILMSGINSTATUS, rilapitypes/RILMSGINSTATUS, *LPRILMSGINSTATUS, RILMSGINSTATUS structure [Network Drivers Starting with Windows Vista], netvista.rilmsginstatus_2
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
-	RILMSGINSTATUS
product: Windows
targetos: Windows
req.typenames: "*LPRILMSGINSTATUS, RILMSGINSTATUS"
req.product: Windows 10 or later.
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
  BYTE [MAXLENGTH_HDR]        rgbHdr;
  BYTE [MAXLENGTH_MSG]        rgbMsg;
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


