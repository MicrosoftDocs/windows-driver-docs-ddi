---
UID: NF:ndis.NdisUpcaseUnicodeString
title: NdisUpcaseUnicodeString macro
author: windows-driver-content
description: The NdisUpcaseUnicodeString function converts a copy of a given Unicode string to upper case and returns the converted string.Note  This function is deprecated for NDIS 6.0 and later.
old-location: netvista\ndisupcaseunicodestring.htm
old-project: netvista
ms.assetid: 5f735c98-26a6-4644-9fd4-b832ac9379c2
ms.author: windowsdriverdev
ms.date: 1/11/2018
ms.keywords: NdisUpcaseUnicodeString
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
req.alt-api: NdisUpcaseUnicodeString
req.alt-loc: ndis.lib,ndis.dll
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
req.typenames: NDIS_SHARED_MEMORY_USAGE, *PNDIS_SHARED_MEMORY_USAGE
---

# NdisUpcaseUnicodeString macro



## -description
The 
  <b>NdisUpcaseUnicodeString</b> function converts a copy of a given Unicode string to upper case and returns
  the converted string.



## -syntax

````
NTSTATUS NdisUpcaseUnicodeString(
  [out] PUNICODE_STRING DestinationString,
  [in]  PUNICODE_STRING SourceString
);
````


## -parameters

### -param DestinationString [out]

A pointer to a caller-allocated buffer in which to return the converted string.


### -param SourceString [in]

A pointer to the source Unicode string to be converted to upper case.


## -remarks


## -see-also
<dl>
<dt>
<a href="..\wdm\nf-wdm-rtlinitunicodestring.md">RtlInitUnicodeString</a>
</dt>
<dt>
<a href="..\wdm\nf-wdm-rtlunicodestringtoansistring.md">RtlUnicodeStringToAnsiString</a>
</dt>
<dt>
<a href="..\wudfwdm\ns-wudfwdm-_unicode_string.md">UNICODE_STRING</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20NdisUpcaseUnicodeString macro%20 RELEASE:%20(1/11/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

