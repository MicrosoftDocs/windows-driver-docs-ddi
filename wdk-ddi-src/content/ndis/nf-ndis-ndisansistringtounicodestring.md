---
UID: NF:ndis.NdisAnsiStringToUnicodeString
title: NdisAnsiStringToUnicodeString macro
author: windows-driver-content
description: The NdisAnsiStringToUnicodeString function converts a given counted ANSI string into a counted Unicode string. The translation conforms to the current system locale information.
old-location: netvista\ndisansistringtounicodestring.htm
old-project: netvista
ms.assetid: 8efdcf9f-df8c-4b3b-8b21-11a10a885322
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: ndis/NdisAnsiStringToUnicodeString, netvista.ndisansistringtounicodestring, ndis_string_ref_e56d613a-b145-4f9e-bb96-3e4d8ad33538.xml, NdisAnsiStringToUnicodeString macro [Network Drivers Starting with Windows Vista], NdisAnsiStringToUnicodeString
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	LibDef
apilocation:
-	ndis.lib
-	ndis.dll
apiname:
-	NdisAnsiStringToUnicodeString
product: Windows
targetos: Windows
req.typenames: "*PNDIS_SHARED_MEMORY_USAGE, NDIS_SHARED_MEMORY_USAGE"
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

<a href="..\wdm\nf-wdm-rtlunicodestringtoansistring.md">RtlUnicodeStringToAnsiString</a>



<a href="..\wudfwdm\ns-wudfwdm-_unicode_string.md">UNICODE_STRING</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff540605">ANSI_STRING</a>



<a href="..\wudfwdm\ns-wudfwdm-_unicode_string.md">UNICODE_STRING</a>



<a href="https://msdn.microsoft.com/en-us/library/gg156036.aspx">DriverEntry of NDIS Protocol
   Drivers</a>



<a href="..\wudfwdm\nf-wudfwdm-rtlinitunicodestring.md">RtlInitUnicodeString</a>



<a href="..\ndis\nc-ndis-protocol_bind_adapter_ex.md">ProtocolBindAdapterEx</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20NdisAnsiStringToUnicodeString macro%20 RELEASE:%20(2/16/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

