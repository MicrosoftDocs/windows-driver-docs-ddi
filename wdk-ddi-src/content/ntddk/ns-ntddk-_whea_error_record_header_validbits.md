---
UID: NS:ntddk._WHEA_ERROR_RECORD_HEADER_VALIDBITS
title: _WHEA_ERROR_RECORD_HEADER_VALIDBITS (ntddk.h)
description: The WHEA_ERROR_RECORD_HEADER_VALIDBITS union describes which members of a WHEA_ERROR_RECORD_HEADER structure contain valid data.
tech.root: whea
ms.date: 12/09/2022
keywords: ["WHEA_ERROR_RECORD_HEADER_VALIDBITS structure"]
ms.keywords: "*PWHEA_ERROR_RECORD_HEADER_VALIDBITS, PWHEA_ERROR_RECORD_HEADER_VALIDBITS, PWHEA_ERROR_RECORD_HEADER_VALIDBITS union pointer [WHEA Drivers and Applications], WHEA_ERROR_RECORD_HEADER_VALIDBITS, WHEA_ERROR_RECORD_HEADER_VALIDBITS union [WHEA Drivers and Applications], _WHEA_ERROR_RECORD_HEADER_VALIDBITS, ntddk/PWHEA_ERROR_RECORD_HEADER_VALIDBITS, ntddk/WHEA_ERROR_RECORD_HEADER_VALIDBITS, whea.whea_error_record_header_validbits, whearef_66b0c2f7-6fad-4cdb-ac15-f4d942d208e1.xml"
req.header: ntddk.h
req.include-header: Ntddk.h
req.target-type: Windows
req.target-min-winverclnt: Supported in Windows Server 2008, Windows Vista SP1, and later versions of Windows.
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
targetos: Windows
req.typenames: WHEA_ERROR_RECORD_HEADER_VALIDBITS, *PWHEA_ERROR_RECORD_HEADER_VALIDBITS
f1_keywords:
 - _WHEA_ERROR_RECORD_HEADER_VALIDBITS
 - ntddk/_WHEA_ERROR_RECORD_HEADER_VALIDBITS
 - PWHEA_ERROR_RECORD_HEADER_VALIDBITS
 - ntddk/PWHEA_ERROR_RECORD_HEADER_VALIDBITS
 - WHEA_ERROR_RECORD_HEADER_VALIDBITS
 - ntddk/WHEA_ERROR_RECORD_HEADER_VALIDBITS
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - ntddk.h
api_name:
 - _WHEA_ERROR_RECORD_HEADER_VALIDBITS
 - PWHEA_ERROR_RECORD_HEADER_VALIDBITS
 - WHEA_ERROR_RECORD_HEADER_VALIDBITS
---

## -description

The **WHEA_ERROR_RECORD_HEADER_VALIDBITS** union describes which members of a [**WHEA_ERROR_RECORD_HEADER**](/windows-hardware/drivers/ddi/ntddk/ns-ntddk-_whea_error_record_header) structure contain valid data.

## -struct-fields

### -field DUMMYSTRUCTNAME

### -field DUMMYSTRUCTNAME.PlatformId

A single bit that indicates that the **PlatformId** member of the **WHEA_ERROR_RECORD_HEADER** structure contains valid data.

### -field DUMMYSTRUCTNAME.Timestamp

A single bit that indicates that the **Timestamp** member of the **WHEA_ERROR_RECORD_HEADER** structure contains valid data.

### -field DUMMYSTRUCTNAME.PartitionId

A single bit that indicates that the **PartitionId** member of the **WHEA_ERROR_RECORD_HEADER** structure contains valid data.

### -field DUMMYSTRUCTNAME.Reserved

Reserved for system use.

### -field AsULONG

A ULONG representation of the contents of the **WHEA_ERROR_RECORD_HEADER_VALIDBITS** union.

## -remarks

A **WHEA_ERROR_RECORD_HEADER_VALIDBITS** union is contained within the [**WHEA_ERROR_RECORD_HEADER**](/windows-hardware/drivers/ddi/ntddk/ns-ntddk-_whea_error_record_header) structure.

After the release of Windows Server 2008, it was discovered that the **Timestamp** and **PlatformId** members of the **WHEA_ERROR_RECORD_HEADER_VALIDBITS** union are defined in the incorrect order. This topic now defines the correct order for these members.

If you build your [Windows hardware error architecture (WHEA) user-mode application](/windows-hardware/drivers/whea/windows-hardware-error-architecture-aware-user-mode-applications) or [platform-specific hardware error driver (PSHED) plug-in](/windows-hardware/drivers/whea/platform-specific-hardware-error-driver-plug-ins2) with the header files from the Windows Server 2008 version of the WDK or Windows SDK, you will have trouble only if your application or PSHED plug-in accesses the **Timestamp** and **PlatformId** members directly when it processes the contents of a **WHEA_ERROR_RECORD_HEADER** structure. When you test these bits in the **AsULONG** member through the bitfield constants that are described in the following list, you will always produce the correct results.

This problem has been fixed in the Windows 7 version of the WDK and SDK.

## -see-also

[**WHEA_ERROR_RECORD_HEADER**](/windows-hardware/drivers/ddi/ntddk/ns-ntddk-_whea_error_record_header)
