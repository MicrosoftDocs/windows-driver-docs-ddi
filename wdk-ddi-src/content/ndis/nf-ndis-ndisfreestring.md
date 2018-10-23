---
UID: NF:ndis.NdisFreeString
title: NdisFreeString macro
author: windows-driver-content
description: The NdisFreeString function releases storage that was allocated by NdisInitializeString for a buffered string.
old-location: netvista\ndisfreestring.htm
tech.root: netvista
ms.assetid: 62b4318a-b883-44fc-a2a5-86a7a884f039
ms.date: 05/02/2018
ms.keywords: NdisFreeString, NdisFreeString macro [Network Drivers Starting with Windows Vista], ndis/NdisFreeString, ndis_string_ref_fbe6ac9f-c6a6-457e-a427-71e9739f3809.xml, netvista.ndisfreestring
ms.topic: macro
req.header: ndis.h
req.include-header: Ndis.h
req.target-type: Desktop
req.target-min-winverclnt: Supported for existing drivers in  NDIS 6.0 and later, but new drivers should use RtlFreeAnsiString or RtlFreeUnicodeString  instead.
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
req.lib: 
req.dll: 
req.irql: PASSIVE_LEVEL
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	ndis.h
api_name:
-	NdisFreeString
product:
- Windows
targetos: Windows
req.typenames: 
---

# NdisFreeString macro


## -description


The 
  <b>NdisFreeString</b> function releases storage that was allocated by 
  <a href="https://msdn.microsoft.com/library/windows/hardware/ff562741">NdisInitializeString</a> for a buffered
  string.


## -parameters




### -param String [in]

An NDIS_STRING type value that describes the string to free. For Windows 2000 and later, NDIS
     defines the NDIS_STRING type as a 
     <a href="https://msdn.microsoft.com/library/windows/hardware/ff564879">UNICODE_STRING</a> type.


## -remarks



An NDIS driver typically calls the 
    <a href="https://msdn.microsoft.com/library/windows/hardware/ff562741">NdisInitializeString</a> function during
    initialization--for example, to set up names passed to the 
    <b>Ndis<i>Xxx</i>Configuration</b> functions. For each call that the driver makes to 
    <b>NdisInitializeString</b>, the driver must make a corresponding call to 
    <b>NdisFreeString</b>. When releasing string buffers that were allocated during initialization, a driver
    must call 
    <b>NdisFreeString</b> before the driver's initialization function returns control.

<b>NdisFreeString</b> must be used only for freeing buffers that were allocated with 
    <b>NdisInitializeString</b>.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff540605">ANSI_STRING</a>



<a href="https://msdn.microsoft.com/library/gg156036.aspx">DriverEntry of NDIS Protocol
   Drivers</a>



<a href="https://msdn.microsoft.com/b146fa81-005b-4a6c-962d-4cb023ea790e">MiniportInitializeEx</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff563715">NdisOpenAdapterEx</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff564520">NdisRegisterProtocolDriver</a>



<a href="https://msdn.microsoft.com/1958722e-012e-4110-a82c-751744bcf9b5">ProtocolBindAdapterEx</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff561929">RtlInitString</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff561934">RtlInitUnicodeString</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff562969">RtlUnicodeStringToAnsiString</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff564879">UNICODE_STRING</a>
 

 

