---
UID: NF:ntddk.WheaGetErrPacketFromErrRecord
title: WheaGetErrPacketFromErrRecord function (ntddk.h)
description: The WheaGetErrPacketFromErrRecord function returns a pointer to the hardware error packet that is contained within a WHEA error record. The hardware error packet is formatted as a WHEA_ERROR_PACKET structure.
old-location: whea\wheageterrpacketfromerrrecord.htm
tech.root: whea
ms.assetid: 8b4a835f-b1ec-4308-8e0d-a13c0f421dc8
ms.date: 02/20/2018
keywords: ["WheaGetErrPacketFromErrRecord function"]
ms.keywords: WheaGetErrPacketFromErrRecord, WheaGetErrPacketFromErrRecord function [WHEA Drivers and Applications], ntddk/WheaGetErrPacketFromErrRecord, whea.wheageterrpacketfromerrrecord, whearef2_c7c202ca-0ed0-4a12-a3f0-64723e6483c6.xml
f1_keywords:
 - "ntddk/WheaGetErrPacketFromErrRecord"
 - "WheaGetErrPacketFromErrRecord"
req.header: ntddk.h
req.include-header: Ntddk.h
req.target-type: Desktop
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
req.irql: <=DISPATCH_LEVEL
topic_type:
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- ntddk.h
api_name:
- WheaGetErrPacketFromErrRecord
targetos: Windows
req.typenames: 
---

# WheaGetErrPacketFromErrRecord function


## -description


The <b>WheaGetErrPacketFromErrRecord</b> function returns a pointer to the hardware error packet that is contained within a WHEA <a href="https://docs.microsoft.com/windows-hardware/drivers/whea/error-records">error record</a>. The hardware error packet is formatted as a <a href="https://docs.microsoft.com/previous-versions/windows/hardware/drivers/ff560465(v=vs.85)">WHEA_ERROR_PACKET</a> structure.


## -parameters




### -param Record 
[in]
A pointer to a WHEA <a href="https://docs.microsoft.com/windows-hardware/drivers/whea/error-records">error record</a> that is formatted as a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddk/ns-ntddk-_whea_error_record">WHEA_ERROR_RECORD</a> structure.


## -returns



<b>WheaGetErrPacketFromErrRecord</b> returns a pointer to the <a href="https://docs.microsoft.com/previous-versions/windows/hardware/drivers/ff560465(v=vs.85)">WHEA_ERROR_PACKET</a> structure within the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddk/ns-ntddk-_whea_error_record">WHEA_ERROR_RECORD</a> structure. If the function does not locate the WHEA_ERROR_PACKET structure, it returns <b>NULL</b>.




## -remarks



The <b>WheaGetErrPacketFromErrRecord</b> function returns a pointer to the hardware error packet that is contained within an error record.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/whea/error-records">Error record</a>



<a href="https://docs.microsoft.com/previous-versions/windows/hardware/drivers/ff560465(v=vs.85)">WHEA_ERROR_PACKET</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddk/ns-ntddk-_whea_error_record">WHEA_ERROR_RECORD</a>
 

 

