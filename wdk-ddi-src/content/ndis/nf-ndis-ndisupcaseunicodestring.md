---
UID: NF:ndis.NdisUpcaseUnicodeString
title: NdisUpcaseUnicodeString macro
author: windows-driver-content
description: The NdisUpcaseUnicodeString function converts a copy of a given Unicode string to upper case and returns the converted string.Note  This function is deprecated for NDIS 6.0 and later.
old-location: netvista\ndisupcaseunicodestring.htm
tech.root: netvista
ms.assetid: 5f735c98-26a6-4644-9fd4-b832ac9379c2
ms.date: 5/2/2018
ms.keywords: NdisUpcaseUnicodeString, NdisUpcaseUnicodeString macro [Network Drivers Starting with Windows Vista], ndis/NdisUpcaseUnicodeString, ndis_string_ref_79578398-7b4c-4741-a39b-5e5e30b2f4b3.xml, netvista.ndisupcaseunicodestring
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
product:
- Windows
targetos: Windows
req.typenames: 
---

# NdisUpcaseUnicodeString macro


## -description


The 
  <b>NdisUpcaseUnicodeString</b> function converts a copy of a given Unicode string to upper case and returns
  the converted string.
<div class="alert"><b>Note</b>  This function is deprecated for NDIS 6.0 and later. </div><div> </div>

## -parameters




### -param _d

A pointer to a caller-allocated buffer in which to return the converted string.


### -param _s

A pointer to the source Unicode string to be converted to upper case.


## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff561934">RtlInitUnicodeString</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff562969">RtlUnicodeStringToAnsiString</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff564879">UNICODE_STRING</a>
 

 

