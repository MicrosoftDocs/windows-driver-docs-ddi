---
UID: NF:ndis.NdisInitAnsiString
title: NdisInitAnsiString macro
author: windows-driver-content
description: The NdisInitAnsiString function initializes a counted ANSI string.
old-location: netvista\ndisinitansistring.htm
old-project: netvista
ms.assetid: e8209781-36b1-4008-94bb-82bdb16f20bf
ms.author: windowsdriverdev
ms.date: 2/27/2018
ms.keywords: NdisInitAnsiString, NdisInitAnsiString macro [Network Drivers Starting with Windows Vista], ndis/NdisInitAnsiString, ndis_string_ref_2d47b8b6-3b3e-48ca-a2be-ee1bca117ef6.xml, netvista.ndisinitansistring
ms.prod: windows-hardware
ms.technology: windows-devices
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
product: Windows
targetos: Windows
req.typenames: NDIS_SHARED_MEMORY_USAGE, *PNDIS_SHARED_MEMORY_USAGE
---

# NdisInitAnsiString macro


## -description


The 
  <b>NdisInitAnsiString</b> function initializes a counted ANSI string.


## -syntax


````
VOID NdisInitAnsiString(
  [in, out] PANSI_STRING DestinationString,
  [in]      PCSTR        SourceString
);
````


## -parameters




### -param _as

TBD


### -param s

TBD






#### - DestinationString [in, out]

A pointer to a caller-allocated buffer in which this function should store the counted ANSI
     string.


#### - SourceString [in]

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

<a href="..\wdm\nf-wdm-rtlunicodestringtoansistring.md">RtlUnicodeStringToAnsiString</a>



<a href="..\wdm\nf-wdm-rtlansistringtounicodestring.md">RtlAnsiStringToUnicodeString</a>



<a href="https://msdn.microsoft.com/en-us/library/gg156036.aspx">DriverEntry of NDIS Protocol
   Drivers</a>



<a href="..\wudfwdm\nf-wudfwdm-rtlinitunicodestring.md">RtlInitUnicodeString</a>



<a href="..\ndis\nc-ndis-protocol_bind_adapter_ex.md">ProtocolBindAdapterEx</a>



<a href="..\ndis\nc-ndis-miniport_initialize.md">MiniportInitializeEx</a>



 

 


