---
UID: NS:mpiowmi._GetPathConfiguration_IN
title: _GetPathConfiguration_IN
author: windows-driver-content
description: The GetPathConfiguration_IN structure is used to retrieve the per path device information.
old-location: storage\getpathconfiguration_in.htm
old-project: storage
ms.assetid: 38396f75-6bcf-493e-9aab-661db59637ae
ms.author: windowsdriverdev
ms.date: 1/10/2018
ms.keywords: _GetPathConfiguration_IN, *PGetPathConfiguration_IN, GetPathConfiguration_IN
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: mpiowmi.h
req.include-header: Mpiowmi.h
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: GetPathConfiguration_IN
req.alt-loc: mpiowmi.h
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
req.typenames: *PGetPathConfiguration_IN, GetPathConfiguration_IN
---

# _GetPathConfiguration_IN structure



## -description
The GetPathConfiguration_IN structure is used to retrieve the per path device information.



## -syntax

````
typedef struct _GetPathConfiguration_IN {
  ULONGLONG PathID;
} GetPathConfiguration_IN, *PGetPathConfiguration_IN;
````


## -struct-fields

### -field PathID

A 64-bitfield that specifies the path that is associated with the device.


## -remarks
