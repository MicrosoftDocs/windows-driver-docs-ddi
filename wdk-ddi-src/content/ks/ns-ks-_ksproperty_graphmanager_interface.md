---
UID: NS:ks._KSPROPERTY_GRAPHMANAGER_INTERFACE
title: "_KSPROPERTY_GRAPHMANAGER_INTERFACE"
author: windows-driver-content
description: "."
old-location: stream\ksproperty_graphmanager_interface.htm
old-project: stream
ms.assetid: CC2A3E78-0A28-4760-A4E1-A2C600CE03CB
ms.author: windowsdriverdev
ms.date: 1/9/2018
ms.keywords: ks/PKSPROPERTY_GRAPHMANAGER_INTERFACE, *PKSPROPERTY_GRAPHMANAGER_INTERFACE, PKSPROPERTY_GRAPHMANAGER_INTERFACE structure pointer [Streaming Media Devices], stream.ksproperty_graphmanager_interface, ks/KSPROPERTY_GRAPHMANAGER_INTERFACE, _KSPROPERTY_GRAPHMANAGER_INTERFACE, KSPROPERTY_GRAPHMANAGER_INTERFACE, PKSPROPERTY_GRAPHMANAGER_INTERFACE, KSPROPERTY_GRAPHMANAGER_INTERFACE structure [Streaming Media Devices]
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
-	KSPROPERTY_GRAPHMANAGER_INTERFACE
product: Windows
targetos: Windows
req.typenames: KSPROPERTY_GRAPHMANAGER_INTERFACE, *PKSPROPERTY_GRAPHMANAGER_INTERFACE
---

# _KSPROPERTY_GRAPHMANAGER_INTERFACE structure


## -description





## -syntax


````
typedef struct _KSPROPERTY_GRAPHMANAGER_INTERFACE {
  PFILE_OBJECT                 GraphManager;
  KSGRAPHMANAGER_FUNCTIONTABLE FunctionTable;
} KSPROPERTY_GRAPHMANAGER_INTERFACE, *PKSPROPERTY_GRAPHMANAGER_INTERFACE;
````


## -struct-fields




#### - GraphManager



#### - FunctionTable


