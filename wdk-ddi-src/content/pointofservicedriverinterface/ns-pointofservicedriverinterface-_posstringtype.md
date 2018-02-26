---
UID: NS:pointofservicedriverinterface._PosStringType
title: "_PosStringType"
author: windows-driver-content
description: This structure represents a Point of Service (POS) unicode string with a length of DataLengthInBytes.
old-location: pos\posstringtype.htm
old-project: pos
ms.assetid: 26cf79d7-1df3-40a3-8536-b672f9bf13a8
ms.author: windowsdriverdev
ms.date: 2/23/2018
ms.keywords: ",  , ,, P, PosStringType, PosStringType structure, S, T, _, _PosStringType, e, g, i, n, o, p, pointofservicedriverinterface/PosStringType, pos.posstringtype, r, s, t, y"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: pointofservicedriverinterface.h
req.include-header: PointOfServiceDriverInterface.h
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
-	PointOfServiceDriverInterface.h
apiname:
-	PosStringType
product: Windows
targetos: Windows
req.typenames: PosStringType
---

# _PosStringType structure


## -description


This structure represents a Point of Service (POS) unicode string with a length of <i>DataLengthInBytes</i>.


## -syntax


````
typedef struct _PosStringType {
  UINT32 DataLengthInBytes;
} PosStringType;
````


## -struct-fields




### -field DataLengthInBytes

The length of the string in bytes.


## -remarks



The string is Unicode and the contents of the string follow immediately after the PosStringType structure.



