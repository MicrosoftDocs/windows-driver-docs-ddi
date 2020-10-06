---
UID: NF:ndis.NdisAnsiStringToUnicodeString
title: NdisAnsiStringToUnicodeString macro (ndis.h)
description: The NdisAnsiStringToUnicodeString function converts a given counted ANSI string into a counted Unicode string. The translation conforms to the current system locale information.
old-location: netvista\ndisansistringtounicodestring.htm
tech.root: netvista
ms.assetid: 8efdcf9f-df8c-4b3b-8b21-11a10a885322
ms.date: 05/02/2018
keywords: ["NdisAnsiStringToUnicodeString macro"]
ms.keywords: NdisAnsiStringToUnicodeString, NdisAnsiStringToUnicodeString macro [Network Drivers Starting with Windows Vista], ndis/NdisAnsiStringToUnicodeString, ndis_string_ref_e56d613a-b145-4f9e-bb96-3e4d8ad33538.xml, netvista.ndisansistringtounicodestring
req.header: ndis.h
req.include-header: Ndis.h
req.target-type: Universal
req.target-min-winverclnt: Supported for existing drivers in  NDIS 6.0 and later, but new drivers should use RtlAnsiStringToUnicodeString instead.
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
req.lib: Ndis.lib
req.dll: 
req.irql: PASSIVE_LEVEL
targetos: Windows
req.typenames: 
f1_keywords:
 - NdisAnsiStringToUnicodeString
 - ndis/NdisAnsiStringToUnicodeString
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - LibDef
api_location:
 - ndis.lib
 - ndis.dll
api_name:
 - NdisAnsiStringToUnicodeString
---

# NdisAnsiStringToUnicodeString macro


## -description

The 
  <b>NdisAnsiStringToUnicodeString</b> function converts a given counted ANSI string into a counted Unicode
  string. The translation conforms to the current system locale information.

## -parameters

### -param _us

A pointer to a caller-allocated buffer in which this function should return the converted Unicode
     string.

### -param _as

A pointer to the ANSI string to be converted.

## -remarks

The caller must allocate storage for both the source and destination strings and release these buffers
    as soon as the strings are no longer needed. The buffer at 
    <i>DestinationString</i> must be at least twice the size of the buffer at 
    <i>SourceString</i> .

## -see-also

<a href="/windows/win32/api/ntdef/ns-ntdef-string">ANSI_STRING</a>



<a href="/previous-versions/windows/embedded/gg156036(v=winembedded.80)">DriverEntry of NDIS Protocol
   Drivers</a>



<a href="/windows-hardware/drivers/ddi/ndis/nc-ndis-miniport_initialize">MiniportInitializeEx</a>



<a href="/windows-hardware/drivers/ddi/ndis/nc-ndis-protocol_bind_adapter_ex">ProtocolBindAdapterEx</a>



<a href="/windows-hardware/drivers/ddi/wdm/nf-wdm-rtlinitunicodestring">RtlInitUnicodeString</a>



<a href="/windows-hardware/drivers/ddi/wdm/nf-wdm-rtlunicodestringtoansistring">RtlUnicodeStringToAnsiString</a>



<a href="/windows/win32/api/ntdef/ns-ntdef-_unicode_string">UNICODE_STRING</a>