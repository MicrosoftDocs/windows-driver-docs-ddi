---
UID: NS:ntddk._WHEA_MEMORY_ERROR_SECTION
title: _WHEA_MEMORY_ERROR_SECTION (ntddk.h)
description: The WHEA_MEMORY_ERROR_SECTION structure describes platform memory error data.
old-location: whea\whea_memory_error_section.htm
tech.root: whea
ms.assetid: eede44f8-0e14-4256-9893-cbdb5ef4ef9b
ms.date: 02/20/2018
keywords: ["_WHEA_MEMORY_ERROR_SECTION structure"]
ms.keywords: "*PWHEA_MEMORY_ERROR, *PWHEA_MEMORY_ERROR_SECTION, PWHEA_MEMORY_ERROR_SECTION, PWHEA_MEMORY_ERROR_SECTION structure pointer [WHEA Drivers and Applications], WHEA_MEMORY_ERROR, WHEA_MEMORY_ERROR_SECTION, WHEA_MEMORY_ERROR_SECTION structure [WHEA Drivers and Applications], _WHEA_MEMORY_ERROR_SECTION, ntddk/PWHEA_MEMORY_ERROR_SECTION, ntddk/WHEA_MEMORY_ERROR_SECTION, whea.whea_memory_error_section, whearef_63417420-4e27-4268-b50f-6d8dc2cdbd58.xml"
f1_keywords:
 - "ntddk/WHEA_MEMORY_ERROR_SECTION"
 - "WHEA_MEMORY_ERROR_SECTION"
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
- WHEA_MEMORY_ERROR_SECTION
product:
- Windows
targetos: Windows
req.typenames: WHEA_MEMORY_ERROR_SECTION, *PWHEA_MEMORY_ERROR_SECTION
---

# _WHEA_MEMORY_ERROR_SECTION structure


## -description


The WHEA_MEMORY_ERROR_SECTION structure describes platform memory error data.


## -struct-fields




### -field ValidBits

A <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddk/ns-ntddk-_whea_memory_error_section_validbits">WHEA_MEMORY_ERROR_SECTION_VALIDBITS</a> union that specifies which members of this structure contain valid data.


### -field ErrorStatus

A <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddk/ns-ntddk-_whea_error_status">WHEA_ERROR_STATUS</a> structure that contains memory error status data.

This member contains valid data only if the <b>Validbits.ErrorStatus</b> bit is set.


### -field PhysicalAddress

The physical address where the memory error occurred.

This member contains valid data only if the <b>Validbits.PhysicalAddress</b> bit is set.


### -field PhysicalAddressMask

A bit mask that specifies which of the bits in the <b>PhysicalAddress</b> member contain valid address data.

This member contains valid data only if the <b>Validbits.PhysicalAddressMask</b> bit is set.


### -field Node

The identifier of the node that contains the memory where the memory error occurred in a system with multiple nodes.

This member contains valid data only if the <b>Validbits.Node</b> bit is set.


### -field Card

The card number of the card that contains the memory where the memory error occurred.

This member contains valid data only if the <b>Validbits.Card</b> bit is set.


### -field Module

The module number of the module that contains the memory where the memory error occurred.

This member contains valid data only if the <b>Validbits.Module</b> bit is set.


### -field Bank

The bank number of the memory bank that contains the memory where the memory error occurred.

This member contains valid data only if the <b>Validbits.Bank</b> bit is set.


### -field Device

The device number of the memory device that contains the memory where the memory error occurred.

This member contains valid data only if the <b>Validbits.Device</b> bit is set.


### -field Row

The row number of the location where the memory error occurred.

This member contains valid data only if the <b>Validbits.Row</b> bit is set.


### -field Column

The column number of the location where the memory error occurred.

This member contains valid data only if the <b>Validbits.Column</b> bit is set.


### -field BitPosition

The bit position where the memory error occurred.

This member contains valid data only if the <b>Validbits.BitPosition</b> bit is set.


### -field RequesterId

An identifier that uniquely identifies the requester associated with the error.

This member contains valid data only if the <b>Validbits.RequesterId</b> bit is set.


### -field ResponderId

An identifier that uniquely identifies the responder associated with the error.

This member contains valid data only if the <b>Validbits.ResponderId</b> bit is set.


### -field TargetId

The hardware address of the intended target of the transaction.

