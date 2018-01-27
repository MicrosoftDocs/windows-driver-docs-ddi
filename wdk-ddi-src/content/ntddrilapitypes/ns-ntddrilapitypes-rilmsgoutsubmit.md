---
UID: NS:ntddrilapitypes.RILMSGOUTSUBMIT
title: RILMSGOUTSUBMIT
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\rilmsgoutsubmit.htm
old-project: netvista
ms.assetid: 83d15e40-b93f-4c7a-bfe4-db939c24b94f
ms.author: windowsdriverdev
ms.date: 1/18/2018
ms.keywords: ntddrilapitypes/RILMSGOUTSUBMIT, *LPRILMSGOUTSUBMIT, RILMSGOUTSUBMIT structure [Network Drivers Starting with Windows Vista], netvista.rilmsgoutsubmit, RILMSGOUTSUBMIT
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
-	RILMSGOUTSUBMIT
product: Windows
targetos: Windows
req.typenames: RILMSGOUTSUBMIT, *LPRILMSGOUTSUBMIT
---

# RILMSGOUTSUBMIT structure


## -description


This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.


## -syntax


````
typedef struct _RILMSGOUTSUBMIT {
  RILADDRESS               raDestAddress;
  RILMSGPROTOCOLID         dwProtocolID;
  RILMSGDCS                rmdDataCoding;
  RILMSGOUTSUBMITVPFORMAT  dwVPFormat;
  RILSYSTEMTIME            stVP;
  DWORD                    dwMsgID;
  DWORD                    cbHdrLength;
  DWORD                    cchMsgLength;
  BYTE [256]               rgbHdr;
  BYTE [512]               rgbMsg;
} RILMSGOUTSUBMIT, RILMSGOUTSUBMIT;
````


## -struct-fields




### -field raDestAddress



### -field dwProtocolID



### -field rmdDataCoding



### -field dwVPFormat



### -field stVP



### -field dwMsgID



### -field cbHdrLength



### -field cchMsgLength



### -field rgbHdr



### -field rgbMsg


