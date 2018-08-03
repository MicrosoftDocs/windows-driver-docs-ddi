---
UID: NS:mpiowmi._MPIOMoveDevice_IN
title: "_MPIOMoveDevice_IN"
author: windows-driver-content
description: The MPIOMoveDevice_IN structure is used to set the active path on the device.
old-location: storage\mpiomovedevice_in.htm
tech.root: storage
ms.assetid: 2652874f-70d0-4eff-a46d-778a68d55cab
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: "*PMPIOMoveDevice_IN, MPIOMoveDevice_IN, MPIOMoveDevice_IN structure [Storage Devices], PMPIOMoveDevice_IN, PMPIOMoveDevice_IN structure pointer [Storage Devices], _MPIOMoveDevice_IN, mpiowmi/MPIOMoveDevice_IN, mpiowmi/PMPIOMoveDevice_IN, storage.mpiomovedevice_in, structs-scsibus_d1c11b7d-5c45-441b-8362-642db610e19e.xml"
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
-	MPIOMoveDevice_IN
product:
- Windows
targetos: Windows
req.typenames: MPIOMoveDevice_IN, *PMPIOMoveDevice_IN
---

# _MPIOMoveDevice_IN structure


## -description


The MPIOMoveDevice_IN structure is used to set the active path on the device.


## -struct-fields




### -field DiskOrdinal

A 32-bitfield that specifies the MPIO disk ordinal value.


### -field Flags

A 32-bitfield that specifies the flags that are associated with the device move operation.


### -field PathID

A 64-bitfield that specifies the path that is associated with the device.

