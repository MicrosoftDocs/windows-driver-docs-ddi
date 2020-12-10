---
UID: NE:ks.VARENUM
title: VARENUM (ks.h)
description: Specifies the variant types.
old-location: stream\varenum.htm
tech.root: stream
ms.date: 10/09/2020
keywords: ["VARENUM enumeration"]
ms.keywords: VARENUM, VARENUM enumeration [Streaming Media Devices], VT_ARRAY, VT_BLOB, VT_BLOB_OBJECT, VT_BOOL, VT_BSTR, VT_BYREF, VT_CARRAY, VT_CF, VT_CLSID, VT_CY, VT_DATE, VT_DECIMAL, VT_DISPATCH, VT_EMPTY, VT_ERROR, VT_FILETIME, VT_HRESULT, VT_I1, VT_I2, VT_I4, VT_I8, VT_ILLEGAL, VT_ILLEGALMASKED, VT_INT, VT_LPSTR, VT_LPWSTR, VT_NULL, VT_PTR, VT_R4, VT_R8, VT_RESERVED, VT_SAFEARRAY, VT_STORAGE, VT_STORED_OBJECT, VT_STREAM, VT_STREAMED_OBJECT, VT_TYPEMASK, VT_UI1, VT_UI2, VT_UI4, VT_UI8, VT_UINT, VT_UNKNOWN, VT_USERDEFINED, VT_VARIANT, VT_VECTOR, VT_VOID, ks/ VT_RESERVED, ks/ VT_VECTOR, ks/VARENUM, ks/VT_ARRAY, ks/VT_BLOB, ks/VT_BLOB_OBJECT, ks/VT_BOOL, ks/VT_BSTR, ks/VT_BYREF, ks/VT_CARRAY, ks/VT_CF, ks/VT_CLSID, ks/VT_CY, ks/VT_DATE, ks/VT_DECIMAL, ks/VT_DISPATCH, ks/VT_EMPTY, ks/VT_ERROR, ks/VT_FILETIME, ks/VT_HRESULT, ks/VT_I1, ks/VT_I2, ks/VT_I4, ks/VT_I8, ks/VT_ILLEGAL, ks/VT_ILLEGALMASKED, ks/VT_INT, ks/VT_LPSTR, ks/VT_LPWSTR, ks/VT_NULL, ks/VT_PTR, ks/VT_R4, ks/VT_R8, ks/VT_SAFEARRAY, ks/VT_STORAGE, ks/VT_STORED_OBJECT, ks/VT_STREAM, ks/VT_STREAMED_OBJECT, ks/VT_TYPEMASK, ks/VT_UI1, ks/VT_UI2, ks/VT_UI4, ks/VT_UI8, ks/VT_UINT, ks/VT_UNKNOWN, ks/VT_USERDEFINED, ks/VT_VARIANT, ks/VT_VOID, stream.varenum
req.header: ks.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: 
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
targetos: Windows
req.typenames: 
f1_keywords:
 - VARENUM
 - ks/VARENUM
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - Ks.h
api_name:
 - VARENUM
---

# VARENUM enumeration

## -description

Specifies the variant types.

## -enum-fields

### -field VT_EMPTY

Not specified.

### -field VT_NULL

Null.

### -field VT_I2

A 2-byte integer.

### -field VT_I4

A 4-byte integer.

### -field VT_R4

A 4-byte real.

### -field VT_R8

An 8-byte real.

### -field VT_CY

 Currency.

### -field VT_DATE

A date.

### -field VT_BSTR

A string.

### -field VT_DISPATCH

An [IDispatch](/windows/win32/api/oaidl/nn-oaidl-idispatch) pointer.

### -field VT_ERROR

An SCODE value.

### -field VT_BOOL

A Boolean value. True is -1 and false is 0.

### -field VT_VARIANT

A variant pointer.

### -field VT_UNKNOWN

An [IUnknown](/windows/win32/api/unknwn/nn-unknwn-iunknown) pointer.

### -field VT_DECIMAL

A 16-byte fixed-pointer value.

### -field VT_I1

A character.

### -field VT_UI1

