---
UID: NF:ndis.NdisFreeString
title: NdisFreeString macro
author: windows-driver-content
description: The NdisFreeString function releases storage that was allocated by NdisInitializeString for a buffered string.
old-location: netvista\ndisfreestring.htm
old-project: netvista
ms.assetid: 62b4318a-b883-44fc-a2a5-86a7a884f039
ms.author: windowsdriverdev
ms.date: 2/16/2018
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
req.lib: ndis.h
req.dll: 
req.irql: PASSIVE_LEVEL
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	ndis.h
apiname:
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

<a href="..\ndis\nc-ndis-protocol_bind_adapter_ex.md">ProtocolBindAdapterEx</a>



<a href="..\wdm\nf-wdm-rtlinitstring.md">RtlInitString</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff540605">ANSI_STRING</a>



<a href="https://msdn.microsoft.com/en-us/library/gg156036.aspx">DriverEntry of NDIS Protocol
   Drivers</a>



<a href="..\wdm\nf-wdm-rtlunicodestringtoansistring.md">RtlUnicodeStringToAnsiString</a>



<a href="..\ndis\nf-ndis-ndisregisterprotocoldriver.md">NdisRegisterProtocolDriver</a>



<a href="..\ndis\nc-ndis-miniport_initialize.md">MiniportInitializeEx</a>



<a href="..\wudfwdm\nf-wudfwdm-rtlinitunicodestring.md">RtlInitUnicodeString</a>



<a href="..\ndis\nf-ndis-ndisopenadapterex.md">NdisOpenAdapterEx</a>



<a href="..\wudfwdm\ns-wudfwdm-_unicode_string.md">UNICODE_STRING</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20NdisFreeString macro%20 RELEASE:%20(2/16/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

