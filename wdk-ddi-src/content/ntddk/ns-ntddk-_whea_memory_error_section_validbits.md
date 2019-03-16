---
UID: NS:ntddk._WHEA_MEMORY_ERROR_SECTION_VALIDBITS
title: _WHEA_MEMORY_ERROR_SECTION_VALIDBITS (ntddk.h)
description: The WHEA_MEMORY_ERROR_SECTION_VALIDBITS union describes which members of a WHEA_MEMORY_ERROR_SECTION structure contain valid data.
old-location: whea\whea_memory_error_section_validbits.htm
tech.root: whea
ms.assetid: 53ac65ff-56fe-411d-b0d1-174fc875a786
ms.date: 02/20/2018
ms.keywords: "*PWHEA_MEMORY_ERROR_SECTION_VALIDBITS, *PWHEA_MEMORY_ERROR_VALIDBITS, PWHEA_MEMORY_ERROR_SECTION_VALIDBITS, PWHEA_MEMORY_ERROR_SECTION_VALIDBITS union pointer [WHEA Drivers and Applications], WHEA_MEMORY_ERROR_SECTION_VALIDBITS, WHEA_MEMORY_ERROR_SECTION_VALIDBITS union [WHEA Drivers and Applications], WHEA_MEMORY_ERROR_VALIDBITS, _WHEA_MEMORY_ERROR_SECTION_VALIDBITS, ntddk/PWHEA_MEMORY_ERROR_SECTION_VALIDBITS, ntddk/WHEA_MEMORY_ERROR_SECTION_VALIDBITS, whea.whea_memory_error_section_validbits, whearef_49eab340-c05f-4201-a45d-8602ec121ef3.xml"
ms.topic: struct
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
- WHEA_MEMORY_ERROR_SECTION_VALIDBITS
product:
- Windows
targetos: Windows
req.typenames: WHEA_MEMORY_ERROR_SECTION_VALIDBITS, *PWHEA_MEMORY_ERROR_SECTION_VALIDBITS
---

# _WHEA_MEMORY_ERROR_SECTION_VALIDBITS structure


## -description


The WHEA_MEMORY_ERROR_SECTION_VALIDBITS union describes which members of a <a href="https://msdn.microsoft.com/library/windows/hardware/ff560565">WHEA_MEMORY_ERROR_SECTION</a> structure contain valid data.


## -struct-fields




### -field DUMMYSTRUCTNAME

 


### -field DUMMYSTRUCTNAME.ErrorStatus

A single bit that indicates that the <b>ErrorStatus</b> member of the WHEA_MEMORY_ERROR_SECTION structure contains valid data.


### -field DUMMYSTRUCTNAME.Bank

A single bit that indicates that the <b>PhysicalAddress</b> member of the WHEA_MEMORY_ERROR_SECTION structure contains valid data.


### -field DUMMYSTRUCTNAME.BitPosition

A single bit that indicates that the <b>PhysicalAddressMask</b> member of the WHEA_MEMORY_ERROR_SECTION structure contains valid data.


### -field DUMMYSTRUCTNAME.Card

A single bit that indicates that the <b>Node</b> member of the WHEA_MEMORY_ERROR_SECTION structure contains valid data.


### -field DUMMYSTRUCTNAME.Column

A single bit that indicates that the <b>Card</b> member of the WHEA_MEMORY_ERROR_SECTION structure contains valid data.


### -field DUMMYSTRUCTNAME.Device

A single bit that indicates that the <b>Module</b> member of the WHEA_MEMORY_ERROR_SECTION structure contains valid data.


### -field DUMMYSTRUCTNAME.ErrorStatus

A single bit that indicates that the <b>Bank</b> member of the WHEA_MEMORY_ERROR_SECTION structure contains valid data.


### -field DUMMYSTRUCTNAME.ErrorType

A single bit that indicates that the <b>Device</b> member of the WHEA_MEMORY_ERROR_SECTION structure contains valid data.


### -field DUMMYSTRUCTNAME.Module

A single bit that indicates that the <b>Row</b> member of the WHEA_MEMORY_ERROR_SECTION structure contains valid data.


### -field DUMMYSTRUCTNAME.Node

A single bit that indicates that the <b>Column</b> member of the WHEA_MEMORY_ERROR_SECTION structure contains valid data.


### -field DUMMYSTRUCTNAME.PhysicalAddress

A single bit that indicates that the <b>BitPosition</b> member of the WHEA_MEMORY_ERROR_SECTION structure contains valid data.


### -field DUMMYSTRUCTNAME.PhysicalAddressMask

A single bit that indicates that the <b>RequesterId</b> member of the WHEA_MEMORY_ERROR_SECTION structure contains valid data.


### -field DUMMYSTRUCTNAME.RequesterId

A single bit that indicates that the <b>ResponderId</b> member of the WHEA_MEMORY_ERROR_SECTION structure contains valid data.


### -field DUMMYSTRUCTNAME.Reserved

