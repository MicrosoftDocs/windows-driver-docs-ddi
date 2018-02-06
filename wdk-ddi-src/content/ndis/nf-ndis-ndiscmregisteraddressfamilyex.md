---
UID: NF:ndis.NdisCmRegisterAddressFamilyEx
title: NdisCmRegisterAddressFamilyEx function
author: windows-driver-content
description: The NdisCmRegisterAddressFamilyEx function registers an address family (AF) for communication between CoNDIS drivers.
old-location: netvista\ndiscmregisteraddressfamilyex.htm
old-project: netvista
ms.assetid: 8890bf31-f2c7-48b0-926d-8931893ede86
ms.author: windowsdriverdev
ms.date: 1/18/2018
ms.keywords: netvista.ndiscmregisteraddressfamilyex, condis_call_manager_ref_5d5bc425-d983-4d7c-8896-7cda4cab625d.xml, NdisCmRegisterAddressFamilyEx, NdisCmRegisterAddressFamilyEx function [Network Drivers Starting with Windows Vista], ndis/NdisCmRegisterAddressFamilyEx
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: ndis.h
req.include-header: Ndis.h
req.target-type: Desktop
req.target-min-winverclnt: Supported in NDIS 6.0 and later.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: Irql_CallManager_Function
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
-	NdisCmRegisterAddressFamilyEx
product: Windows
targetos: Windows
req.typenames: NDIS_SHARED_MEMORY_USAGE, *PNDIS_SHARED_MEMORY_USAGE
---

# NdisCmRegisterAddressFamilyEx function


## -description


The
  <b>NdisCmRegisterAddressFamilyEx</b> function registers an address family (AF) for communication between
  CoNDIS drivers.


## -syntax


````
NDIS_STATUS NdisCmRegisterAddressFamilyEx(
  _In_ NDIS_HANDLE        NdisBindingHandle,
  _In_ PCO_ADDRESS_FAMILY AddressFamily
);
````


## -parameters




### -param NdisBindingHandle [in]

A handle that NDIS provided at the 
     <i>NdisBindingHandle</i> parameter of the 
     <a href="..\ndis\nf-ndis-ndisopenadapterex.md">NdisOpenAdapterEx</a> function. This handle
     identifies the binding to associate with the AF.


### -param AddressFamily [in]

A pointer to a 
     <a href="https://msdn.microsoft.com/library/windows/hardware/ff545368">CO_ADDRESS_FAMILY</a> structure that identifies
     the call manager and the AF that it supports for the binding that 
     <i>NdisBindingHandle</i> specifies.
     

The pointer for 
     <i>AddressFamily</i> becomes an input parameter to the 
     <a href="..\ndis\nc-ndis-protocol_co_af_register_notify.md">
     ProtocolCoAfRegisterNotify</a> functions of all of the clients that are bound to the same CoNDIS
     miniport adapter.


## -returns


<b>NdisCmRegisterAddressFamilyEx</b> can return any of the following:
<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>NDIS_STATUS_SUCCESS</b></dt>
</dl>
</td>
<td width="60%">
The protocol driver registered the AF that the 
       <i>AddressFamily</i> points to, so NDIS will call the 
       <a href="..\ndis\nc-ndis-protocol_co_af_register_notify.md">
       ProtocolCoAfRegisterNotify</a> functions of all of the clients that bind themselves to the same
       miniport adapter.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>NDIS_STATUS_RESOURCES</b></dt>
</dl>
</td>
<td width="60%">
The requested operation failed because NDIS could not allocate sufficient memory or initialize
       the state that it uses to track the call manager or the specified AF.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>NDIS_STATUS_FAILURE</b></dt>
</dl>
</td>
<td width="60%">
NDIS failed the call to 
       <b>NdisCmRegisterAddressFamilyEx</b>, possibly for one of the following reasons:
       

<ul>
<li>
The caller was not registered as a connection-oriented protocol driver.

</li>
<li>
The miniport driver that the caller is bound to was not registered as a connection-oriented
         miniport driver.

</li>
<li>
Another call manager has already registered the specified AF.

</li>
<li>
The caller's binding is being closed.

</li>
</ul>
</td>
</tr>
</table> 



## -remarks


NDIS stand-alone call managers, which register as NDIS protocol drivers by calling the 
    <a href="..\ndis\nf-ndis-ndisregisterprotocoldriver.md">
    NdisRegisterProtocolDriver</a> function, should call the 
    <b>NdisCmRegisterAddressFamilyEx</b> function to register an AF. Miniport call managers (MCMs) must
    instead call the 
    <a href="..\ndis\nf-ndis-ndismcmregisteraddressfamilyex.md">
    NdisMCmRegisterAddressFamilyEx</a> function.

To register an AF for a binding, the stand-alone call manager should call 
    <b>NdisCmRegisterAddressFamilyEx</b> from the 
    <a href="..\ndis\nc-ndis-protocol_bind_adapter_ex.md">
    ProtocolBindAdapterEx</a> function.

A stand-alone call manager's 
    <i>ProtocolBindAdapterEx</i> function first establishes the binding to the underlying miniport driver by
    calling the 
    <a href="..\ndis\nf-ndis-ndisopenadapterex.md">NdisOpenAdapterEx</a> function. Each time
    NDIS calls 
    <i>ProtocolBindAdapterEx</i> with another handle at the 
    <i>BindContext</i> parameter, 
    <i>ProtocolBindAdapterEx</i> establishes a binding and registers an AF that it supports. In other words, a
    stand-alone call manager eventually registers an AF for each binding on which it provides call-management
    services to connection-oriented clients.

The call manager can support more than one AF and can support more than one AF for a single binding.
    However, only one call manager can support a given AF for clients that are bound to a given miniport
    adapter.

When a call manager's 
    <a href="..\ndis\nc-ndis-protocol_bind_adapter_ex.md">ProtocolBindAdapterEx</a> function
    returns control after a successful binding operation, NDIS calls the 
    <a href="..\ndis\nc-ndis-protocol_co_af_register_notify.md">
    ProtocolCoAfRegisterNotify</a> functions of all of the clients that are bound to the same miniport
    adapter.



## -see-also

<a href="..\ndis\nf-ndis-ndisregisterprotocoldriver.md">NdisRegisterProtocolDriver</a>

<a href="..\ndis\nf-ndis-ndismcmregisteraddressfamilyex.md">
   NdisMCmRegisterAddressFamilyEx</a>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff545368">CO_ADDRESS_FAMILY</a>

<a href="..\ndis\nc-ndis-protocol_co_af_register_notify.md">ProtocolCoAfRegisterNotify</a>

<a href="..\ndis\nc-ndis-protocol_bind_adapter_ex.md">ProtocolBindAdapterEx</a>

<a href="..\ndis\nf-ndis-ndisopenadapterex.md">NdisOpenAdapterEx</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20NdisCmRegisterAddressFamilyEx function%20 RELEASE:%20(1/18/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

