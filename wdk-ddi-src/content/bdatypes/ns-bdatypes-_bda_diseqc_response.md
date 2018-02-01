---
UID: NS:bdatypes._BDA_DISEQC_RESPONSE
title: "_BDA_DISEQC_RESPONSE"
author: windows-driver-content
description: "."
old-location: stream\bda_diseqc_response.htm
old-project: stream
ms.assetid: 724FD17B-D12B-423D-AA0E-93D9D31DC93E
ms.author: windowsdriverdev
ms.date: 1/9/2018
ms.keywords: PBDA_DISEQC_RESPONSE, *PBDA_DISEQC_RESPONSE, bdatypes/BDA_DISEQC_RESPONSE, bdatypes/PBDA_DISEQC_RESPONSE, _BDA_DISEQC_RESPONSE, PBDA_DISEQC_RESPONSE structure pointer [Streaming Media Devices], stream.bda_diseqc_response, BDA_DISEQC_RESPONSE, BDA_DISEQC_RESPONSE structure [Streaming Media Devices]
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: bdatypes.h
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
req.irql: PASSIVE_LEVEL
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	Bdatypes.h
apiname:
-	BDA_DISEQC_RESPONSE
product: Windows
targetos: Windows
req.typenames: BDA_DISEQC_RESPONSE, *PBDA_DISEQC_RESPONSE
---

# _BDA_DISEQC_RESPONSE structure


## -description





## -syntax


````
typedef struct _BDA_DISEQC_RESPONSE {
  ULONG ulRequestId;
  ULONG ulPacketLength;
  BYTE  argbPacketData[8];
} BDA_DISEQC_RESPONSE, *PBDA_DISEQC_RESPONSE;
````


## -struct-fields




### -field ulRequestId



### -field ulPacketLength



### -field argbPacketData


