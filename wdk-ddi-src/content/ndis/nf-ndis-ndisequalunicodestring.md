---
UID: NF:ndis.NdisEqualUnicodeString
title: NdisEqualUnicodeString macro (ndis.h)
description: The NdisEqualUnicodeString function compares two Unicode strings and returns whether they are equal.
old-location: netvista\ndisequalunicodestring.htm
tech.root: netvista
ms.date: 05/02/2018
keywords: ["NdisEqualUnicodeString macro"]
ms.keywords: NdisEqualUnicodeString, NdisEqualUnicodeString macro [Network Drivers Starting with Windows Vista], ndis/NdisEqualUnicodeString, ndis_string_ref_ccfcf1e6-b983-47a3-a46e-3a6ff1eb7158.xml, netvista.ndisequalunicodestring
req.header: ndis.h
req.include-header: Ndis.h
req.target-type: Desktop
req.target-min-winverclnt: Supported for existing drivers in  NDIS 6.0 and later, but new drivers should use RtlEqualUnicodeString instead.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: Irql_Miscellaneous_Function
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: PASSIVE_LEVEL
targetos: Windows
req.typenames: 
f1_keywords:
 - NdisEqualUnicodeString
 - ndis/NdisEqualUnicodeString
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - ndis.h
api_name:
 - NdisEqualUnicodeString
---

# NdisEqualUnicodeString macro


## -description

The
  <b>NdisEqualUnicodeString</b> function compares two Unicode strings and returns whether they are
  equal.

## -parameters

### -param _String1 

[in]
A pointer to an NDIS_STRING type that describes the first Unicode string.

### -param _String2 

[in]
A pointer to an NDIS_STRING type that describes the second Unicode string.

### -param _CaseInsensitive

A Boolean value that is <b>TRUE</b>, if case should be ignored when doing the comparison. Otherwise, it
     is <b>FALSE</b>.

## -remarks

Starting with Windows 2000 and later drivers, a string of type NDIS_STRING is a counted,
    null-terminated Unicode string. That is, NDIS defines the NDIS_STRING type as a 
    <a href="/windows/win32/api/ntdef/ns-ntdef-_unicode_string">UNICODE_STRING</a> type.

## -see-also

<a href="/windows/win32/api/ntdef/ns-ntdef-_unicode_string">UNICODE_STRING</a>
