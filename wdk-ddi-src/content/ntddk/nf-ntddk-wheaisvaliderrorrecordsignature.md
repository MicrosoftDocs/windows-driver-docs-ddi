---
UID: NF:ntddk.WheaIsValidErrorRecordSignature
title: WheaIsValidErrorRecordSignature function (ntddk.h)
description: The WheaIsValidErrorRecordSignature function verifies whether a WHEA error record is valid.
old-location: whea\wheaisvaliderrorrecordsignature.htm
tech.root: whea
ms.date: 02/20/2018
keywords: ["WheaIsValidErrorRecordSignature function"]
ms.keywords: WheaIsValidErrorRecordSignature, WheaIsValidErrorRecordSignature function [WHEA Drivers and Applications], ntddk/WheaIsValidErrorRecordSignature, whea.wheaisvaliderrorrecordsignature, whearef2_6ba74e00-cc1f-49e9-b6ee-b300571eb412.xml
req.header: ntddk.h
req.include-header: Ntddk.h
req.target-type: Desktop
req.target-min-winverclnt: Supported in Windows 7 and later versions of Windows.
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
targetos: Windows
req.typenames: 
f1_keywords:
 - WheaIsValidErrorRecordSignature
 - ntddk/WheaIsValidErrorRecordSignature
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - ntddk.h
api_name:
 - WheaIsValidErrorRecordSignature
---

# WheaIsValidErrorRecordSignature function


## -description

The <b>WheaIsValidErrorRecordSignature </b>function verifies whether a WHEA <a href="/windows-hardware/drivers/whea/error-records">error record</a> is valid.

## -parameters

### -param Record 

[in]
A pointer to a WHEA <a href="/windows-hardware/drivers/whea/error-records">error record</a> that is formatted as a <a href="/windows-hardware/drivers/ddi/ntddk/ns-ntddk-_whea_error_record">WHEA_ERROR_RECORD</a> structure.

## -returns

<b>WheaIsValidErrorRecordSignature </b>returns a Boolean value that indicates whether the WHEA <a href="/windows-hardware/drivers/whea/error-records">error record</a> is valid. If it is valid, the function returns <b>TRUE</b>.

## -remarks

The <b>WheaIsValidErrorRecordSignature </b>function verifies that the specified <a href="/windows-hardware/drivers/ddi/ntddk/ns-ntddk-_whea_error_record">WHEA_ERROR_RECORD</a> structure contains valid values.

## -see-also

<a href="/windows-hardware/drivers/whea/error-records">Error record</a>



<a href="/windows-hardware/drivers/ddi/ntddk/ns-ntddk-_whea_error_record">WHEA_ERROR_RECORD</a>



<a href="/windows-hardware/drivers/ddi/ntddk/ns-ntddk-_whea_error_record_header">WHEA_ERROR_RECORD_HEADER</a>
