---
UID: NF:ndis.NdisInitializeString
title: NdisInitializeString function (ndis.h)
description: The NdisInitializeString function allocates storage for and initializes a counted string in the system-default character set.
old-location: netvista\ndisinitializestring.htm
tech.root: netvista
ms.assetid: c6945d7d-5152-4968-a628-7850b8083a82
ms.date: 05/02/2018
ms.keywords: NdisInitializeString, NdisInitializeString function [Network Drivers Starting with Windows Vista], ndis/NdisInitializeString, ndis_string_ref_886eff5e-5f5a-49f2-91d3-e87128cf0542.xml, netvista.ndisinitializestring
ms.topic: function
req.header: ndis.h
req.include-header: Ndis.h
req.target-type: Universal
req.target-min-winverclnt: Supported for existing drivers in  NDIS 6.0 and later, but new drivers should use RtlInitUnicodeString  or RTL_CONSTANT_STRING or   DECLARE_CONST_UNICODE_STRING (see ntdef.h) instead.
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
- NdisInitializeString
product:
- Windows
targetos: Windows
req.typenames: 
---

# NdisInitializeString function


## -description


The 
  <b>NdisInitializeString</b> function allocates storage for and initializes a counted string in the
  system-default character set.


## -parameters




### -param Destination

A pointer that is <b>NULL</b> when 
     <b>NdisInitializeString</b> is called; on return from this function, this parameter points to an
     NDIS_STRING type that describes an initialized counted string. For Windows 2000 and later, NDIS defines
     the NDIS_STRING type as a 
     <a href="https://docs.microsoft.com/windows/desktop/api/ntdef/ns-ntdef-_unicode_string">UNICODE_STRING</a> type.

### -param Source

A pointer to a null-terminated string with which to initialize the counted string. 
     <i>SourceString</i> must not be <b>NULL</b>.


## -returns



None




## -remarks



<b>NdisInitializeString</b> sets the 
    <b>Length</b> and 
    <b>MaximumLength</b> members of NDIS_STRING for the destination string and terminates the destination
    string with zero. For Windows 2000 and later drivers, 
    <b>NdisInitializeString</b> converts the supplied source string to Unicode characters.

<i>SourceString</i> must not be <b>NULL</b>.

The buffer allocated by 
    <b>NdisInitializeString</b> should be released with the 
    <a href="https://msdn.microsoft.com/library/windows/hardware/ff562604">NdisFreeString</a> function.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff540605">ANSI_STRING</a>



<a href="https://msdn.microsoft.com/library/gg156036.aspx">DriverEntry of NDIS Protocol
   Drivers</a>



<a href="https://msdn.microsoft.com/b146fa81-005b-4a6c-962d-4cb023ea790e">MiniportInitializeEx</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff561729">RtlAnsiStringToUnicodeString</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff561854">RtlEqualUnicodeString</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff561899">RtlFreeAnsiString</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff561903">RtlFreeUnicodeString</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff561929">RtlInitString</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff561934">RtlInitUnicodeString</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff562969">RtlUnicodeStringToAnsiString</a>



<a href="https://docs.microsoft.com/windows/desktop/api/ntdef/ns-ntdef-_unicode_string">UNICODE_STRING</a>
 

 

