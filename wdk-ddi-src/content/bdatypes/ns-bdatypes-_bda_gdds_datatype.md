---
UID: NS:bdatypes._BDA_GDDS_DATATYPE
title: "_BDA_GDDS_DATATYPE"
author: windows-driver-content
description: "."
old-location: stream\bda_gdds_datatype.htm
old-project: stream
ms.assetid: D2E6A110-EC0F-4753-BAF1-7A9F84ECDD35
ms.author: windowsdriverdev
ms.date: 1/9/2018
ms.keywords: BDA_GDDS_DATATYPE, stream.bda_gdds_datatype, *P_BDA_GDDS_DATATYPE, P_BDA_GDDS_DATATYPE, _BDA_GDDS_DATATYPE, P_BDA_GDDS_DATATYPE structure pointer [Streaming Media Devices], bdatypes/BDA_GDDS_DATATYPE, BDA_GDDS_DATATYPE structure [Streaming Media Devices], bdatypes/P_BDA_GDDS_DATATYPE
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
-	BDA_GDDS_DATATYPE
product: Windows
targetos: Windows
req.typenames: BDA_GDDS_DATATYPE, *P_BDA_GDDS_DATATYPE
---

# _BDA_GDDS_DATATYPE structure


## -description





## -syntax


````
typedef struct _BDA_GDDS_DATATYPE {
  PBDARESULT lResult;
  GUID       uuidDataType;
} BDA_GDDS_DATATYPE, *P_BDA_GDDS_DATATYPE;
````


## -struct-fields




### -field lResult



### -field uuidDataType


