---
UID: NS:bdatypes._BDA_ISDBCAS_REQUESTHEADER
title: "_BDA_ISDBCAS_REQUESTHEADER"
author: windows-driver-content
description: "."
old-location: stream\bda_isdbcas_requestheader.htm
old-project: stream
ms.assetid: E83111C1-5A46-4AB4-B54C-F8330943070D
ms.author: windowsdriverdev
ms.date: 2/22/2018
ms.keywords: ",  , *, *PBDA_ISDBCAS_REQUESTHEADER, ,, A, B, BDA_ISDBCAS_REQUESTHEADER, BDA_ISDBCAS_REQUESTHEADER structure [Streaming Media Devices], C, D, E, H, I, P, PBDA_ISDBCAS_REQUESTHEADER, PBDA_ISDBCAS_REQUESTHEADER structure pointer [Streaming Media Devices], Q, R, S, T, U, _, _BDA_ISDBCAS_REQUESTHEADER, bdatypes/BDA_ISDBCAS_REQUESTHEADER, bdatypes/PBDA_ISDBCAS_REQUESTHEADER, stream.bda_isdbcas_requestheader"
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
-	BDA_ISDBCAS_REQUESTHEADER
product: Windows
targetos: Windows
req.typenames: BDA_ISDBCAS_REQUESTHEADER, *PBDA_ISDBCAS_REQUESTHEADER
---

# _BDA_ISDBCAS_REQUESTHEADER structure


## -description





## -syntax


````
typedef struct _BDA_ISDBCAS_REQUESTHEADER {
  BYTE  bInstruction;
  BYTE  bReserved[3];
  ULONG ulDataLength;
  BYTE  argbIsdbCommand[MIN_DIMENSION];
} BDA_ISDBCAS_REQUESTHEADER, *PBDA_ISDBCAS_REQUESTHEADER;
````


## -struct-fields




### -field bInstruction

EMD/EMG


### -field bReserved

Reserved for future use.


### -field ulDataLength

Specifies the size in bytes of the <b>argbIsdbCommand</b> member.


### -field argbIsdbCommand

