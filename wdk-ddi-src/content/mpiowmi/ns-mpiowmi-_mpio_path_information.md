---
UID: NS:mpiowmi._MPIO_PATH_INFORMATION
title: "_MPIO_PATH_INFORMATION"
author: windows-driver-content
description: The MPIO_PATH_INFORMATION structure represents a top-level view of all the paths that are under MPIO control. To query the path information, the request must be sent to the MPIO control object by using its WMI instance name.
old-location: storage\mpio_path_information.htm
old-project: storage
ms.assetid: 12383ae0-69c8-4546-9560-08aa4a50de8e
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: "*PMPIO_PATH_INFORMATION, MPIO_PATH_INFORMATION, MPIO_PATH_INFORMATION structure [Storage Devices], PMPIO_PATH_INFORMATION, PMPIO_PATH_INFORMATION structure pointer [Storage Devices], _MPIO_PATH_INFORMATION, mpiowmi/MPIO_PATH_INFORMATION, mpiowmi/PMPIO_PATH_INFORMATION, storage.mpio_path_information, structs-scsibus_2000c93b-2c86-478c-a70e-89622ca40862.xml"
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
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	mpiowmi.h
api_name:
-	MPIO_PATH_INFORMATION
product: Windows
targetos: Windows
req.typenames: MPIO_PATH_INFORMATION, *PMPIO_PATH_INFORMATION
---

# _MPIO_PATH_INFORMATION structure


## -description


The MPIO_PATH_INFORMATION structure represents a top-level view of all the paths that are under MPIO control. To query the path information, the request must be sent to the MPIO control object by using its WMI instance name.


## -struct-fields




### -field NumberPaths

An unsigned 32-bitfield that represents the total number of paths that MPIO is aware of.


### -field Pad

Should be zero.


### -field PathList

An array that returns information about each of the paths. The number of elements in the array is given by <i>NumberPaths</i> and each element of the array represents an instance of an MPIO_ADAPTER_INFORMATION structure.

