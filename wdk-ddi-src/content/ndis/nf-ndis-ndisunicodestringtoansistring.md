---
UID: NF:ndis.NdisUnicodeStringToAnsiString
title: NdisUnicodeStringToAnsiString macro (ndis.h)
description: The NdisUnicodeStringToAnsiString function converts a given counted Unicode string into a counted ANSI string. The translation conforms to the current system locale information.
old-location: netvista\ndisunicodestringtoansistring.htm
tech.root: netvista
ms.assetid: 37ac55b8-093e-4bf4-9c66-05ab5fc7ebc9
ms.date: 05/02/2018
keywords: ["NdisUnicodeStringToAnsiString macro"]
ms.keywords: NdisUnicodeStringToAnsiString, NdisUnicodeStringToAnsiString macro [Network Drivers Starting with Windows Vista], ndis/NdisUnicodeStringToAnsiString, ndis_string_ref_31235ece-f64c-4806-af32-e3ffffdb7904.xml, netvista.ndisunicodestringtoansistring
f1_keywords:
 - "ndis/NdisUnicodeStringToAnsiString"
 - "NdisUnicodeStringToAnsiString"
req.header: ndis.h
req.include-header: Ndis.h
req.target-type: Universal
req.target-min-winverclnt: Supported for existing drivers in  NDIS 6.0 and later, but new drivers should use RtlUnicodeStringToAnsiString instead.
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
topic_type:
- APIRef
- kbSyntax
api_type:
- LibDef
api_location:
- ndis.lib
- ndis.dll
api_name:
- NdisUnicodeStringToAnsiString
targetos: Windows
req.typenames: 
---

# NdisUnicodeStringToAnsiString macro


## -description


The 
  <b>NdisUnicodeStringToAnsiString</b> function converts a given counted Unicode string into a counted ANSI
  string. The translation conforms to the current system locale information.


## -parameters




### -param _as

A pointer to a caller-allocated buffer in which this function should return the converted ANSI
     string.

### -param _us

A pointer to the Unicode string to be converted.


## -remarks



The caller must allocate storage for both the source and destination strings and release these buffers
    as soon as the strings are no longer needed. The buffer at 
    <i>SourceString</i> must be at least twice the size of that at 
    <i>DestinationString</i> .




## -see-also




<a href="https://docs.microsoft.com/windows/win32/api/ntdef/ns-ntdef-string">ANSI_STRING</a>



<a href="https://docs.microsoft.com/previous-versions/windows/embedded/gg156036(v=winembedded.80)">DriverEntry of NDIS Protocol
   Drivers</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nc-ndis-miniport_initialize">MiniportInitializeEx</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nc-ndis-protocol_bind_adapter_ex">ProtocolBindAdapterEx</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-rtlansistringtounicodestring">RtlAnsiStringToUnicodeString</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-rtlinitunicodestring">RtlInitUnicodeString</a>



<a href="https://docs.microsoft.com/windows/win32/api/ntdef/ns-ntdef-_unicode_string">UNICODE_STRING</a>
 

 

