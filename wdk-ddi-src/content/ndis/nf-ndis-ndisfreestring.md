---
UID: NF:ndis.NdisFreeString
title: NdisFreeString macro
author: windows-driver-content
description: The NdisFreeString function releases storage that was allocated by NdisInitializeString for a buffered string.
old-location: netvista\ndisfreestring.htm
old-project: netvista
ms.assetid: 62b4318a-b883-44fc-a2a5-86a7a884f039
ms.author: windowsdriverdev
ms.date: 2/27/2018
ms.keywords: NdisFreeString, NdisFreeString macro [Network Drivers Starting with Windows Vista], ndis/NdisFreeString, ndis_string_ref_fbe6ac9f-c6a6-457e-a427-71e9739f3809.xml, netvista.ndisfreestring
ms.prod: windows-hardware
ms.technology: windows-devices
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
product: Windows
targetos: Windows
req.typenames: NDIS_SHARED_MEMORY_USAGE, *PNDIS_SHARED_MEMORY_USAGE
---

# NdisFreeString macro


## -description


The 
  <b>NdisFreeString</b> function releases storage that was allocated by 
  <a href="..\ndis\nf-ndis-ndisinitializestring.md">NdisInitializeString</a> for a buffered
  string.


## -syntax


````
VOID NdisFreeString(
  [in] NDIS_STRING String
);
````


## -parameters




### -param String [in]

An NDIS_STRING type value that describes the string to free. For Windows 2000 and later, NDIS
     defines the NDIS_STRING type as a 
     <a href="..\wudfwdm\ns-wudfwdm-_unicode_string.md">UNICODE_STRING</a> type.


## -remarks



An NDIS driver typically calls the 
    <a href="..\ndis\nf-ndis-ndisinitializestring.md">NdisInitializeString</a> function during
    initialization--for example, to set up names passed to the 
    <b>Ndis<i>Xxx</i>Configuration</b> functions. For each call that the driver makes to 
    <b>NdisInitializeString</b>, the driver must make a corresponding call to 
    <b>NdisFreeString</b>. When releasing string buffers that were allocated during initialization, a driver
    must call 
    <b>NdisFreeString</b> before the driver's initialization function returns control.

<b>NdisFreeString</b> must be used only for freeing buffers that were allocated with 
    <b>NdisInitializeString</b>.




## -see-also

<a href="..\wudfwdm\ns-wudfwdm-_unicode_string.md">UNICODE_STRING</a>



<a href="..\wdm\nf-wdm-rtlunicodestringtoansistring.md">RtlUnicodeStringToAnsiString</a>



<a href="..\wdm\nf-wdm-rtlinitstring.md">RtlInitString</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff540605">ANSI_STRING</a>



<a href="..\ndis\nf-ndis-ndisopenadapterex.md">NdisOpenAdapterEx</a>



<a href="https://msdn.microsoft.com/en-us/library/gg156036.aspx">DriverEntry of NDIS Protocol
   Drivers</a>



<a href="..\wudfwdm\nf-wudfwdm-rtlinitunicodestring.md">RtlInitUnicodeString</a>



<a href="..\ndis\nc-ndis-protocol_bind_adapter_ex.md">ProtocolBindAdapterEx</a>



<a href="..\ndis\nc-ndis-miniport_initialize.md">MiniportInitializeEx</a>



<a href="..\ndis\nf-ndis-ndisregisterprotocoldriver.md">NdisRegisterProtocolDriver</a>



 

 