A single bit that indicates that the <b>TargetId</b> member of the WHEA_MEMORY_ERROR_SECTION structure contains valid data.


### -field DUMMYSTRUCTNAME.ResponderId

A single bit that indicates that the <b>ErrorType</b> member of the WHEA_MEMORY_ERROR_SECTION structure contains valid data.


### -field DUMMYSTRUCTNAME.Row

Reserved for system use.


### -field DUMMYSTRUCTNAME.TargetId

A ULONGLONG representation of the contents of the WHEA_MEMORY_ERROR_SECTION_VALIDBITS union.

### -field DUMMYSTRUCTNAME.ErrorType
The type of memory error that occurred. Possible values are:

| Possible Values                   | Description                                                                                                                                                                      |
| --------------------------------- | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| WHEA_MEMERRTYPE_UNKNOWN           | An unknown error.                                                                                                                                                                |
| WHEA_MEMERRTYPE_NOERROR           | No error occurred.                                                                                                                                                               |
| WHEA_MEMERRTYPE_SINGLEBITECC      | A single bit [ECC](https://msdn.microsoft.com/0dd010e7-3e10-422a-adcb-8fe7df9e29ab) error.                                                                            |
| WHEA_MEMERRTYPE_MULTIBITECC       | multibit ECC error.                                                                                                                                                              |
| WHEA_MEMERRTYPE_SINGLESYMCHIPKILL | A single symbol <a href="https://go.microsoft.com/fwlink/p/?linkid=81372">ChipKill</a> <a href="https://msdn.microsoft.com/0dd010e7-3e10-422a-adcb-8fe7df9e29ab">ECC</a> error.   |
| WHEA_MEMERRTYPE_MULTISYMCHIPKILL  | A multiple symbol <a href="https://go.microsoft.com/fwlink/p/?linkid=81372">ChipKill</a> <a href="https://msdn.microsoft.com/0dd010e7-3e10-422a-adcb-8fe7df9e29ab">ECC</a> error. |
| WHEA_MEMERRTYPE_MASTERABORT       | A master abort.                                                                                                                                                                  |
| WHEA_MEMERRTYPE_TARGETABORT       | A target abort.                                                                                                                                                                  |
| WHEA_MEMERRTYPE_PARITYERROR       | A parity error.                                                                                                                                                                  |
| WHEA_MEMERRTYPE_WATCHDOGTIMEOUT   | A watchdog timeout.                                                                                                                                                              |
| WHEA_MEMERRTYPE_INVALIDADDRESS    | An invalid memory address.                                                                                                                                                       |
| WHEA_MEMERRTYPE_MIRRORBROKEN      | A broken memory mirror.                                                                                                                                                          |
| WHEA_MEMERRTYPE_MEMORYSPARING     | A memory sparing error.                                                                                                                                                          | This member contains valid data only if the <b>Validbits.ErrorType</b> bit is set. |
 
### -field DUMMYSTRUCTNAME.RankNumber
The Rank number of the memory error location. This member contains valid data only if the **ValidBits.RankNumber** bit is set. This value is available starting Windows 10, version 1803.
 
### -field DUMMYSTRUCTNAME.CardHandle
Contains the SMBIOS handle for the Memory Array Structure that represents the Memory Card.  This member contains valid data only if the **ValidBits.CardHandle** is set. This value is available starting Windows 10, version 1803.
 
### -field DUMMYSTRUCTNAME.ModuleHandle
Contains the SMBIOS handle for the Memory Device Structure that represents the Memory Module.  This member contains valid data only if the **ValidBits.ModuleHandle** is set. This value is available starting Windows 10, version 1803.
 
### -field DUMMYSTRUCTNAME.ExtendedRow
Contains valid data only if the **ValidBits.ExtendedRow** bits is set.

### -field DUMMYSTRUCTNAME.BankGroup
The bank number of the memory bank that contains the memory where the memory error occurred. If **Validbits.Bank** is set.

If **ValidBits.BankGroup** is set, the **Bank** member Bit (15:8) is Bank Group.
 
### -field DUMMYSTRUCTNAME.BankAddress
The bank number of the memory bank that contains the memory where the memory error occurred.  If **Validbits.Bank** is set.

If **ValidBits.BankAddress** is set, the **Bank** member Bit (7:0) Bank Address.

### -field DUMMYSTRUCTNAME.ChipIdentification
If **ValidBits.ChipIdentification** is set, Bits 7:5 contain Chip Identification.

This value is available starting Windows 10, version 1803.
 
### -field DUMMYSTRUCTNAME.Reserved

Reserved.


## -remarks



A WHEA_MEMORY_ERROR_SECTION_VALIDBITS union is contained within the <a href="https://msdn.microsoft.com/library/windows/hardware/ff560565">WHEA_MEMORY_ERROR_SECTION</a> structure.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff560565">WHEA_MEMORY_ERROR_SECTION</a>
 

 

