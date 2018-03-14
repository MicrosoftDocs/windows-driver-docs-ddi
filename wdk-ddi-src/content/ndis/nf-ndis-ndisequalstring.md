---
UID: NF:ndis.NdisEqualString
title: NdisEqualString macro
author: windows-driver-content
description: The NdisEqualString function compares two strings, in the OS-default character set, to determine whether they are equal.
old-location: netvista\ndisequalstring.htm
old-project: netvista
ms.assetid: cc5da07d-fcd2-40f9-8ba9-d7ddf35e7b7f
ms.author: windowsdriverdev
ms.date: 2/27/2018
ms.keywords: NdisEqualString, NdisEqualString macro [Network Drivers Starting with Windows Vista], ndis/NdisEqualString, ndis_string_ref_31191521-4693-40f9-a6e7-0c9b09bc6298.xml, netvista.ndisequalstring
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: macro
req.header: ndis.h
req.include-header: Ndis.h
req.target-type: Universal
req.target-min-winverclnt: Supported for existing drivers in  NDIS 6.0 and later, but new drivers should use RtlEqualUnicodeString instead.
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
-	NdisEqualString
product: Windows
targetos: Windows
req.typenames: NDIS_SHARED_MEMORY_USAGE, *PNDIS_SHARED_MEMORY_USAGE
---

# NdisEqualString macro


## -description


The 
  <b>NdisEqualString</b> function compares two strings, in the OS-default character set, to determine whether
  they are equal.


## -syntax


````
BOOLEAN NdisEqualString(
  [in] PNDIS_STRING String1,
  [in] PNDIS_STRING String2,
  [in] BOOLEAN      CaseInsensitive
);
````


## -parameters




### -param _String1 [in]

A pointer to an NDIS_STRING type that describes the first string.


### -param _String2 [in]

A pointer to an NDIS_STRING type that describes the second string.


### -param _CaseInsensitive [in]

A boolean value that is <b>TRUE</b> if case should be ignored when doing the comparison. Otherwise, it is
     <b>FALSE</b>.


## -remarks



Starting with Windows 2000, a string of type NDIS_STRING is a counted, null-terminated Unicode string.
    That is, NDIS defines the NDIS_STRING type as a 
    <a href="..\wudfwdm\ns-wudfwdm-_unicode_string.md">UNICODE_STRING</a> type.




## -see-also

<a href="..\wudfwdm\ns-wudfwdm-_unicode_string.md">UNICODE_STRING</a>



<a href="..\wdm\nf-wdm-rtlinitstring.md">RtlInitString</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff540605">ANSI_STRING</a>



<a href="..\wudfwdm\nf-wudfwdm-rtlinitunicodestring.md">RtlInitUnicodeString</a>



<a href="..\ndis\nc-ndis-protocol_bind_adapter_ex.md">ProtocolBindAdapterEx</a>



<a href="..\ndis\nc-ndis-miniport_initialize.md">MiniportInitializeEx</a>



 

 


