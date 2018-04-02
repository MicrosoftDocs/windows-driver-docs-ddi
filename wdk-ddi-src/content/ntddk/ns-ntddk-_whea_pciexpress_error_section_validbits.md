---
UID: NS:ntddk._WHEA_PCIEXPRESS_ERROR_SECTION_VALIDBITS
title: "_WHEA_PCIEXPRESS_ERROR_SECTION_VALIDBITS"
author: windows-driver-content
description: The WHEA_PCIEXPRESS_ERROR_SECTION_VALIDBITS union describes which members of a WHEA_PCIEXPRESS_ERROR_SECTION structure contain valid data.
old-location: whea\whea_pciexpress_error_section_validbits.htm
old-project: whea
ms.assetid: 1c4c3e9c-32a2-405a-b27d-98f8da715626
ms.author: windowsdriverdev
ms.date: 2/20/2018
ms.keywords: "*PWHEA_PCIEXPRESS_ERROR_SECTION_VALIDBITS, *PWHEA_PCIEXPRESS_ERROR_VALIDBITS, PWHEA_PCIEXPRESS_ERROR_SECTION_VALIDBITS, PWHEA_PCIEXPRESS_ERROR_SECTION_VALIDBITS union pointer [WHEA Drivers and Applications], WHEA_PCIEXPRESS_ERROR_SECTION_VALIDBITS, WHEA_PCIEXPRESS_ERROR_SECTION_VALIDBITS union [WHEA Drivers and Applications], WHEA_PCIEXPRESS_ERROR_VALIDBITS, _WHEA_PCIEXPRESS_ERROR_SECTION_VALIDBITS, ntddk/PWHEA_PCIEXPRESS_ERROR_SECTION_VALIDBITS, ntddk/WHEA_PCIEXPRESS_ERROR_SECTION_VALIDBITS, whea.whea_pciexpress_error_section_validbits, whearef_9b6e3f92-4939-401a-9da2-e2ece44b1e98.xml"
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
-	WHEA_PCIEXPRESS_ERROR_SECTION_VALIDBITS
product: Windows
targetos: Windows
req.typenames: WHEA_PCIEXPRESS_ERROR_SECTION_VALIDBITS, *PWHEA_PCIEXPRESS_ERROR_SECTION_VALIDBITS
---

# _WHEA_PCIEXPRESS_ERROR_SECTION_VALIDBITS structure


## -description


The WHEA_PCIEXPRESS_ERROR_SECTION_VALIDBITS union describes which members of a <a href="https://msdn.microsoft.com/library/windows/hardware/ff560576">WHEA_PCIEXPRESS_ERROR_SECTION</a> structure contain valid data.


## -struct-fields




### -field DUMMYSTRUCTNAME

 


### -field ValidBits

A ULONGLONG representation of the contents of the WHEA_PCIEXPRESS_ERROR_SECTION_VALIDBITS union.


#### - AerInfo

A single bit that indicates that the <b>AerInfo</b> member of the WHEA_PCIEXPRESS_ERROR_SECTION structure contains valid data.


#### - BridgeControlStatus

A single bit that indicates that the <b>BridgeControlStatus</b> member of the WHEA_PCIEXPRESS_ERROR_SECTION structure contains valid data.


#### - CommandStatus

A single bit that indicates that the <b>CommandStatus</b> member of the WHEA_PCIEXPRESS_ERROR_SECTION structure contains valid data.


#### - DeviceId

A single bit that indicates that the <b>DeviceId</b> member of the WHEA_PCIEXPRESS_ERROR_SECTION structure contains valid data.


#### - DeviceSerialNumber

A single bit that indicates that the <b>DeviceSerialNumber</b> member of the WHEA_PCIEXPRESS_ERROR_SECTION structure contains valid data.


#### - ExpressCapability

A single bit that indicates that the <b>ExpressCapability</b> member of the WHEA_PCIEXPRESS_ERROR_SECTION structure contains valid data.


#### - PortType

A single bit that indicates that the <b>PortType</b> member of the WHEA_PCIEXPRESS_ERROR_SECTION structure contains valid data.


#### - Reserved

Reserved for system use.


#### - Version

A single bit that indicates that the <b>Version</b> member of the WHEA_PCIEXPRESS_ERROR_SECTION structure contains valid data.


## -remarks



A WHEA_PCIEXPRESS_ERROR_SECTION_VALIDBITS union is contained within the <a href="https://msdn.microsoft.com/library/windows/hardware/ff560576">WHEA_PCIEXPRESS_ERROR_SECTION</a> structure.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff560576">WHEA_PCIEXPRESS_ERROR_SECTION</a>
 

 

