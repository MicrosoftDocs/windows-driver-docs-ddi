---
UID: NS:ntddk._WHEA_ERROR_RECORD_HEADER_VALIDBITS
title: _WHEA_ERROR_RECORD_HEADER_VALIDBITS (ntddk.h)
description: The WHEA_ERROR_RECORD_HEADER_VALIDBITS union describes which members of a WHEA_ERROR_RECORD_HEADER structure contain valid data.
old-location: whea\whea_error_record_header_validbits.htm
tech.root: whea
ms.assetid: b16dd19f-1a67-4066-9dae-b36ff6f44d43
ms.date: 02/20/2018
keywords: ["_WHEA_ERROR_RECORD_HEADER_VALIDBITS structure"]
ms.keywords: "*PWHEA_ERROR_RECORD_HEADER_VALIDBITS, PWHEA_ERROR_RECORD_HEADER_VALIDBITS, PWHEA_ERROR_RECORD_HEADER_VALIDBITS union pointer [WHEA Drivers and Applications], WHEA_ERROR_RECORD_HEADER_VALIDBITS, WHEA_ERROR_RECORD_HEADER_VALIDBITS union [WHEA Drivers and Applications], _WHEA_ERROR_RECORD_HEADER_VALIDBITS, ntddk/PWHEA_ERROR_RECORD_HEADER_VALIDBITS, ntddk/WHEA_ERROR_RECORD_HEADER_VALIDBITS, whea.whea_error_record_header_validbits, whearef_66b0c2f7-6fad-4cdb-ac15-f4d942d208e1.xml"
f1_keywords:
 - "ntddk/WHEA_ERROR_RECORD_HEADER_VALIDBITS"
 - "WHEA_ERROR_RECORD_HEADER_VALIDBITS"
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
topic_type:
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- ntddk.h
api_name:
- WHEA_ERROR_RECORD_HEADER_VALIDBITS
product:
- Windows
targetos: Windows
req.typenames: WHEA_ERROR_RECORD_HEADER_VALIDBITS, *PWHEA_ERROR_RECORD_HEADER_VALIDBITS
---

# _WHEA_ERROR_RECORD_HEADER_VALIDBITS structure


## -description


The WHEA_ERROR_RECORD_HEADER_VALIDBITS union describes which members of a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddk/ns-ntddk-_whea_error_record_header">WHEA_ERROR_RECORD_HEADER</a> structure contain valid data.


## -struct-fields




### -field DUMMYSTRUCTNAME

 


### -field DUMMYSTRUCTNAME.PlatformId

A single bit that indicates that the <b>PlatformId</b> member of the WHEA_ERROR_RECORD_HEADER structure contains valid data.


### -field DUMMYSTRUCTNAME.Timestamp

A single bit that indicates that the <b>Timestamp</b> member of the WHEA_ERROR_RECORD_HEADER structure contains valid data.


### -field DUMMYSTRUCTNAME.PartitionId

A single bit that indicates that the <b>PartitionId</b> member of the WHEA_ERROR_RECORD_HEADER structure contains valid data.


### -field DUMMYSTRUCTNAME.Reserved

Reserved for system use.


### -field AsULONG

A ULONG representation of the contents of the WHEA_ERROR_RECORD_HEADER_VALIDBITS union.


## -remarks



A WHEA_ERROR_RECORD_HEADER_VALIDBITS union is contained within the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddk/ns-ntddk-_whea_error_record_header">WHEA_ERROR_RECORD_HEADER</a> structure.

<div class="alert"><b>Important</b>  After the release of Windows Server 2008, it was discovered that the <b>Timestamp</b> and <b>PlatformId</b> members of the WHEA_ERROR_RECORD_HEADER_VALIDBITS union are defined in the incorrect order. This topic now defines the correct order for these members.<p class="note">If you build your <a href="https://docs.microsoft.com/windows-hardware/drivers/whea/windows-hardware-error-architecture-aware-user-mode-applications">Windows hardware error architecture (WHEA) user-mode application</a> or <a href="https://docs.microsoft.com/windows-hardware/drivers/whea/platform-specific-hardware-error-driver-plug-ins2">platform-specific hardware error driver (PSHED) plug-in</a> with the header files from the Windows Server 2008 version of the WDK or Windows SDK, you will have trouble only if your application or PSHED plug-in accesses the <b>Timestamp</b> and <b>PlatformId</b> members directly when it processes the contents of a WHEA_ERROR_RECORD_HEADER structure. When you test these bits in the <b>AsULONG </b>member through the bitfield constants that are described in the following list, you will always produce the correct results.

<p class="note">This problem has been fixed in the Windows 7 version of the WDK and SDK.

</div>
<div> </div>
The following bitfield constants can be used to test the bits in the <b>AsULONG </b>member:






## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddk/ns-ntddk-_whea_error_record_header">WHEA_ERROR_RECORD_HEADER</a>
 

 

