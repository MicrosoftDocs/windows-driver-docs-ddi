---
UID: NS:mpiodisk._MPIO_GET_DESCRIPTOR
title: _MPIO_GET_DESCRIPTOR (mpiodisk.h)
description: The MPIO_GET_DESCRIPTOR structure is used to query for LUN instances that correspond to various paths.
old-location: storage\mpio_get_descriptor.htm
tech.root: storage
ms.assetid: cabd2a6d-20d0-4499-8494-7ad746f2d915
ms.date: 03/29/2018
ms.keywords: "*PMPIO_GET_DESCRIPTOR, MPIO_GET_DESCRIPTOR, MPIO_GET_DESCRIPTOR structure [Storage Devices], PMPIO_GET_DESCRIPTOR, PMPIO_GET_DESCRIPTOR structure pointer [Storage Devices], _MPIO_GET_DESCRIPTOR, mpiodisk/MPIO_GET_DESCRIPTOR, mpiodisk/PMPIO_GET_DESCRIPTOR, storage.mpio_get_descriptor, structs-scsibus_4d648295-24f6-44c1-a0a9-8a46aeada604.xml"
ms.topic: struct
req.header: mpiodisk.h
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
-	mpiodisk.h
api_name:
-	MPIO_GET_DESCRIPTOR
product:
- Windows
targetos: Windows
req.typenames: MPIO_GET_DESCRIPTOR, *PMPIO_GET_DESCRIPTOR
---

# _MPIO_GET_DESCRIPTOR structure


## -description


The MPIO_GET_DESCRIPTOR structure is used to query for LUN instances that correspond to various paths. This structure retrieves device-path pairing information about a multi-path disk. The target of the request must be a pseudo-LUN that is addressed by using its WMI instance name.


## -struct-fields




### -field NumberPdos

An unsigned 32-bitfield that returns the number of real instances of the pseudo-LUN through its various paths.


### -field DeviceName

A string field of maximum-length 63 characters that returns the device name that is created by MPIO for the LUN.


### -field PdoInformation

A field that returns an array of PDO_INFORMATION structures, where the number of elements is given by <i>NumberPdos</i>, and each element represents an instance of the LUN that is exposed through a particular path.

