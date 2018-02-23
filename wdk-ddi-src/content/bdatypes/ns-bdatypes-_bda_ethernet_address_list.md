---
UID: NS:bdatypes._BDA_ETHERNET_ADDRESS_LIST
title: "_BDA_ETHERNET_ADDRESS_LIST"
author: windows-driver-content
description: "."
old-location: stream\bda_ethernet_address_list.htm
old-project: stream
ms.assetid: 2985A0EC-4B5F-43FA-A2E9-487877A3C9A0
ms.author: windowsdriverdev
ms.date: 2/22/2018
ms.keywords: "*PBDA_ETHERNET_ADDRESS_LIST, stream.bda_ethernet_address_list, BDA_ETHERNET_ADDRESS_LIST structure [Streaming Media Devices], PBDA_ETHERNET_ADDRESS_LIST, _BDA_ETHERNET_ADDRESS_LIST, bdatypes/BDA_ETHERNET_ADDRESS_LIST, BDA_ETHERNET_ADDRESS_LIST, bdatypes/PBDA_ETHERNET_ADDRESS_LIST, PBDA_ETHERNET_ADDRESS_LIST structure pointer [Streaming Media Devices]"
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
-	BDA_ETHERNET_ADDRESS_LIST
product: Windows
targetos: Windows
req.typenames: BDA_ETHERNET_ADDRESS_LIST, *PBDA_ETHERNET_ADDRESS_LIST
---

# _BDA_ETHERNET_ADDRESS_LIST structure


## -description





## -syntax


````
typedef struct _BDA_ETHERNET_ADDRESS_LIST {
  ULONG                ulcAddresses;
  BDA_ETHERNET_ADDRESS rgAddressl[MIN_DIMENSION];
} BDA_ETHERNET_ADDRESS_LIST, *PBDA_ETHERNET_ADDRESS_LIST;
````


## -struct-fields




### -field ulcAddresses


### -field rgAddressl

