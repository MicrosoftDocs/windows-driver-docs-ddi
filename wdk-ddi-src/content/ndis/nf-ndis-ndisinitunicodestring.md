---
UID: NF:ndis.NdisInitUnicodeString
title: NdisInitUnicodeString macro (ndis.h)
description: The NdisInitUnicodeString function initializes a counted Unicode string.
old-location: netvista\ndisinitunicodestring.htm
tech.root: netvista
ms.assetid: 073feb91-48ae-4ad5-9061-117e6541021c
ms.date: 05/02/2018
ms.keywords: NdisInitUnicodeString, NdisInitUnicodeString macro [Network Drivers Starting with Windows Vista], ndis/NdisInitUnicodeString, ndis_string_ref_a25a98b2-f88b-4a56-9bb7-77a4e6dc10a6.xml, netvista.ndisinitunicodestring
f1_keywords:
 - "ndis/NdisInitUnicodeString"
req.header: ndis.h
req.include-header: Ndis.h
req.target-type: Universal
req.target-min-winverclnt: Supported for NDIS 6.0 and NDIS 5.1 drivers (see    NdisInitUnicodeString (NDIS   5.1)) in Windows Vista. Supported for NDIS 5.1 drivers (see    NdisInitUnicodeString (NDIS   5.1)) in Windows XP.
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
req.irql: See Remarks section
topic_type:
- APIRef
- kbSyntax
api_type:
- LibDef
api_location:
- ndis.lib
- ndis.dll
api_name:
- NdisInitUnicodeString
product:
- Windows
targetos: Windows
req.typenames: 
---

# NdisInitUnicodeString macro


## -description


The 
  <b>NdisInitUnicodeString</b> function initializes a counted Unicode string.


## -parameters




### -param _us

A pointer to a caller-allocated NDIS_STRING type in which 
     <b>NdisInitUnicodeString</b> should store the counted Unicode string. For Windows 2000 and later, NDIS
     defines the NDIS_STRING type as a 
     <a href="https://docs.microsoft.com/windows/desktop/api/ntdef/ns-ntdef-_unicode_string">UNICODE_STRING</a> type.


### -param s

A pointer to a null-terminated string with which to initialize the counted string.

## -remarks



The 
    <i>DestinationString</i> is initialized to point to the 
    <i>SourceString</i> . The 
    <b>Length</b> and 
    <b>MaximumLength</b> members of NDIS_STRING for the 
    <i>DestinationString</i> are initialized to the length of the string at 
    <i>SourceString</i>. If 
    <i>SourceString</i> is <b>NULL</b>, the length is zero.

Callers of 
    <b>NdisInitUnicodeString</b> must be running at IRQL <= DISPATCH_LEVEL if the 
    <i>DestinationString</i> buffer is allocated from nonpaged memory. Usually, callers are running at IRQL =
    PASSIVE_LEVEL during driver initialization.




## -see-also




<a href="https://docs.microsoft.com/previous-versions/windows/embedded/gg156036(v=winembedded.80)">DriverEntry of NDIS Protocol
   Drivers</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nc-ndis-miniport_initialize">MiniportInitializeEx</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nf-ndis-ndisansistringtounicodestring">
   NdisAnsiStringToUnicodeString</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nf-ndis-ndisinitansistring">NdisInitAnsiString</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nf-ndis-ndisinitializestring">NdisInitializeString</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nf-ndis-ndisunicodestringtoansistring">
   NdisUnicodeStringToAnsiString</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nc-ndis-protocol_bind_adapter_ex">ProtocolBindAdapterEx</a>



<a href="https://docs.microsoft.com/windows/desktop/api/ntdef/ns-ntdef-_unicode_string">UNICODE_STRING</a>
 

 

