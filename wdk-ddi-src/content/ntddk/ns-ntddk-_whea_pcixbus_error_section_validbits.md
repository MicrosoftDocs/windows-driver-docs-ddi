---
UID: NS:ntddk._WHEA_PCIXBUS_ERROR_SECTION_VALIDBITS
title: _WHEA_PCIXBUS_ERROR_SECTION_VALIDBITS (ntddk.h)
description: The WHEA_PCIXBUS_ERROR_SECTION_VALIDBITS union describes which members of a WHEA_PCIXBUS_ERROR_SECTION structure contain valid data.
old-location: whea\whea_pcixbus_error_section_validbits.htm
tech.root: whea
ms.assetid: 85f14500-9cf6-42a6-a302-0990b99ddb5f
ms.date: 02/20/2018
keywords: ["WHEA_PCIXBUS_ERROR_SECTION_VALIDBITS structure"]
ms.keywords: "*PWHEA_PCIXBUS_ERROR_SECTION_VALIDBITS, *PWHEA_PCIXBUS_ERROR_VALIDBITS, PWHEA_PCIXBUS_ERROR_SECTION_VALIDBITS, PWHEA_PCIXBUS_ERROR_SECTION_VALIDBITS union pointer [WHEA Drivers and Applications], WHEA_PCIXBUS_ERROR_SECTION_VALIDBITS, WHEA_PCIXBUS_ERROR_SECTION_VALIDBITS union [WHEA Drivers and Applications], WHEA_PCIXBUS_ERROR_VALIDBITS, _WHEA_PCIXBUS_ERROR_SECTION_VALIDBITS, ntddk/PWHEA_PCIXBUS_ERROR_SECTION_VALIDBITS, ntddk/WHEA_PCIXBUS_ERROR_SECTION_VALIDBITS, whea.whea_pcixbus_error_section_validbits, whearef_a01d7635-52ac-4b47-98f9-b09601dce4ff.xml"
f1_keywords:
 - "ntddk/WHEA_PCIXBUS_ERROR_SECTION_VALIDBITS"
 - "WHEA_PCIXBUS_ERROR_SECTION_VALIDBITS"
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
- WHEA_PCIXBUS_ERROR_SECTION_VALIDBITS
targetos: Windows
req.typenames: WHEA_PCIXBUS_ERROR_SECTION_VALIDBITS, *PWHEA_PCIXBUS_ERROR_SECTION_VALIDBITS
---

# _WHEA_PCIXBUS_ERROR_SECTION_VALIDBITS structure


## -description


The WHEA_PCIXBUS_ERROR_SECTION_VALIDBITS union describes which members of a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddk/ns-ntddk-_whea_pcixbus_error_section">WHEA_PCIXBUS_ERROR_SECTION</a> structure contain valid data.


## -struct-fields




### -field DUMMYSTRUCTNAME

 


### -field DUMMYSTRUCTNAME.ErrorStatus

A single bit that indicates that the <b>ErrorStatus</b> member of the WHEA_PCIXBUS_ERROR_SECTION structure contains valid data.


### -field DUMMYSTRUCTNAME.ErrorType

A single bit that indicates that the <b>ErrorType</b> member of the WHEA_PCIXBUS_ERROR_SECTION structure contains valid data.


### -field DUMMYSTRUCTNAME.BusId

A single bit that indicates that the <b>BusId</b> member of the WHEA_PCIXBUS_ERROR_SECTION structure contains valid data.


### -field DUMMYSTRUCTNAME.BusAddress

A single bit that indicates that the <b>BusAddress</b> member of the WHEA_PCIXBUS_ERROR_SECTION structure contains valid data.


### -field DUMMYSTRUCTNAME.BusData

A single bit that indicates that the <b>BusData</b> member of the WHEA_PCIXBUS_ERROR_SECTION structure contains valid data.


### -field DUMMYSTRUCTNAME.BusCommand

A single bit that indicates that the <b>BusCommand</b> member of the WHEA_PCIXBUS_ERROR_SECTION structure contains valid data.


### -field DUMMYSTRUCTNAME.RequesterId

A single bit that indicates that the <b>RequesterId</b> member of the WHEA_PCIXBUS_ERROR_SECTION structure contains valid data.


### -field DUMMYSTRUCTNAME.CompleterId

A single bit that indicates that the <b>CompleterId</b> member of the WHEA_PCIXBUS_ERROR_SECTION structure contains valid data.


### -field DUMMYSTRUCTNAME.TargetId

A single bit that indicates that the <b>TargetId</b> member of the WHEA_PCIXBUS_ERROR_SECTION structure contains valid data.


### -field DUMMYSTRUCTNAME.Reserved

Reserved for system use.


### -field ValidBits

A ULONGLONG representation of the contents of the WHEA_PCIXBUS_ERROR_SECTION_VALIDBITS union.


## -remarks



A WHEA_PCIXBUS_ERROR_SECTION_VALIDBITS union is contained within the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddk/ns-ntddk-_whea_pcixbus_error_section">WHEA_PCIXBUS_ERROR_SECTION</a> structure.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddk/ns-ntddk-_whea_pcixbus_error_section">WHEA_PCIXBUS_ERROR_SECTION</a>
 

 

