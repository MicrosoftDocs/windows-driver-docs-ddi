---
UID: NF:ndis.NdisAnsiStringToUnicodeString
title: NdisAnsiStringToUnicodeString macro
author: windows-driver-content
description: The NdisAnsiStringToUnicodeString function converts a given counted ANSI string into a counted Unicode string. The translation conforms to the current system locale information.
old-location: netvista\ndisansistringtounicodestring.htm
old-project: netvista
ms.assetid: 8efdcf9f-df8c-4b3b-8b21-11a10a885322
ms.author: windowsdriverdev
ms.date: 2/27/2018
ms.keywords: NdisAnsiStringToUnicodeString, NdisAnsiStringToUnicodeString macro [Network Drivers Starting with Windows Vista], ndis/NdisAnsiStringToUnicodeString, ndis_string_ref_e56d613a-b145-4f9e-bb96-3e4d8ad33538.xml, netvista.ndisansistringtounicodestring
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: macro
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	LibDef
api_location:
-	ndis.lib
-	ndis.dll
api_name:
-	NdisAnsiStringToUnicodeString
product: Windows
targetos: Windows
req.typenames: NDIS_SHARED_MEMORY_USAGE, *PNDIS_SHARED_MEMORY_USAGE
---

# NdisAnsiStringToUnicodeString macro


## -description


The 
  <b>NdisAnsiStringToUnicodeString</b> function converts a given counted ANSI string into a counted Unicode
  string. The translation conforms to the current system locale information.


## -syntax


````
NDIS_STATUS NdisAnsiStringToUnicodeString(
  [in, out] PUNICODE_STRING DestinationString,
  [in]      PANSI_STRING    SourceString
);
````


## -parameters




### -param _us

TBD


### -param _as

TBD






#### - DestinationString [in, out]

A pointer to a caller-allocated buffer in which this function should return the converted Unicode
     string.


#### - SourceString [in]

A pointer to the ANSI string to be converted.


## -remarks



The caller must allocate storage for both the source and destination strings and release these buffers
    as soon as the strings are no longer needed. The buffer at 
    <i>DestinationString</i> must be at least twice the size of the buffer at 
    <i>SourceString</i> .




## -see-also

<a href="..\wudfwdm\ns-wudfwdm-_unicode_string.md">UNICODE_STRING</a>



<a href="..\wdm\nf-wdm-rtlunicodestringtoansistring.md">RtlUnicodeStringToAnsiString</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff540605">ANSI_STRING</a>



<a href="https://msdn.microsoft.com/en-us/library/gg156036.aspx">DriverEntry of NDIS Protocol
   Drivers</a>



<a href="..\wudfwdm\nf-wudfwdm-rtlinitunicodestring.md">RtlInitUnicodeString</a>



<a href="..\ndis\nc-ndis-protocol_bind_adapter_ex.md">ProtocolBindAdapterEx</a>



<a href="..\ndis\nc-ndis-miniport_initialize.md">MiniportInitializeEx</a>



 

 


