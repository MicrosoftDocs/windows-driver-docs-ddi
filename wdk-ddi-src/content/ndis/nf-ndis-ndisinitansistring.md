---
UID: NF:ndis.NdisInitAnsiString
title: NdisInitAnsiString macro
author: windows-driver-content
description: The NdisInitAnsiString function initializes a counted ANSI string.
old-location: netvista\ndisinitansistring.htm
tech.root: netvista
ms.assetid: e8209781-36b1-4008-94bb-82bdb16f20bf
ms.date: 05/02/2018
ms.keywords: NdisInitAnsiString, NdisInitAnsiString macro [Network Drivers Starting with Windows Vista], ndis/NdisInitAnsiString, ndis_string_ref_2d47b8b6-3b3e-48ca-a2be-ee1bca117ef6.xml, netvista.ndisinitansistring
ms.topic: macro
req.header: ndis.h
req.include-header: Ndis.h
req.target-type: Universal
req.target-min-winverclnt: Supported for existing drivers in  NDIS 6.0 and later, but new drivers should use RtlInitString instead.
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
-	APIRef
-	kbSyntax
api_type:
-	LibDef
api_location:
-	ndis.lib
-	ndis.dll
api_name:
-	NdisInitAnsiString
product:
- Windows
targetos: Windows
req.typenames: 
---

# NdisInitAnsiString macro


## -description


The 
  <b>NdisInitAnsiString</b> function initializes a counted ANSI string.


## -parameters




### -param _as

A pointer to a caller-allocated buffer in which this function should store the counted ANSI
     string.

### -param s

A pointer to a null-terminated string with which to initialize the counted string.

## -remarks



The 
    <i>DestinationString</i> is initialized to point to the 
    <i>SourceString</i>. The length and maximum length for the 
    <i>DestinationString</i> are initialized to the length of the string at 
    <i>SourceString</i>. If 
    <i>SourceString</i> is <b>NULL</b>, the length is zero.

Callers of 
    <b>NdisInitAnsiString</b> must be running at IRQL &lt;= DISPATCH_LEVEL if the 
    <i>DestinationString</i> buffer is allocated from nonpaged memory. Usually, callers are running at IRQL =
    PASSIVE_LEVEL during driver initialization.




## -see-also




<a href="https://msdn.microsoft.com/library/gg156036.aspx">DriverEntry of NDIS Protocol
   Drivers</a>



<a href="https://msdn.microsoft.com/b146fa81-005b-4a6c-962d-4cb023ea790e">MiniportInitializeEx</a>



<a href="https://msdn.microsoft.com/1958722e-012e-4110-a82c-751744bcf9b5">ProtocolBindAdapterEx</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff561729">RtlAnsiStringToUnicodeString</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff561934">RtlInitUnicodeString</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff562969">RtlUnicodeStringToAnsiString</a>
 

 

