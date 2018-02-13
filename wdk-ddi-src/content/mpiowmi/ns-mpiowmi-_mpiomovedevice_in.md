---
UID: NS:mpiowmi._MPIOMoveDevice_IN
title: "_MPIOMoveDevice_IN"
author: windows-driver-content
description: The MPIOMoveDevice_IN structure is used to set the active path on the device.
old-location: storage\mpiomovedevice_in.htm
old-project: storage
ms.assetid: 2652874f-70d0-4eff-a46d-778a68d55cab
ms.author: windowsdriverdev
ms.date: 1/10/2018
ms.keywords: MPIOMoveDevice_IN structure [Storage Devices], *PMPIOMoveDevice_IN, PMPIOMoveDevice_IN, PMPIOMoveDevice_IN structure pointer [Storage Devices], _MPIOMoveDevice_IN, mpiowmi/MPIOMoveDevice_IN, MPIOMoveDevice_IN, mpiowmi/PMPIOMoveDevice_IN, structs-scsibus_d1c11b7d-5c45-441b-8362-642db610e19e.xml, storage.mpiomovedevice_in
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	mpiowmi.h
apiname:
-	MPIOMoveDevice_IN
product: Windows
targetos: Windows
req.typenames: "*PMPIOMoveDevice_IN, MPIOMoveDevice_IN"
---

# _MPIOMoveDevice_IN structure


## -description


The MPIOMoveDevice_IN structure is used to set the active path on the device.


## -syntax


````
typedef struct _MPIOMoveDevice_IN {
  ULONG     DiskOrdinal;
  ULONG     Flags;
  ULONGLONG PathID;
} MPIOMoveDevice_IN, *PMPIOMoveDevice_IN;
````


## -struct-fields




### -field DiskOrdinal

A 32-bitfield that specifies the MPIO disk ordinal value.


### -field Flags

A 32-bitfield that specifies the flags that are associated with the device move operation.


### -field PathID

A 64-bitfield that specifies the path that is associated with the device.

