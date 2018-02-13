---
UID: NS:bdatypes._BDA_WMDRM_KEYINFOLIST
title: "_BDA_WMDRM_KEYINFOLIST"
author: windows-driver-content
description: "."
old-location: stream\bda_wmdrm_keyinfolist.htm
old-project: stream
ms.assetid: 0A151425-C22F-4201-855F-FF6FECE611D7
ms.author: windowsdriverdev
ms.date: 1/9/2018
ms.keywords: bdatypes/PBDA_WMDRM_KEYINFOLIST, *PBDA_WMDRM_KEYINFOLIST, stream.bda_wmdrm_keyinfolist, PBDA_WMDRM_KEYINFOLIST structure pointer [Streaming Media Devices], BDA_WMDRM_KEYINFOLIST structure [Streaming Media Devices], _BDA_WMDRM_KEYINFOLIST, PBDA_WMDRM_KEYINFOLIST, bdatypes/BDA_WMDRM_KEYINFOLIST, BDA_WMDRM_KEYINFOLIST
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
-	BDA_WMDRM_KEYINFOLIST
product: Windows
targetos: Windows
req.typenames: "*PBDA_WMDRM_KEYINFOLIST, BDA_WMDRM_KEYINFOLIST"
---

# _BDA_WMDRM_KEYINFOLIST structure


## -description





## -syntax


````
typedef struct _BDA_WMDRM_KEYINFOLIST {
  PBDARESULT lResult;
  ULONG      ulKeyuuidBufferLen;
  GUID       argKeyuuidBuffer[MIN_DIMENSION];
} BDA_WMDRM_KEYINFOLIST, *PBDA_WMDRM_KEYINFOLIST;
````


## -struct-fields




### -field lResult


### -field ulKeyuuidBufferLen


### -field argKeyuuidBuffer

