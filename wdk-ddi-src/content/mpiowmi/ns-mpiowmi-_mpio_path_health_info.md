---
UID: NS:mpiowmi._MPIO_PATH_HEALTH_INFO
title: _MPIO_PATH_HEALTH_INFO (mpiowmi.h)
description: The MPIO_PATH_HEALTH_INFO structure is used to query the available health information for every path that is exposed to the system.
old-location: storage\mpio_path_health_info.htm
tech.root: storage
ms.assetid: efb49852-3c0a-4dab-9d50-c103ba4a136b
ms.date: 03/29/2018
ms.keywords: "*PMPIO_PATH_HEALTH_INFO, MPIO_PATH_HEALTH_INFO, MPIO_PATH_HEALTH_INFO structure [Storage Devices], PMPIO_PATH_HEALTH_INFO, PMPIO_PATH_HEALTH_INFO structure pointer [Storage Devices], _MPIO_PATH_HEALTH_INFO, mpiowmi/MPIO_PATH_HEALTH_INFO, mpiowmi/PMPIO_PATH_HEALTH_INFO, storage.mpio_path_health_info, structs-scsibus_482617c5-3ed9-4a17-ab14-15fc65057062.xml"
ms.topic: struct
f1_keywords:
 - "mpiowmi/MPIO_PATH_HEALTH_INFO"
req.header: mpiowmi.h
req.include-header: Mpiowmi.h
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
topic_type:
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- mpiowmi.h
api_name:
- MPIO_PATH_HEALTH_INFO
product:
- Windows
targetos: Windows
req.typenames: MPIO_PATH_HEALTH_INFO, *PMPIO_PATH_HEALTH_INFO
---

# _MPIO_PATH_HEALTH_INFO structure


## -description


The MPIO_PATH_HEALTH_INFO structure is used to query the available health information for every path that is exposed to the system.


## -struct-fields




### -field NumberPathPackets

An unsigned 32-bitfield that returns the number of health packets available that correspond to the number of available paths under MPIO control.


### -field Reserved

Should be zero.


### -field PathHealthPackets

A field that contains an array with health information about all the available paths under MPIO control. The number of elements of the array is given by NumberPathPackets and each element of the array is an instance of the MPIO_PATH_HEALTH_CLASS structure.

