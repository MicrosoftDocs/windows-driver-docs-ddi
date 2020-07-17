---
UID: NF:ks.KsCacheMedium
title: KsCacheMedium function (ks.h)
description: The KsCacheMedium function improves graph building performance of pins that use Mediums to define connectivity.
old-location: stream\kscachemedium.htm
tech.root: stream
ms.assetid: d0e9c146-5d73-49e8-92a8-c453f5bbbfe9
ms.date: 04/23/2018
keywords: ["KsCacheMedium function"]
ms.keywords: KsCacheMedium, KsCacheMedium function [Streaming Media Devices], ks/KsCacheMedium, ksfunc_19ac113f-3eb8-4073-90b0-786cc82cdf37.xml, stream.kscachemedium
f1_keywords:
 - "ks/KsCacheMedium"
 - "KsCacheMedium"
req.header: ks.h
req.include-header: Ks.h
req.target-type: Universal
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
req.lib: Ks.lib
req.dll: 
req.irql: 
topic_type:
- APIRef
- kbSyntax
api_type:
- LibDef
api_location:
- Ks.lib
- Ks.dll
api_name:
- KsCacheMedium
product:
- Windows
targetos: Windows
req.typenames: 
---

# KsCacheMedium function


## -description


The <b>KsCacheMedium</b> function improves graph building performance of pins that use Mediums to define connectivity.


## -parameters




### -param SymbolicLink [in]

The symbolic link used to open the device interface.


### -param Medium [in]

Points to the medium to cache.


### -param PinDirection [in]

Contains the direction of the Pin.  1 is output, 0 is input.


## -returns



<b>KsCacheMedium</b> returns STATUS_SUCCESS if the caching operation is successful, failure if it is not.




## -remarks



<b>KsCacheMedium</b> improves graph building performance by creating a registry key at: 

<b>\System\CurrentControlSet\Control\MediumCache\GUID\DWORD\DWORD </b>

This enables fast lookup of connected filters in TvTuner and other complex graphs.  Note that the GUID identifies the Medium of the connection, and that the DWORDs denote the device instance.  The value name is the SymbolicLink for the driver, and ActualValue is the pin direction.turning. 



