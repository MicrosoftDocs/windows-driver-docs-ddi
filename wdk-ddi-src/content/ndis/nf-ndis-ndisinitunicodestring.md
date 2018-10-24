---
UID: NF:ndis.NdisInitUnicodeString
title: NdisInitUnicodeString macro
author: windows-driver-content
description: The NdisInitUnicodeString function initializes a counted Unicode string.
old-location: netvista\ndisinitunicodestring.htm
tech.root: netvista
ms.assetid: 073feb91-48ae-4ad5-9061-117e6541021c
ms.date: 05/02/2018
ms.keywords: NdisInitUnicodeString, NdisInitUnicodeString macro [Network Drivers Starting with Windows Vista], ndis/NdisInitUnicodeString, ndis_string_ref_a25a98b2-f88b-4a56-9bb7-77a4e6dc10a6.xml, netvista.ndisinitunicodestring
ms.topic: macro
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
-	APIRef
-	kbSyntax
api_type:
-	LibDef
api_location:
-	ndis.lib
-	ndis.dll
api_name:
-	NdisInitUnicodeString
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
     <a href="https://msdn.microsoft.com/library/windows/hardware/ff564879">UNICODE_STRING</a> type.


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
    <b>NdisInitUnicodeString</b> must be running at IRQL &lt;= DISPATCH_LEVEL if the 
    <i>DestinationString</i> buffer is allocated from nonpaged memory. Usually, callers are running at IRQL =
    PASSIVE_LEVEL during driver initialization.




## -see-also




<a href="https://msdn.microsoft.com/library/gg156036.aspx">DriverEntry of NDIS Protocol
   Drivers</a>



<a href="https://msdn.microsoft.com/b146fa81-005b-4a6c-962d-4cb023ea790e">MiniportInitializeEx</a>



<a href="https://msdn.microsoft.com/8efdcf9f-df8c-4b3b-8b21-11a10a885322">
   NdisAnsiStringToUnicodeString</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff562730">NdisInitAnsiString</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff562741">NdisInitializeString</a>



<a href="https://msdn.microsoft.com/37ac55b8-093e-4bf4-9c66-05ab5fc7ebc9">
   NdisUnicodeStringToAnsiString</a>



<a href="https://msdn.microsoft.com/1958722e-012e-4110-a82c-751744bcf9b5">ProtocolBindAdapterEx</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff564879">UNICODE_STRING</a>
 

 