An unsigned character.

### -field VT_UI2

An unsigned short.

### -field VT_UI4

An unsigned long.

### -field VT_I8

A 64-bit integer.

### -field VT_UI8

A 64-bit unsigned integer.

### -field VT_INT

An integer.

### -field VT_UINT

An unsigned integer.

### -field VT_VOID

A C-style void.

### -field VT_HRESULT

An HRESULT value.

### -field VT_PTR

A pointer type.

### -field VT_SAFEARRAY

A safe array. Use VT_ARRAY in VARIANT.

### -field VT_CARRAY

A C-style array.

### -field VT_USERDEFINED

A user-defined type.

### -field VT_LPSTR

A null-terminated string.

### -field VT_LPWSTR

A wide null-terminated string.

### -field VT_FILETIME

A [FILETIME](/windows/win32/api/minwinbase/ns-minwinbase-filetime) value.

### -field VT_BLOB

Length-prefixed bytes.

### -field VT_STREAM

The name of the stream follows.

### -field VT_STORAGE

The name of the storage follows.

### -field VT_STREAMED_OBJECT

The stream contains an object.

### -field VT_STORED_OBJECT

The storage contains an object.

### -field VT_BLOB_OBJECT

The blob contains an object.

### -field VT_CF

A clipboard format.

### -field VT_CLSID

A class ID.

### -field VT_BSTR_BLOB

Reserved for system use.

### -field VT_VECTOR

A simple counted array.

### -field VT_ARRAY

A SAFEARRAY pointer.

### -field VT_BYREF

A void pointer for local use.

### -field VT_RESERVED

Reserved.

### -field VT_ILLEGAL

An illegal value.

### -field VT_ILLEGALMASKED

An illegal masked value.

### -field VT_TYPEMASK

A type mask.

## -remarks

The following table shows where these values can be used.

| Value | VARIANT | TYPEDESC | Property set | Safe array |
|--|--|--|--|--|
| VT_ARRAY | X |  |  |  |
| VT_BLOB |  |  | X |  |
| VT_BLOB_OBJECT |  |  | X |  |
| VT_BOOL | X | X | X | X |
| VT_BSTR | X | X | X | X |
| VT_BSTR_BLOB |  |  |  |  |
| VT_BYREF | X |  |  |  |
| VT_CARRAY | X |  |  |  |
| VT_CF |  |  | X |  |
| VT_CLSID |  |  | X |  |
| VT_CY | X | X | X | X |
| VT_DATE | X | X | X | X |
| VT_DECIMAL | X | X |  | X |
| VT_DISPATCH | X | X |  | X |
| VT_EMPTY | X |  | X |  |
| VT_ERROR | X | X | X | X |
| VT_FILETIME |  |  | X |  |
| VT_HRESULT |  |  | X |  |
| VT_I1 | X | X | X | X |
| VT_I2 | X | X | X | X |
| VT_I4 | X | X | X | X |
| VT_I8 |  | X | X |  |
| VT_ILLEGAL |  |  | X |  |
| VT_INT | X | X | X | X |
| VT_LPSTR |  | X | X |  |
| VT_LPWSTR |  | X | X |  |
| VT_NULL | X |  | X |  |
| VT_PTR |  |  | X |  |
| VT_R4 | X | X | X | X |
| VT_R8 | X | X | X | X |
| VT_SAFEARRAY |  | X |  |  |
| VT_STORAGE |  |  | X |  |
| VT_STORED_OBJECT |  |  | X |  |
| VT_STREAM |  |  | X |  |
| VT_STREAMED_OBJECT |  |  | X |  |
| VT_UI1 | X | X | X | X |
| VT_UI2 | X | X | X | X |
| VT_UI4 | X | X | X | X |
| VT_UI8 |  | X | X |  |
| VT_UINT | X | X |  | X |
| VT_UNKNOWN | X | X |  | X |
| VT_USERDEFINED |  |  | X |  |
| VT_VARIANT | X | X | X | X |
| VT_VECTOR |  |  | X |  |
| VT_VOID |  |  | X |  |

**VT_BSTR_BLOB** is reserved for system use.
