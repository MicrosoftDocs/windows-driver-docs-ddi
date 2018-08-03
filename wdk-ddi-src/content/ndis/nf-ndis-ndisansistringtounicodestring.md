---
UID: NF:ndis.NdisAnsiStringToUnicodeString
title: NdisAnsiStringToUnicodeString macro
author: windows-driver-content
description: The NdisAnsiStringToUnicodeString function converts a given counted ANSI string into a counted Unicode string. The translation conforms to the current system locale information.
old-location: netvista\ndisansistringtounicodestring.htm
tech.root: netvista
ms.assetid: 8efdcf9f-df8c-4b3b-8b21-11a10a885322
ms.author: windowsdriverdev
ms.date: 5/2/2018
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
product:
- Windows
targetos: Windows
req.typenames: 
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




<a href="https://msdn.microsoft.com/library/windows/hardware/ff540605">ANSI_STRING</a>



<a href="https://msdn.microsoft.com/en-us/library/gg156036.aspx">DriverEntry of NDIS Protocol
   Drivers</a>



<a href="https://msdn.microsoft.com/b146fa81-005b-4a6c-962d-4cb023ea790e">MiniportInitializeEx</a>



<a href="https://msdn.microsoft.com/1958722e-012e-4110-a82c-751744bcf9b5">ProtocolBindAdapterEx</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff561934">RtlInitUnicodeString</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff562969">RtlUnicodeStringToAnsiString</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff564879">UNICODE_STRING</a>
 

 

