---
UID: NF:ndis.NdisUpcaseUnicodeString
title: NdisUpcaseUnicodeString macro
author: windows-driver-content
description: The NdisUpcaseUnicodeString function converts a copy of a given Unicode string to upper case and returns the converted string.Note  This function is deprecated for NDIS 6.0 and later.
old-location: netvista\ndisupcaseunicodestring.htm
old-project: netvista
ms.assetid: 5f735c98-26a6-4644-9fd4-b832ac9379c2
ms.author: windowsdriverdev
ms.date: 2/27/2018
ms.keywords: NdisUpcaseUnicodeString, NdisUpcaseUnicodeString macro [Network Drivers Starting with Windows Vista], ndis/NdisUpcaseUnicodeString, ndis_string_ref_79578398-7b4c-4741-a39b-5e5e30b2f4b3.xml, netvista.ndisupcaseunicodestring
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: macro
req.header: ndis.h
req.include-header: Ndis.h
req.target-type: Universal
req.target-min-winverclnt: Supported for existing drivers in  NDIS 6.0 and later, but new drivers should use RtlUpcaseUnicodeString instead.
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
-	NdisUpcaseUnicodeString
product: Windows
targetos: Windows
req.typenames: NDIS_SHARED_MEMORY_USAGE, *PNDIS_SHARED_MEMORY_USAGE
---

# NdisUpcaseUnicodeString macro


## -description


The 
  <b>NdisUpcaseUnicodeString</b> function converts a copy of a given Unicode string to upper case and returns
  the converted string.
<div class="alert"><b>Note</b>  This function is deprecated for NDIS 6.0 and later. </div><div> </div>

## -syntax


````
NTSTATUS NdisUpcaseUnicodeString(
  [out] PUNICODE_STRING DestinationString,
  [in]  PUNICODE_STRING SourceString
);
````


## -parameters




### -param _d

TBD


### -param _s

TBD






#### - DestinationString [out]

A pointer to a caller-allocated buffer in which to return the converted string.


#### - SourceString [in]

A pointer to the source Unicode string to be converted to upper case.


## -see-also

<a href="..\wudfwdm\nf-wudfwdm-rtlinitunicodestring.md">RtlInitUnicodeString</a>



<a href="..\wudfwdm\ns-wudfwdm-_unicode_string.md">UNICODE_STRING</a>



<a href="..\wdm\nf-wdm-rtlunicodestringtoansistring.md">RtlUnicodeStringToAnsiString</a>



 

 


