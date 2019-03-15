---
UID: NF:ntddk.WheaIsValidErrorRecordSignature
title: WheaIsValidErrorRecordSignature function (ntddk.h)
description: The WheaIsValidErrorRecordSignature function verifies whether a WHEA error record is valid.
old-location: whea\wheaisvaliderrorrecordsignature.htm
tech.root: whea
ms.assetid: 35149395-4238-41fd-ae96-6491534e3cc1
ms.date: 02/20/2018
ms.keywords: WheaIsValidErrorRecordSignature, WheaIsValidErrorRecordSignature function [WHEA Drivers and Applications], ntddk/WheaIsValidErrorRecordSignature, whea.wheaisvaliderrorrecordsignature, whearef2_6ba74e00-cc1f-49e9-b6ee-b300571eb412.xml
ms.topic: function
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
req.irql: "<=DISPATCH_LEVEL"
topic_type:
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- ntddk.h
api_name:
- WheaIsValidErrorRecordSignature
product:
- Windows
targetos: Windows
req.typenames: 
---

# WheaIsValidErrorRecordSignature function


## -description


The <b>WheaIsValidErrorRecordSignature </b>function verifies whether a WHEA <a href="https://msdn.microsoft.com/080da29a-b5cb-45a5-848d-048d9612ee2a">error record</a> is valid.


## -parameters




### -param Record [in]

A pointer to a WHEA <a href="https://msdn.microsoft.com/080da29a-b5cb-45a5-848d-048d9612ee2a">error record</a> that is formatted as a <a href="https://msdn.microsoft.com/library/windows/hardware/ff560483">WHEA_ERROR_RECORD</a> structure.


## -returns



<b>WheaIsValidErrorRecordSignature </b>returns a Boolean value that indicates whether the WHEA <a href="https://msdn.microsoft.com/080da29a-b5cb-45a5-848d-048d9612ee2a">error record</a> is valid. If it is valid, the function returns <b>TRUE</b>.




## -remarks



The <b>WheaIsValidErrorRecordSignature </b>function verifies that the specified <a href="https://msdn.microsoft.com/library/windows/hardware/ff560483">WHEA_ERROR_RECORD</a> structure contains valid values.




## -see-also




<a href="https://msdn.microsoft.com/080da29a-b5cb-45a5-848d-048d9612ee2a">Error record</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff560483">WHEA_ERROR_RECORD</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff560487">WHEA_ERROR_RECORD_HEADER</a>
 

 

