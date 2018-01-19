---
UID: NS:ks._KSPROPERTY_GRAPHMANAGER_INTERFACE
title: _KSPROPERTY_GRAPHMANAGER_INTERFACE
author: windows-driver-content
description: .
old-location: stream\ksproperty_graphmanager_interface.htm
old-project: stream
ms.assetid: CC2A3E78-0A28-4760-A4E1-A2C600CE03CB
ms.author: windowsdriverdev
ms.date: 1/9/2018
ms.keywords: _KSPROPERTY_GRAPHMANAGER_INTERFACE, *PKSPROPERTY_GRAPHMANAGER_INTERFACE, KSPROPERTY_GRAPHMANAGER_INTERFACE
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
req.alt-api: KSPROPERTY_GRAPHMANAGER_INTERFACE
req.alt-loc: Ks.h
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
req.typenames: *PKSPROPERTY_GRAPHMANAGER_INTERFACE, KSPROPERTY_GRAPHMANAGER_INTERFACE
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

### -field GraphManager


### -field FunctionTable


## -remarks
