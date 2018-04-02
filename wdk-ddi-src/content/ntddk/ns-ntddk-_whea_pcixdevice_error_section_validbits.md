---
UID: NS:ntddk._WHEA_PCIXDEVICE_ERROR_SECTION_VALIDBITS
title: "_WHEA_PCIXDEVICE_ERROR_SECTION_VALIDBITS"
author: windows-driver-content
description: The WHEA_PCIXDEVICE_ERROR_SECTION_VALIDBITS union describes which members of a WHEA_PCIXDEVICE_ERROR_SECTION structure contain valid data.
old-location: whea\whea_pcixdevice_error_section_validbits.htm
old-project: whea
ms.assetid: 705cfd2c-b4c0-4a59-a494-f57007e13385
ms.author: windowsdriverdev
ms.date: 2/20/2018
ms.keywords: "*PWHEA_PCIXDEVICE_ERROR_SECTION_VALIDBITS, *PWHEA_PCIXDEVICE_ERROR_VALIDBITS, PWHEA_PCIXDEVICE_ERROR_SECTION_VALIDBITS, PWHEA_PCIXDEVICE_ERROR_SECTION_VALIDBITS union pointer [WHEA Drivers and Applications], WHEA_PCIXDEVICE_ERROR_SECTION_VALIDBITS, WHEA_PCIXDEVICE_ERROR_SECTION_VALIDBITS union [WHEA Drivers and Applications], WHEA_PCIXDEVICE_ERROR_VALIDBITS, _WHEA_PCIXDEVICE_ERROR_SECTION_VALIDBITS, ntddk/PWHEA_PCIXDEVICE_ERROR_SECTION_VALIDBITS, ntddk/WHEA_PCIXDEVICE_ERROR_SECTION_VALIDBITS, whea.whea_pcixdevice_error_section_validbits, whearef_aa4d8f33-e22c-46df-8bb7-408cf04db2d1.xml"
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
-	WHEA_PCIXDEVICE_ERROR_SECTION_VALIDBITS
product:
- Windows
targetos: Windows
req.typenames: WHEA_PCIXDEVICE_ERROR_SECTION_VALIDBITS, *PWHEA_PCIXDEVICE_ERROR_SECTION_VALIDBITS
---

# _WHEA_PCIXDEVICE_ERROR_SECTION_VALIDBITS structure


## -description


The WHEA_PCIXDEVICE_ERROR_SECTION_VALIDBITS union describes which members of a <a href="https://msdn.microsoft.com/library/windows/hardware/ff560589">WHEA_PCIXDEVICE_ERROR_SECTION</a> structure contain valid data.


## -struct-fields




### -field DUMMYSTRUCTNAME

 


### -field ValidBits

A ULONGLONG representation of the contents of the WHEA_PCIXDEVICE_ERROR_SECTION_VALIDBITS union.


#### - ErrorStatus

A single bit that indicates that the <b>ErrorStatus</b> member of the WHEA_PCIXDEVICE_ERROR_SECTION structure contains valid data.


#### - IdInfo

A single bit that indicates that the <b>IdInfo</b> member of the WHEA_PCIXDEVICE_ERROR_SECTION structure contains valid data.


#### - IoNumber

A single bit that indicates that the <b>IoNumber</b> member of the WHEA_PCIXDEVICE_ERROR_SECTION structure contains valid data.


#### - MemoryNumber

A single bit that indicates that the <b>MemoryNumber</b> member of the WHEA_PCIXDEVICE_ERROR_SECTION structure contains valid data.


#### - RegisterDataPairs

A single bit that indicates that the <b>RegisterDataPairs</b> member of the WHEA_PCIXDEVICE_ERROR_SECTION structure contains valid data.


#### - Reserved

Reserved for system use.


## -remarks



A WHEA_PCIXDEVICE_ERROR_SECTION_VALIDBITS union is contained within the <a href="https://msdn.microsoft.com/library/windows/hardware/ff560589">WHEA_PCIXDEVICE_ERROR_SECTION</a> structure.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff560589">WHEA_PCIXDEVICE_ERROR_SECTION</a>
 

 

