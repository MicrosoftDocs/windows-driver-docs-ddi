---
UID: NF:ndis.NdisUnicodeStringToAnsiString
title: NdisUnicodeStringToAnsiString macro
author: windows-driver-content
description: The NdisUnicodeStringToAnsiString function converts a given counted Unicode string into a counted ANSI string. The translation conforms to the current system locale information.
old-location: netvista\ndisunicodestringtoansistring.htm
old-project: netvista
ms.assetid: 37ac55b8-093e-4bf4-9c66-05ab5fc7ebc9
ms.author: windowsdriverdev
ms.date: 2/27/2018
ms.keywords: NdisUnicodeStringToAnsiString, NdisUnicodeStringToAnsiString macro [Network Drivers Starting with Windows Vista], ndis/NdisUnicodeStringToAnsiString, ndis_string_ref_31235ece-f64c-4806-af32-e3ffffdb7904.xml, netvista.ndisunicodestringtoansistring
ms.prod: windows-hardware
ms.technology: windows-devices
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
product: Windows
targetos: Windows
req.typenames: NDIS_SHARED_MEMORY_USAGE, *PNDIS_SHARED_MEMORY_USAGE
---

# NdisUnicodeStringToAnsiString macro


## -description


The 
  <b>NdisUnicodeStringToAnsiString</b> function converts a given counted Unicode string into a counted ANSI
  string. The translation conforms to the current system locale information.


## -syntax


````
NDIS_STATUS NdisUnicodeStringToAnsiString(
  [in, out] PANSI_STRING    DestinationString,
  [in]      PUNICODE_STRING SourceString
);
````


## -parameters




### -param _as

TBD


### -param _us

TBD






#### - DestinationString [in, out]

A pointer to a caller-allocated buffer in which this function should return the converted ANSI
     string.


#### - SourceString [in]

A pointer to the Unicode string to be converted.


## -remarks



The caller must allocate storage for both the source and destination strings and release these buffers
    as soon as the strings are no longer needed. The buffer at 
    <i>SourceString</i> must be at least twice the size of that at 
    <i>DestinationString</i> .




## -see-also

<a href="https://msdn.microsoft.com/en-us/library/gg156036.aspx">DriverEntry of NDIS Protocol
   Drivers</a>



<a href="..\wudfwdm\ns-wudfwdm-_unicode_string.md">UNICODE_STRING</a>



<a href="..\wdm\nf-wdm-rtlansistringtounicodestring.md">RtlAnsiStringToUnicodeString</a>



<a href="..\wudfwdm\nf-wudfwdm-rtlinitunicodestring.md">RtlInitUnicodeString</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff540605">ANSI_STRING</a>



<a href="..\ndis\nc-ndis-protocol_bind_adapter_ex.md">ProtocolBindAdapterEx</a>



<a href="..\ndis\nc-ndis-miniport_initialize.md">MiniportInitializeEx</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20NdisUnicodeStringToAnsiString macro%20 RELEASE:%20(2/27/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

