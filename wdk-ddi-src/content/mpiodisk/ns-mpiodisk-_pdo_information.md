---
UID: NS:mpiodisk._PDO_INFORMATION
title: _PDO_INFORMATION
author: windows-driver-content
description: The PDO_INFORMATION structure represents a device-path pairing, which is an instance of a LUN through a particular path.
old-location: storage\pdo_information.htm
old-project: storage
ms.assetid: 26ce460f-b12d-4e5e-994a-047a1853325d
ms.author: windowsdriverdev
ms.date: 1/10/2018
ms.keywords: _PDO_INFORMATION, *PPDO_INFORMATION, PDO_INFORMATION
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: mpiodisk.h
req.include-header: Mpiowmi.h
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: PDO_INFORMATION
req.alt-loc: mpiodisk.h
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
req.typenames: *PPDO_INFORMATION, PDO_INFORMATION
---

# _PDO_INFORMATION structure



## -description
The PDO_INFORMATION structure represents a device-path pairing, which is an instance of a LUN through a particular path.



## -syntax

````
typedef struct _PDO_INFORMATION {
  PDOSCSI_ADDR ScsiAddress;
  ULONG        DeviceState;
  ULONGLONG    PathIdentifier;
  ULONG        IdentifierType;
  ULONG        IdentifierLength;
  UCHAR        Identifier[32];
  UCHAR        Pad[4];
} PDO_INFORMATION, *PPDO_INFORMATION;
````


## -struct-fields

### -field ScsiAddress

A PDOSCSI_ADDR structure that represents the SCSI address of the LUN's instance that corresponds to a particular path.


### -field DeviceState

An unsigned 32-bitfield that represents whether the path, through which this instance of the LUN was exposed, is usable.


### -field PathIdentifier

An unsigned 64-bitfield that represents the identifier that is associated with the path through which this instance of the LUN is exposed.


### -field IdentifierType

An unsigned 32-bitfield that represents the identifier type of the LUN's controller.


### -field IdentifierLength

An unsigned 32-bitfield that represents the length of the identifier of the LUN's controller.


### -field Identifier

An unsigned 64-bitfield that represents the identifier that is associated with the path through which this instance of the LUN is exposed.


### -field Pad

Should be zero.


## -remarks
