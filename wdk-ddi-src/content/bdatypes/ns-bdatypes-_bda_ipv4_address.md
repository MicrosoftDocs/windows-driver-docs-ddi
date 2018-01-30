---
UID: NS:bdatypes._BDA_IPv4_ADDRESS
title: "_BDA_IPv4_ADDRESS"
author: windows-driver-content
description: "."
old-location: stream\bda_ipv4_address.htm
old-project: stream
ms.assetid: 5206CEEB-C1EF-4AE0-B4BC-52E8D85AD706
ms.author: windowsdriverdev
ms.date: 1/9/2018
ms.keywords: BDA_IPv4_ADDRESS, BDA_IPv4_ADDRESS structure [Streaming Media Devices], bdatypes/PBDA_IPv4_ADDRESS, stream.bda_ipv4_address, PBDA_IPv4_ADDRESS structure pointer [Streaming Media Devices], PBDA_IPv4_ADDRESS, bdatypes/BDA_IPv4_ADDRESS, _BDA_IPv4_ADDRESS, *PBDA_IPv4_ADDRESS
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
-	BDA_IPv4_ADDRESS
product: Windows
targetos: Windows
req.typenames: "*PBDA_IPv4_ADDRESS, BDA_IPv4_ADDRESS"
---

# _BDA_IPv4_ADDRESS structure


## -description





## -syntax


````
typedef struct _BDA_IPv4_ADDRESS {
  BYTE rgbAddress[4];
} BDA_IPv4_ADDRESS, *PBDA_IPv4_ADDRESS;
````


## -struct-fields




### -field rgbAddress


