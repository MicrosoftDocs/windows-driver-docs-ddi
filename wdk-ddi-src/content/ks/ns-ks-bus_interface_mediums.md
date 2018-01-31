---
UID: NS:ks.BUS_INTERFACE_MEDIUMS
title: BUS_INTERFACE_MEDIUMS
author: windows-driver-content
description: "."
old-location: stream\bus_interface_mediums.htm
old-project: stream
ms.assetid: 0A2D1D8F-8C82-4335-9FBF-4515A8DC20C1
ms.author: windowsdriverdev
ms.date: 1/9/2018
ms.keywords: stream.bus_interface_mediums, PBUS_INTERFACE_MEDIUMS structure pointer [Streaming Media Devices], *PBUS_INTERFACE_MEDIUMS, ks/BUS_INTERFACE_MEDIUMS, BUS_INTERFACE_MEDIUMS structure [Streaming Media Devices], PBUS_INTERFACE_MEDIUMS, BUS_INTERFACE_MEDIUMS, ks/PBUS_INTERFACE_MEDIUMS
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: ks.h
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
-	Ks.h
apiname:
-	BUS_INTERFACE_MEDIUMS
product: Windows
targetos: Windows
req.typenames: "*PBUS_INTERFACE_MEDIUMS, BUS_INTERFACE_MEDIUMS"
---

# BUS_INTERFACE_MEDIUMS structure


## -description





## -syntax


````
typedef struct {
  INTERFACE           Interface;
  PFNQUERYMEDIUMSLIST QueryMediumsList;
} BUS_INTERFACE_MEDIUMS, *PBUS_INTERFACE_MEDIUMS;
````


## -struct-fields




#### - Interface

Specifies the standard interface header.


#### - QueryMediumsList

Specifies the interface definition.

