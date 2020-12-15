---
UID: NF:wdm.RtlInitUTF8String
title: RtlInitUTF8String function
description: TBD
tech.root: kernel
ms.date: 03/24/2020
ms.topic: function
ms.keywords: RtlInitUTF8String
req.header: wdm.h
req.include-header: 
req.target-type: 
req.target-min-winverclnt: Windows 10, version 2004
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.lib: 
req.dll: 
req.irql: 
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
targetos: Windows
topic_type:
 - apiref
api_type:
 - DllExport
api_location:
 - wdm.h
api_name:
 - RtlInitUTF8String
product:
 - Windows
f1_keywords:
 - RtlInitUTF8String
 - wdm/RtlInitUTF8String
---

# RtlInitUTF8String function


## -description

The **RtlInitUTF8String** function initializes a counted string of UTF-8 characters.

## -parameters

### -param DestinationString

A pointer to **UTF8_STRING** (**STRING**) structure to be initialized.

### -param SourceString

Optional pointer to a null-terminated character string. This string is used to initialize the counted string pointed to by <i>DestinationString</i>.

## -returns

None

## -remarks

The routine copies the <i>SourceString</i> pointer value to the <b>Buffer</b> member of the [**UTF8_STRING**](/windows/win32/api/ntdef/ns-ntdef-string) structure pointed to by <i>DestinationString</i>. The <b>Length</b> member of this structure is set to the length, in bytes, of the source string, excluding the terminating null. The <b>MaximumLength</b> member of the structure is set to the length, in bytes, of the source string, including the terminating null. If <i>SourceString</i> is <b>NULL</b>, <b>Length</b> and <b>MaximumLength</b> are both set to zero.

<b>RtlInitUTF8String</b> does not alter the source string pointed to by <i>SourceString</i>.

## -see-also

[**RtlInitAnsiString**](./nf-wdm-rtlinitansistring.md)
