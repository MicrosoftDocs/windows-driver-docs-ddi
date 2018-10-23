---
UID: NF:ndis.NdisUnicodeStringToAnsiString
title: NdisUnicodeStringToAnsiString macro
author: windows-driver-content
description: The NdisUnicodeStringToAnsiString function converts a given counted Unicode string into a counted ANSI string. The translation conforms to the current system locale information.
old-location: netvista\ndisunicodestringtoansistring.htm
tech.root: netvista
ms.assetid: 37ac55b8-093e-4bf4-9c66-05ab5fc7ebc9
ms.date: 05/02/2018
ms.keywords: NdisUnicodeStringToAnsiString, NdisUnicodeStringToAnsiString macro [Network Drivers Starting with Windows Vista], ndis/NdisUnicodeStringToAnsiString, ndis_string_ref_31235ece-f64c-4806-af32-e3ffffdb7904.xml, netvista.ndisunicodestringtoansistring
ms.topic: macro
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
-	APIRef
-	kbSyntax
api_type:
-	LibDef
api_location:
-	ndis.lib
-	ndis.dll
api_name:
-	NdisUnicodeStringToAnsiString
product:
- Windows
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




<a href="https://msdn.microsoft.com/library/windows/hardware/ff540605">ANSI_STRING</a>



<a href="https://msdn.microsoft.com/library/gg156036.aspx">DriverEntry of NDIS Protocol
   Drivers</a>



<a href="https://msdn.microsoft.com/b146fa81-005b-4a6c-962d-4cb023ea790e">MiniportInitializeEx</a>



<a href="https://msdn.microsoft.com/1958722e-012e-4110-a82c-751744bcf9b5">ProtocolBindAdapterEx</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff561729">RtlAnsiStringToUnicodeString</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff561934">RtlInitUnicodeString</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff564879">UNICODE_STRING</a>
 

 

