---
UID: NF:ndis.NdisEqualString
title: NdisEqualString macro (ndis.h)
description: The NdisEqualString function compares two strings, in the OS-default character set, to determine whether they are equal.
old-location: netvista\ndisequalstring.htm
tech.root: netvista
ms.assetid: cc5da07d-fcd2-40f9-8ba9-d7ddf35e7b7f
ms.date: 05/02/2018
keywords: ["NdisEqualString macro"]
ms.keywords: NdisEqualString, NdisEqualString macro [Network Drivers Starting with Windows Vista], ndis/NdisEqualString, ndis_string_ref_31191521-4693-40f9-a6e7-0c9b09bc6298.xml, netvista.ndisequalstring
f1_keywords:
 - "ndis/NdisEqualString"
 - "NdisEqualString"
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
- APIRef
- kbSyntax
api_type:
- LibDef
api_location:
- ndis.lib
- ndis.dll
api_name:
- NdisEqualString
product:
- Windows
targetos: Windows
req.typenames: 
---

# NdisEqualString macro


## -description


The 
  <b>NdisEqualString</b> function compares two strings, in the OS-default character set, to determine whether
  they are equal.


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
    <a href="https://docs.microsoft.com/windows/desktop/api/ntdef/ns-ntdef-_unicode_string">UNICODE_STRING</a> type.




## -see-also




<a href="https://docs.microsoft.com/windows/win32/api/ntdef/ns-ntdef-string">ANSI_STRING</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nc-ndis-miniport_initialize">MiniportInitializeEx</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nc-ndis-protocol_bind_adapter_ex">ProtocolBindAdapterEx</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-rtlinitstring">RtlInitString</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-rtlinitunicodestring">RtlInitUnicodeString</a>



<a href="https://docs.microsoft.com/windows/desktop/api/ntdef/ns-ntdef-_unicode_string">UNICODE_STRING</a>
 

 

