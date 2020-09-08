---
UID: NE:dbgmodel.PreferredFormat
title: PreferredFormat (dbgmodel.h)
description: Predefined values of the "PreferredFormat" key which may appear as the metadata on a returned key value.
ms.assetid: 13729758-f5f8-4f28-80b8-ed8c89d56db5
ms.date: 07/16/2018
keywords: ["PreferredFormat enumeration"]
ms.keywords: PreferredFormat, ,
req.header: dbgmodel.h
req.include-header: 
req.target-type: 
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: 
req.max-support: 
req.typenames: 
targetos: Windows
tech.root: debugger
ms.custom: RS5
f1_keywords:
 - PreferredFormat
 - dbgmodel/PreferredFormat
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - dbgmodel.h
api_name:
 - PreferredFormat
---

# PreferredFormat enumeration


## -description

Predefined values of the "PreferredFormat" key which may appear as the metadata on a returned key value.  This indicates the preferred DISPLAY FORMAT for a given value.

## -enum-fields

### -field FormatNone 

There is no preferred format

### -field FormatSingleCharacter 

The preferred format is a single character as '*'

### -field FormatQuotedString 

The preferred format is a quoted 8-bit string

### -field FormatString 

The preferred format is a non-quoted 8-bit string

### -field FormatQuotedUnicodeString 

The preferred format is a quoted Unicode (UTF-16) string

### -field FormatUnicodeString 

The preferred format is a non-quoted Unicode (UTF-16) string

### -field FormatQuotedUTF8String 

The preferred format is a quoted UTF-8 string

### -field FormatUTF8String 

The preferred format is a non-quoted UTF-8 string

### -field FormatBSTRString 

The preferred format is a quoted BSTR

### -field FormatQuotedHString 

The preferred format is a quoted WinRT HSTRING

### -field FormatHString 

The preferred format is a non-quoted WinRT HSTRING

### -field FormatRaw 

The preferred format is the raw (native) type

### -field FormatEnumNameOnly 

The preferred format is the enum name only

### -field FormatEscapedStringWithQuote 

The preferred format is the quoted string with escaped characters

### -field FormatUTF32String 

The preferred format is a non-quoted Unicode (UTF-32) string

### -field FormatQuotedUTF32String 

The preferred format is a quoted Unicode (UTF-32) string

## -remarks

## -see-also

[Debugger Data Model C++ Overview](https://docs.microsoft.com/windows-hardware/drivers/debugger/data-model-cpp-overview)

