---
UID: NF:ndis.NdisInitUnicodeString
title: NdisInitUnicodeString macro
author: windows-driver-content
description: The NdisInitUnicodeString function initializes a counted Unicode string.
old-location: netvista\ndisinitunicodestring.htm
old-project: netvista
ms.assetid: 073feb91-48ae-4ad5-9061-117e6541021c
ms.author: windowsdriverdev
ms.date: 1/18/2018
ms.keywords: ndis/NdisInitUnicodeString, netvista.ndisinitunicodestring, NdisInitUnicodeString, NdisInitUnicodeString macro [Network Drivers Starting with Windows Vista], ndis_string_ref_a25a98b2-f88b-4a56-9bb7-77a4e6dc10a6.xml
ms.prod: windows-hardware
ms.technology: windows-devices
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	LibDef
apilocation:
-	ndis.lib
-	ndis.dll
apiname:
-	NdisInitUnicodeString
product: Windows
targetos: Windows
req.typenames: "*PNDIS_SHARED_MEMORY_USAGE, NDIS_SHARED_MEMORY_USAGE"
---

# NdisInitUnicodeString macro


## -description


The 
  <b>NdisInitUnicodeString</b> function initializes a counted Unicode string.


## -syntax


````
VOID NdisInitUnicodeString(
  [in, out] PNDIS_STRING DestinationString,
  [in]      PCWSTR       SourceString
);
````


## -parameters




### -param _us

TBD


### -param s

TBD






#### - DestinationString [in, out]

A pointer to a caller-allocated NDIS_STRING type in which 
     <b>NdisInitUnicodeString</b> should store the counted Unicode string. For Windows 2000 and later, NDIS
     defines the NDIS_STRING type as a 
     <a href="..\wudfwdm\ns-wudfwdm-_unicode_string.md">UNICODE_STRING</a> type.


#### - SourceString [in]

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

<a href="..\ndis\nc-ndis-protocol_bind_adapter_ex.md">ProtocolBindAdapterEx</a>



<a href="..\ndis\nf-ndis-ndisansistringtounicodestring.md">
   NdisAnsiStringToUnicodeString</a>



<a href="..\ndis\nc-ndis-miniport_initialize.md">MiniportInitializeEx</a>



<a href="..\wudfwdm\ns-wudfwdm-_unicode_string.md">UNICODE_STRING</a>



<a href="https://msdn.microsoft.com/en-us/library/gg156036.aspx">DriverEntry of NDIS Protocol
   Drivers</a>



<a href="..\ndis\nf-ndis-ndisinitializestring.md">NdisInitializeString</a>



<a href="..\ndis\nf-ndis-ndisunicodestringtoansistring.md">
   NdisUnicodeStringToAnsiString</a>



<a href="..\ndis\nf-ndis-ndisinitansistring.md">NdisInitAnsiString</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20NdisInitUnicodeString macro%20 RELEASE:%20(1/18/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