This member contains valid data only if the <b>Validbits.TargetId</b> bit is set.


### -field ErrorType

The type of memory error that occurred. Possible values are:

| Possible Values                   | Description                                                                                                                                                                      |
| --------------------------------- | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| WHEA_MEMERRTYPE_UNKNOWN           | An unknown error.                                                                                                                                                                |
| WHEA_MEMERRTYPE_NOERROR           | No error occurred.                                                                                                                                                               |
| WHEA_MEMERRTYPE_SINGLEBITECC      | A single bit [ECC](https://docs.microsoft.com/windows-hardware/drivers/) error.                                                                            |
| WHEA_MEMERRTYPE_MULTIBITECC       | multibit ECC error.                                                                                                                                                              |
| WHEA_MEMERRTYPE_SINGLESYMCHIPKILL | A single symbol <a href="https://go.microsoft.com/fwlink/p/?linkid=81372">ChipKill</a> <a href="https://docs.microsoft.com/windows-hardware/drivers/">ECC</a> error.   |
| WHEA_MEMERRTYPE_MULTISYMCHIPKILL  | A multiple symbol <a href="https://go.microsoft.com/fwlink/p/?linkid=81372">ChipKill</a> <a href="https://docs.microsoft.com/windows-hardware/drivers/">ECC</a> error. |
| WHEA_MEMERRTYPE_MASTERABORT       | A master abort.                                                                                                                                                                  |
| WHEA_MEMERRTYPE_TARGETABORT       | A target abort.                                                                                                                                                                  |
| WHEA_MEMERRTYPE_PARITYERROR       | A parity error.                                                                                                                                                                  |
| WHEA_MEMERRTYPE_WATCHDOGTIMEOUT   | A watchdog timeout.                                                                                                                                                              |
| WHEA_MEMERRTYPE_INVALIDADDRESS    | An invalid memory address.                                                                                                                                                       |
| WHEA_MEMERRTYPE_MIRRORBROKEN      | A broken memory mirror.                                                                                                                                                          |
| WHEA_MEMERRTYPE_MEMORYSPARING     | A memory sparing error.                                                                                                                                                          | This member contains valid data only if the <b>Validbits.ErrorType</b> bit is set. |


### -field Extended

Contains valid data only if the **ValidBits.ExtendedRow** bits is set.

If **ValidBits.Row** is not set, the **Row** member contains row number bits (15:0) and Extended contains row number bits (17:16). Bit 0 is the 16th bit of the **Row**.  Bit 1 is the 17th bit of the **Row**.

If **ValidBits.ChipIdentification** is set, Bits 7:5 contain Chip Identification.

This value is available starting Windows 10, version 1803.

### -field RankNumber

The Rank number of the memory error location. This member contains valid data only if the **ValidBits.RankNumber** bit is set. This value is available starting Windows 10, version 1803.
 
### -field CardHandle
Contains the SMBIOS handle for the Memory Array Structure that represents the Memory Card.  This member contains valid data only if the **ValidBits.CardHandle** is set. This value is available starting Windows 10, version 1803.

 
### -field ModuleHandle
Contains the SMBIOS handle for the Memory Device Structure that represents the Memory Module.  This member contains valid data only if the **ValidBits.ModuleHandle** is set. This value is available starting Windows 10, version 1803.

## -remarks



The WHEA_MEMORY_ERROR_SECTION structure describes the error data that is contained in a platform memory error section of an <a href="https://docs.microsoft.com/windows-hardware/drivers/whea/error-records">error record</a>. An error record contains a platform memory error section only if the <b>SectionType </b>member of one of the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddk/ns-ntddk-_whea_error_record_section_descriptor">WHEA_ERROR_RECORD_SECTION_DESCRIPTOR</a> structures that describe the error record sections for that error record contains MEMORY_ERROR_SECTION_GUID.




## -see-also




<a href="https://docs.microsoft.com/previous-versions/windows/hardware/drivers/ff560465(v=vs.85)">WHEA_ERROR_PACKET</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddk/ns-ntddk-_whea_error_record_section_descriptor">WHEA_ERROR_RECORD_SECTION_DESCRIPTOR</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddk/ns-ntddk-_whea_error_status">WHEA_ERROR_STATUS</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddk/ns-ntddk-_whea_memory_error_section_validbits">WHEA_MEMORY_ERROR_SECTION_VALIDBITS</a>
 

 

