---
UID: NS:ntddstor._STORAGE_MINIPORT_DESCRIPTOR
title: STORAGE_MINIPORT_DESCRIPTOR (ntddstor.h)
description: "Microsoft reserves the STORAGE_MINIPORT_DESCRIPTOR structure for internal use only. Don't use this structure in your code."
old-location: storage\storage_miniport_descriptor.htm
tech.root: storage
ms.date: 08/18/2022
keywords: ["STORAGE_MINIPORT_DESCRIPTOR structure"]
ms.keywords: "*PSTORAGE_MINIPORT_DESCRIPTOR, PSTORAGE_MINIPORT_DESCRIPTOR, PSTORAGE_MINIPORT_DESCRIPTOR structure pointer [Storage Devices], STORAGE_MINIPORT_DESCRIPTOR, STORAGE_MINIPORT_DESCRIPTOR structure [Storage Devices], _STORAGE_MINIPORT_DESCRIPTOR, ntddstor/PSTORAGE_MINIPORT_DESCRIPTOR, ntddstor/STORAGE_MINIPORT_DESCRIPTOR, storage.storage_miniport_descriptor"
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
targetos: Windows
req.typenames: STORAGE_MINIPORT_DESCRIPTOR, *PSTORAGE_MINIPORT_DESCRIPTOR
f1_keywords:
 - _STORAGE_MINIPORT_DESCRIPTOR
 - ntddstor/_STORAGE_MINIPORT_DESCRIPTOR
 - PSTORAGE_MINIPORT_DESCRIPTOR
 - ntddstor/PSTORAGE_MINIPORT_DESCRIPTOR
 - STORAGE_MINIPORT_DESCRIPTOR
 - ntddstor/STORAGE_MINIPORT_DESCRIPTOR
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - ntddstor.h
api_name:
 - _STORAGE_MINIPORT_DESCRIPTOR
 - PSTORAGE_MINIPORT_DESCRIPTOR
 - STORAGE_MINIPORT_DESCRIPTOR
---

# STORAGE_MINIPORT_DESCRIPTOR structure

## -description

Reserved for system use.

## -struct-fields

### -field Version

Contains the size of this structure, in bytes. The value of this member will change as members are added to the structure.

### -field Size

Specifies the total size of the data returned, in bytes. This may include data that follows this structure.

### -field Portdriver

Type of port driver as enumerated by the [**STORAGE_PORT_CODE_SET**](/previous-versions/windows/hardware/drivers/mt668773(v=vs.85)) enumeration.

### -field LUNResetSupported

Indicates whether a LUN reset is supported.

### -field TargetResetSupported

Indicates whether a target reset is supported.

### -field IoTimeoutValue

The timeout value for the device, in milliseconds (ms). Introduced in Windows 8.

### -field ExtraIoInfoSupported

Indicates whether extra I/O info is supported. Introduced in Windows 8.1

### -field Flags

### -field Flags.DUMMYSTRUCTNAME

### -field Flags.DUMMYSTRUCTNAME.LogicalPoFxForDisk

### -field Flags.DUMMYSTRUCTNAME.Reserved

### -field Flags.AsUCHAR

### -field Reserved0[2]

Reserved for future use.

### -field Reserved0[3]

Reserved for future use.

### -field Reserved1

Reserved for future use.
