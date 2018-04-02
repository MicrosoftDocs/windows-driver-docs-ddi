---
UID: NS:ntddk._WHEA_MEMORY_ERROR_SECTION
title: "_WHEA_MEMORY_ERROR_SECTION"
author: windows-driver-content
description: The WHEA_MEMORY_ERROR_SECTION structure describes platform memory error data.
old-location: whea\whea_memory_error_section.htm
old-project: whea
ms.assetid: eede44f8-0e14-4256-9893-cbdb5ef4ef9b
ms.author: windowsdriverdev
ms.date: 2/20/2018
ms.keywords: "*PWHEA_MEMORY_ERROR, *PWHEA_MEMORY_ERROR_SECTION, PWHEA_MEMORY_ERROR_SECTION, PWHEA_MEMORY_ERROR_SECTION structure pointer [WHEA Drivers and Applications], WHEA_MEMORY_ERROR, WHEA_MEMORY_ERROR_SECTION, WHEA_MEMORY_ERROR_SECTION structure [WHEA Drivers and Applications], _WHEA_MEMORY_ERROR_SECTION, ntddk/PWHEA_MEMORY_ERROR_SECTION, ntddk/WHEA_MEMORY_ERROR_SECTION, whea.whea_memory_error_section, whearef_63417420-4e27-4268-b50f-6d8dc2cdbd58.xml"
ms.prod: windows-hardware
ms.technology: windows-devices
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
req.irql: PASSIVE_LEVEL
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	ntddk.h
api_name:
-	WHEA_MEMORY_ERROR_SECTION
product: Windows
targetos: Windows
req.typenames: WHEA_MEMORY_ERROR_SECTION, *PWHEA_MEMORY_ERROR_SECTION
---

# _WHEA_MEMORY_ERROR_SECTION structure


## -description


The WHEA_MEMORY_ERROR_SECTION structure describes platform memory error data.


## -struct-fields




### -field ValidBits

A <a href="https://msdn.microsoft.com/library/windows/hardware/ff560568">WHEA_MEMORY_ERROR_SECTION_VALIDBITS</a> union that specifies which members of this structure contain valid data.


### -field ErrorStatus

A <a href="https://msdn.microsoft.com/library/windows/hardware/ff560514">WHEA_ERROR_STATUS</a> structure that contains memory error status data.

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





#### WHEA_MEMERRTYPE_UNKNOWN

An unknown error.



#### WHEA_MEMERRTYPE_NOERROR

No error occurred.



#### WHEA_MEMERRTYPE_SINGLEBITECC

A single bit <a href="https://msdn.microsoft.com/0dd010e7-3e10-422a-adcb-8fe7df9e29ab">ECC</a> error.



#### WHEA_MEMERRTYPE_MULTIBITECC

A multibit ECC error.



#### WHEA_MEMERRTYPE_SINGLESYMCHIPKILL

A single symbol <a href="http://go.microsoft.com/fwlink/p/?linkid=81372">ChipKill</a> <a href="https://msdn.microsoft.com/0dd010e7-3e10-422a-adcb-8fe7df9e29ab">ECC</a> error.



#### WHEA_MEMERRTYPE_MULTISYMCHIPKILL

A multiple symbol <a href="http://go.microsoft.com/fwlink/p/?linkid=81372">ChipKill</a> <a href="https://msdn.microsoft.com/0dd010e7-3e10-422a-adcb-8fe7df9e29ab">ECC</a> error.



#### WHEA_MEMERRTYPE_MASTERABORT

A master abort.



#### WHEA_MEMERRTYPE_TARGETABORT

A target abort.



#### WHEA_MEMERRTYPE_PARITYERROR

A parity error.



#### WHEA_MEMERRTYPE_WATCHDOGTIMEOUT

A watchdog timeout.



#### WHEA_MEMERRTYPE_INVALIDADDRESS

An invalid memory address.



#### WHEA_MEMERRTYPE_MIRRORBROKEN

A broken memory mirror.



#### WHEA_MEMERRTYPE_MEMORYSPARING

A memory sparing error.

This member contains valid data only if the <b>Validbits.ErrorType</b> bit is set.


## -remarks



The WHEA_MEMORY_ERROR_SECTION structure describes the error data that is contained in a platform memory error section of an <a href="https://msdn.microsoft.com/080da29a-b5cb-45a5-848d-048d9612ee2a">error record</a>. An error record contains a platform memory error section only if the <b>SectionType </b>member of one of the <a href="https://msdn.microsoft.com/library/windows/hardware/ff560496">WHEA_ERROR_RECORD_SECTION_DESCRIPTOR</a> structures that describe the error record sections for that error record contains MEMORY_ERROR_SECTION_GUID.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff560465">WHEA_ERROR_PACKET</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff560496">WHEA_ERROR_RECORD_SECTION_DESCRIPTOR</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff560514">WHEA_ERROR_STATUS</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff560568">WHEA_MEMORY_ERROR_SECTION_VALIDBITS</a>
 

 

