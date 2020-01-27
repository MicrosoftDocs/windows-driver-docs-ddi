---
UID: NS:ntddk._WHEA_TIMESTAMP
title: _WHEA_TIMESTAMP (ntddk.h)
description: The WHEA_TIMESTAMP union describes the time that an error was reported to the operating system.
old-location: whea\whea_timestamp.htm
tech.root: whea
ms.assetid: 70a6555d-1da9-4013-911a-4a9d011b0205
ms.date: 02/20/2018
ms.keywords: "*PWHEA_TIMESTAMP, PWHEA_TIMESTAMP, PWHEA_TIMESTAMP union pointer [WHEA Drivers and Applications], WHEA_TIMESTAMP, WHEA_TIMESTAMP union [WHEA Drivers and Applications], _WHEA_TIMESTAMP, ntddk/PWHEA_TIMESTAMP, ntddk/WHEA_TIMESTAMP, whea.whea_timestamp, whearef_d0fafe3b-0cea-4adf-a68a-b565e04ae258.xml"
f1_keywords:
 - "ntddk/WHEA_TIMESTAMP"
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
- WHEA_TIMESTAMP
product:
- Windows
targetos: Windows
req.typenames: WHEA_TIMESTAMP, *PWHEA_TIMESTAMP
---

# _WHEA_TIMESTAMP structure


## -description


The WHEA_TIMESTAMP union describes the time that an error was reported to the operating system.


## -struct-fields




### -field DUMMYSTRUCTNAME

 


### -field DUMMYSTRUCTNAME.Seconds

The number of seconds past the minute.


### -field DUMMYSTRUCTNAME.Minutes

The number of minutes past the hour.


### -field DUMMYSTRUCTNAME.Hours

The hour in the day.


### -field DUMMYSTRUCTNAME.Precise

If this member is set to 1, the timestamp correlates precisely to the time of the error event.

<div class="alert"><b>Note</b>  This member is supported in Windows 7 and later versions of Windows.</div>
<div> </div>

### -field DUMMYSTRUCTNAME.Reserved

Reserved for system use.


### -field DUMMYSTRUCTNAME.Day

The day of the month.


### -field DUMMYSTRUCTNAME.Month

The month of the year.


### -field DUMMYSTRUCTNAME.Year

The year within the century.


### -field DUMMYSTRUCTNAME.Century

The century.


### -field AsLARGE_INTEGER

A LARGE_INTEGER representation of the contents of the WHEA_TIMESTAMP union.


## -remarks



A WHEA_TIMESTAMP union is contained within the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddk/ns-ntddk-_whea_error_record_header">WHEA_ERROR_RECORD_HEADER</a> structure.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddk/ns-ntddk-_whea_error_record_header">WHEA_ERROR_RECORD_HEADER</a>
 

 

