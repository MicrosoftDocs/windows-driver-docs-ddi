---
UID: NS:ntddk._WHEA_MEMORY_ERROR_SECTION_VALIDBITS
title: "_WHEA_MEMORY_ERROR_SECTION_VALIDBITS"
author: windows-driver-content
description: The WHEA_MEMORY_ERROR_SECTION_VALIDBITS union describes which members of a WHEA_MEMORY_ERROR_SECTION structure contain valid data.
old-location: whea\whea_memory_error_section_validbits.htm
old-project: whea
ms.assetid: 53ac65ff-56fe-411d-b0d1-174fc875a786
ms.author: windowsdriverdev
ms.date: 2/20/2018
ms.keywords: "*PWHEA_MEMORY_ERROR_SECTION_VALIDBITS, *PWHEA_MEMORY_ERROR_VALIDBITS, PWHEA_MEMORY_ERROR_SECTION_VALIDBITS, PWHEA_MEMORY_ERROR_SECTION_VALIDBITS union pointer [WHEA Drivers and Applications], WHEA_MEMORY_ERROR_SECTION_VALIDBITS, WHEA_MEMORY_ERROR_SECTION_VALIDBITS union [WHEA Drivers and Applications], WHEA_MEMORY_ERROR_VALIDBITS, _WHEA_MEMORY_ERROR_SECTION_VALIDBITS, ntddk/PWHEA_MEMORY_ERROR_SECTION_VALIDBITS, ntddk/WHEA_MEMORY_ERROR_SECTION_VALIDBITS, whea.whea_memory_error_section_validbits, whearef_49eab340-c05f-4201-a45d-8602ec121ef3.xml"
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
req.irql: 
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	ntddk.h
api_name:
-	WHEA_MEMORY_ERROR_SECTION_VALIDBITS
product: Windows
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


### -field DUMMYSTRUCTNAME.PhysicalAddress

A single bit that indicates that the <b>PhysicalAddress</b> member of the WHEA_MEMORY_ERROR_SECTION structure contains valid data.


### -field DUMMYSTRUCTNAME.PhysicalAddressMask

A single bit that indicates that the <b>PhysicalAddressMask</b> member of the WHEA_MEMORY_ERROR_SECTION structure contains valid data.


### -field DUMMYSTRUCTNAME.Node

A single bit that indicates that the <b>Node</b> member of the WHEA_MEMORY_ERROR_SECTION structure contains valid data.


### -field DUMMYSTRUCTNAME.Card

A single bit that indicates that the <b>Card</b> member of the WHEA_MEMORY_ERROR_SECTION structure contains valid data.


### -field DUMMYSTRUCTNAME.Module

A single bit that indicates that the <b>Module</b> member of the WHEA_MEMORY_ERROR_SECTION structure contains valid data.


### -field DUMMYSTRUCTNAME.Bank

A single bit that indicates that the <b>Bank</b> member of the WHEA_MEMORY_ERROR_SECTION structure contains valid data.


### -field DUMMYSTRUCTNAME.Device

A single bit that indicates that the <b>Device</b> member of the WHEA_MEMORY_ERROR_SECTION structure contains valid data.


### -field DUMMYSTRUCTNAME.Row

A single bit that indicates that the <b>Row</b> member of the WHEA_MEMORY_ERROR_SECTION structure contains valid data.


### -field DUMMYSTRUCTNAME.Column

A single bit that indicates that the <b>Column</b> member of the WHEA_MEMORY_ERROR_SECTION structure contains valid data.


### -field DUMMYSTRUCTNAME.BitPosition

A single bit that indicates that the <b>BitPosition</b> member of the WHEA_MEMORY_ERROR_SECTION structure contains valid data.


### -field DUMMYSTRUCTNAME.RequesterId

A single bit that indicates that the <b>RequesterId</b> member of the WHEA_MEMORY_ERROR_SECTION structure contains valid data.


### -field DUMMYSTRUCTNAME.ResponderId

A single bit that indicates that the <b>ResponderId</b> member of the WHEA_MEMORY_ERROR_SECTION structure contains valid data.


### -field DUMMYSTRUCTNAME.TargetId

A single bit that indicates that the <b>TargetId</b> member of the WHEA_MEMORY_ERROR_SECTION structure contains valid data.


### -field DUMMYSTRUCTNAME.ErrorType

A single bit that indicates that the <b>ErrorType</b> member of the WHEA_MEMORY_ERROR_SECTION structure contains valid data.


### -field DUMMYSTRUCTNAME.Reserved

Reserved for system use.


### -field ValidBits

A ULONGLONG representation of the contents of the WHEA_MEMORY_ERROR_SECTION_VALIDBITS union.


## -remarks



A WHEA_MEMORY_ERROR_SECTION_VALIDBITS union is contained within the <a href="https://msdn.microsoft.com/library/windows/hardware/ff560565">WHEA_MEMORY_ERROR_SECTION</a> structure.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff560565">WHEA_MEMORY_ERROR_SECTION</a>
 

 

