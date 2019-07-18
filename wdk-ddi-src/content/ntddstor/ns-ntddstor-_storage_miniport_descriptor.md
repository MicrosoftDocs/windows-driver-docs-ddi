---
UID: NS:ntddstor._STORAGE_MINIPORT_DESCRIPTOR
title: _STORAGE_MINIPORT_DESCRIPTOR (ntddstor.h)
description: Reserved for system use.
old-location: storage\storage_miniport_descriptor.htm
tech.root: storage
ms.assetid: 30497CA8-70B6-48F9-B5D5-45E606A3226E
ms.date: 03/29/2018
ms.keywords: "*PSTORAGE_MINIPORT_DESCRIPTOR, PSTORAGE_MINIPORT_DESCRIPTOR, PSTORAGE_MINIPORT_DESCRIPTOR structure pointer [Storage Devices], STORAGE_MINIPORT_DESCRIPTOR, STORAGE_MINIPORT_DESCRIPTOR structure [Storage Devices], _STORAGE_MINIPORT_DESCRIPTOR, ntddstor/PSTORAGE_MINIPORT_DESCRIPTOR, ntddstor/STORAGE_MINIPORT_DESCRIPTOR, storage.storage_miniport_descriptor"
ms.topic: struct
f1_keywords:
 - "ntddstor/STORAGE_MINIPORT_DESCRIPTOR"
req.header: ntddstor.h
req.include-header: Ntddstor.h
req.target-type: Windows
req.target-min-winverclnt: Windows Vista
req.target-min-winversvr: Windows Server 2008
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
- ntddstor.h
api_name:
- STORAGE_MINIPORT_DESCRIPTOR
product:
- Windows
targetos: Windows
req.typenames: STORAGE_MINIPORT_DESCRIPTOR, *PSTORAGE_MINIPORT_DESCRIPTOR
---

# _STORAGE_MINIPORT_DESCRIPTOR structure


## -description


Reserved for system use.


## -struct-fields




### -field Version

Contains the size of this structure, in bytes. The value of this member will change as members are added to 
      the structure.


### -field Size

Specifies the total size of the data returned, in bytes. This may include data that follows this 
      structure.


### -field Portdriver

Type of port driver as enumerated by the 
     <a href="https://docs.microsoft.com/previous-versions/windows/hardware/drivers/mt668773(v=vs.85)">STORAGE_PORT_CODE_SET</a> enumeration.


### -field LUNResetSupported

Indicates whether a LUN reset is supported.


### -field TargetResetSupported

Indicates whether a target reset is supported.


### -field IoTimeoutValue

<b>Introduced in Windows 8:  </b>Indicates the timeout value for the device, in milliseconds (ms).


### -field ExtraIoInfoSupported

<b>Introduced in Windows 8.1:  </b>Indicates if extra I/O info is supported.


### -field Reserved0

<b>Introduced in Windows 8.1:  </b>Reserved for future use.


### -field Reserved1

<b>Introduced in Windows 8.1:  </b>Reserved for future use.

