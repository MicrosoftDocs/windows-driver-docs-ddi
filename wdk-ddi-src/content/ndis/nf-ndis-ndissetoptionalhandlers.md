---
UID: NF:ndis.NdisSetOptionalHandlers
title: NdisSetOptionalHandlers function
author: windows-driver-content
description: NDIS drivers can call the NdisSetOptionalHandlers function to set or change the entry points of driver functions.
old-location: netvista\ndissetoptionalhandlers.htm
old-project: netvista
ms.assetid: 97649f4f-942a-47fc-a541-6f160c8b4eb4
ms.author: windowsdriverdev
ms.date: 1/18/2018
ms.keywords: netvista.ndissetoptionalhandlers, NdisSetOptionalHandlers function [Network Drivers Starting with Windows Vista], ndis/NdisSetOptionalHandlers, ndis_configuration_ref_343cba4f-9651-4f42-b0a9-0a85475cb6bf.xml, NdisSetOptionalHandlers
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: ndis.h
req.include-header: Ndis.h
req.target-type: Universal
req.target-min-winverclnt: Supported in NDIS 6.0 and later.
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
-	NdisSetOptionalHandlers
product: Windows
targetos: Windows
req.typenames: NDIS_SHARED_MEMORY_USAGE, *PNDIS_SHARED_MEMORY_USAGE
---

# NdisSetOptionalHandlers function


## -description


NDIS drivers can call the 
  <b>NdisSetOptionalHandlers</b> function to set or change the entry points of driver functions.


## -syntax


````
NDIS_STATUS NdisSetOptionalHandlers(
   NDIS_HANDLE                    NdisHandle,
   PNDIS_DRIVER_OPTIONAL_HANDLERS OptionalHandlers
);
````


## -parameters




### -param NdisHandle

An NDIS handle that identifies a driver or driver instance.
     

For a protocol driver, this is the 
     <i>NdisDriverHandle</i> value passed to the 
     <a href="..\ndis\nc-ndis-set_options.md">ProtocolSetOptions</a> function or the 
     <i>NdisBindingHandle</i> value obtained by calling the 
     <a href="..\ndis\nf-ndis-ndisopenadapterex.md">NdisOpenAdapterEx</a> function.

For a miniport driver, this is the 
     <i>NdisDriverHandle</i> value passed to the 
     <a href="https://msdn.microsoft.com/en-us/library/windows/hardware/ff570269">MiniportSetOptions</a> function

For a filter driver, this is the 
     <i>NdisDriverHandle</i> value passed to the 
     <a href="https://msdn.microsoft.com/en-us/library/windows/hardware/ff570269">FilterSetOptions</a> function or the 
     <i>NdisFilterHandle</i> value passed to the 
     <a href="..\ndis\nc-ndis-filter_attach.md">FilterAttach</a> function.


### -param OptionalHandlers

A pointer to one of the following NDIS structures:
     


<a href="..\ndischimney\ns-ndischimney-_ndis_client_chimney_offload_generic_characteristics.md">
        NDIS_CLIENT_CHIMNEY_OFFLOAD_GENERIC_CHARACTERISTICS</a>



<a href="..\ndischimney\ns-ndischimney-_ndis_client_chimney_offload_tcp_characteristics.md">
        NDIS_CLIENT_CHIMNEY_OFFLOAD_TCP_CHARACTERISTICS</a>



<a href="..\ndis\ns-ndis-_ndis_co_call_manager_optional_handlers.md">
        NDIS_CO_CALL_MANAGER_OPTIONAL_HANDLERS</a>



<a href="..\ndis\ns-ndis-_ndis_co_client_optional_handlers.md">
        NDIS_CO_CLIENT_OPTIONAL_HANDLERS</a>



<a href="..\ndis\ns-ndis-_ndis_filter_partial_characteristics.md">
        NDIS_FILTER_PARTIAL_CHARACTERISTICS</a>



<a href="..\ndis\ns-ndis-_ndis_miniport_co_characteristics.md">
        NDIS_MINIPORT_CO_CHARACTERISTICS</a>



<a href="..\ndis\ns-ndis-_ndis_miniport_pnp_characteristics.md">
        NDIS_MINIPORT_PNP_CHARACTERISTICS</a>



<a href="..\ndis\ns-ndis-_ndis_miniport_ss_characteristics.md">NDIS_MINIPORT_SS_CHARACTERISTICS</a>



<a href="..\ndisndk\ns-ndisndk-_ndis_ndk_provider_characteristics.md">NDIS_NDK_PROVIDER_CHARACTERISTICS</a>



<a href="..\ndis\ns-ndis-_ndis_protocol_co_characteristics.md">
        NDIS_PROTOCOL_CO_CHARACTERISTICS</a>



<a href="..\ndischimney\ns-ndischimney-_ndis_provider_chimney_offload_generic_characteristics.md">
        NDIS_PROVIDER_CHIMNEY_OFFLOAD_GENERIC_CHARACTERISTICS</a>



<a href="..\ndischimney\ns-ndischimney-_ndis_provider_chimney_offload_tcp_characteristics.md">
        NDIS_PROVIDER_CHIMNEY_OFFLOAD_TCP_CHARACTERISTICS</a>



<a href="..\ndis\ns-ndis-_ndis_shared_memory_provider_characteristics.md">
        NDIS_SHARED_MEMORY_PROVIDER_CHARACTERISTICS</a>



## -returns


<b>NdisSetOptionalHandlers</b> returns one of the following status values:
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

<a href="..\ndis\nf-ndis-ndissetoptionalhandlers.md">NdisSetOptionalHandlers</a> returns <b>NDIS_STATUS_SUCCESS</b> if it set the driver entry points.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>NDIS_STATUS_RESOURCES</b></dt>
</dl>
</td>
<td width="60%">

<a href="..\ndis\nf-ndis-ndissetoptionalhandlers.md">NdisSetOptionalHandlers</a> failed due to insufficient resources.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>NDIS_STATUS_NOT_SUPPORTED</b></dt>
</dl>
</td>
<td width="60%">

<a href="..\ndis\nf-ndis-ndissetoptionalhandlers.md">NdisSetOptionalHandlers</a> failed because the miniport driver did not specify that it supports NDIS
       6.0 or later. A miniport driver specifies its NDIS version when it calls the 
       <a href="..\ndis\nf-ndis-ndismregisterminiportdriver.md">
       NdisMRegisterMiniportDriver</a> function.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>NDIS_STATUS_FAILURE</b></dt>
</dl>
</td>
<td width="60%">

<a href="..\ndis\nf-ndis-ndissetoptionalhandlers.md">NdisSetOptionalHandlers</a> returns <b>NDIS_STATUS_FAILURE</b> if none of the preceding values
       applies.

</td>
</tr>
</table> 



## -remarks


An NDIS driver can call 
    <b>NdisSetOptionalHandlers</b> to overwrite its default entry points. The structure types passed at 
    <i>OptionalHandlers</i> vary according to the type of driver.

Protocol drivers can call 
    <b>NdisSetOptionalHandlers</b> in the context of the 
    <a href="..\ndis\nc-ndis-set_options.md">ProtocolSetOptions</a> function. As an option, protocol drivers can call 
    <b>NdisSetOptionalHandlers</b> from the 
    <a href="..\ndis\nc-ndis-protocol_bind_adapter_ex.md">ProtocolBindAdapterEx</a> function or
    the 
    <a href="..\ndis\nc-ndis-protocol_open_adapter_complete_ex.md">
    ProtocolOpenAdapterCompleteEx</a> function after the protocol driver has a valid handle from the 
    <a href="..\ndis\nf-ndis-ndisopenadapterex.md">NdisOpenAdapterEx</a> function.

In this case, the valid structures are:


<a href="..\ndis\ns-ndis-_ndis_protocol_co_characteristics.md">
       NDIS_PROTOCOL_CO_CHARACTERISTICS</a>



<a href="..\ndis\ns-ndis-_ndis_co_client_optional_handlers.md">
       NDIS_CO_CLIENT_OPTIONAL_HANDLERS</a>



<a href="..\ndis\ns-ndis-_ndis_co_call_manager_optional_handlers.md">
       NDIS_CO_CALL_MANAGER_OPTIONAL_HANDLERS</a>



<a href="..\ndis\ns-ndis-_ndis_shared_memory_provider_characteristics.md">
       NDIS_SHARED_MEMORY_PROVIDER_CHARACTERISTICS</a>



<a href="..\ndischimney\ns-ndischimney-_ndis_client_chimney_offload_generic_characteristics.md">
       NDIS_CLIENT_CHIMNEY_OFFLOAD_GENERIC_CHARACTERISTICS</a>



<a href="..\ndischimney\ns-ndischimney-_ndis_client_chimney_offload_tcp_characteristics.md">
       NDIS_CLIENT_CHIMNEY_OFFLOAD_TCP_CHARACTERISTICS</a>


For more information on the 2 chimney offload structures, see 
    <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/network/full-tcp-offload">NDIS 6.0 TCP chimney offload
    documentation</a>.

Miniport drivers call 
    <b>NdisSetOptionalHandlers</b> in the context of the 
    <a href="https://msdn.microsoft.com/en-us/library/windows/hardware/ff570269">MiniportSetOptions</a> function.

In this case, the valid structures are:


<a href="..\ndis\ns-ndis-_ndis_miniport_co_characteristics.md">
       NDIS_MINIPORT_CO_CHARACTERISTICS</a>



<a href="..\ndis\ns-ndis-_ndis_miniport_pnp_characteristics.md">
       NDIS_MINIPORT_PNP_CHARACTERISTICS</a>



<a href="..\ndis\ns-ndis-_ndis_miniport_ss_characteristics.md">NDIS_MINIPORT_SS_CHARACTERISTICS</a>



<a href="..\ndisndk\ns-ndisndk-_ndis_ndk_provider_characteristics.md">NDIS_NDK_PROVIDER_CHARACTERISTICS</a>



<a href="..\ndis\ns-ndis-_ndis_co_call_manager_optional_handlers.md">
       NDIS_CO_CALL_MANAGER_OPTIONAL_HANDLERS</a>



<a href="..\ndis\ns-ndis-_ndis_shared_memory_provider_characteristics.md">
       NDIS_SHARED_MEMORY_PROVIDER_CHARACTERISTICS</a>



<a href="..\ndischimney\ns-ndischimney-_ndis_client_chimney_offload_generic_characteristics.md">
       NDIS_CLIENT_CHIMNEY_OFFLOAD_GENERIC_CHARACTERISTICS</a>



<a href="..\ndischimney\ns-ndischimney-_ndis_client_chimney_offload_tcp_characteristics.md">
       NDIS_CLIENT_CHIMNEY_OFFLOAD_TCP_CHARACTERISTICS</a>


For more information on the 2 chimney offload structures, see 
    <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/network/full-tcp-offload">NDIS 6.0 TCP chimney offload
    documentation</a>.

Filter drivers call 
    <b>NdisSetOptionalHandlers</b> in the context of the 
    <a href="https://msdn.microsoft.com/en-us/library/windows/hardware/ff570269">FilterSetOptions</a> function.

There are no optional filter driver services in the current Windows version.

Filter drivers can call 
    <b>NdisSetOptionalHandlers</b> for a filter module. Filter drivers call 
    <b>NdisSetOptionalHandlers</b> in the context of the 
    <a href="..\ndis\nc-ndis-filter_set_module_options.md">
    FilterSetModuleOptions</a> function.

In this case, the valid structures are:


<a href="..\ndis\ns-ndis-_ndis_filter_partial_characteristics.md">
       NDIS_FILTER_PARTIAL_CHARACTERISTICS</a>



<a href="..\ndischimney\ns-ndischimney-_ndis_client_chimney_offload_generic_characteristics.md">NDIS_CLIENT_CHIMNEY_OFFLOAD_GENERIC_CHARACTERISTICS</a>



<a href="..\ndischimney\ns-ndischimney-_ndis_client_chimney_offload_tcp_characteristics.md">NDIS_CLIENT_CHIMNEY_OFFLOAD_TCP_CHARACTERISTICS</a>



<a href="..\ndischimney\ns-ndischimney-_ndis_provider_chimney_offload_generic_characteristics.md">NDIS_PROVIDER_CHIMNEY_OFFLOAD_GENERIC_CHARACTERISTICS</a>



<a href="..\ndischimney\ns-ndischimney-_ndis_provider_chimney_offload_tcp_characteristics.md">NDIS_PROVIDER_CHIMNEY_OFFLOAD_TCP_CHARACTERISTICS</a>


For more information on the 4 chimney offload structures, see 
    <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/network/full-tcp-offload">NDIS 6.0 TCP chimney offload
    documentation</a>.



## -see-also

<a href="..\ndis\nf-ndis-ndisopenadapterex.md">NdisOpenAdapterEx</a>

<a href="..\ndis\ns-ndis-_ndis_protocol_co_characteristics.md">
   NDIS_PROTOCOL_CO_CHARACTERISTICS</a>

<a href="..\ndis\nc-ndis-filter_attach.md">FilterAttach</a>

<a href="..\ndis\nc-ndis-filter_restart.md">FilterRestart</a>

<a href="..\ndis\ns-ndis-_ndis_miniport_pnp_characteristics.md">
   NDIS_MINIPORT_PNP_CHARACTERISTICS</a>

<a href="https://msdn.microsoft.com/en-us/library/windows/hardware/ff570269">MiniportSetOptions</a>

<a href="https://msdn.microsoft.com/en-us/library/windows/hardware/ff570269">FilterSetOptions</a>

<a href="..\ndis\ns-ndis-_ndis_miniport_co_characteristics.md">
   NDIS_MINIPORT_CO_CHARACTERISTICS</a>

<a href="..\ndis\ns-ndis-_ndis_shared_memory_provider_characteristics.md">
   NDIS_SHARED_MEMORY_PROVIDER_CHARACTERISTICS</a>

<a href="..\ndis\ns-ndis-_ndis_co_client_optional_handlers.md">
   NDIS_CO_CLIENT_OPTIONAL_HANDLERS</a>

<a href="..\ndis\ns-ndis-_ndis_co_call_manager_optional_handlers.md">
   NDIS_CO_CALL_MANAGER_OPTIONAL_HANDLERS</a>

<a href="..\ndis\ns-ndis-_ndis_filter_partial_characteristics.md">
   NDIS_FILTER_PARTIAL_CHARACTERISTICS</a>

<a href="..\ndis\nf-ndis-ndismregisterminiportdriver.md">NdisMRegisterMiniportDriver</a>

<a href="..\ndis\nc-ndis-set_options.md">ProtocolSetOptions</a>

<a href="..\ndis\nc-ndis-protocol_open_adapter_complete_ex.md">
   ProtocolOpenAdapterCompleteEx</a>

<a href="..\ndis\nc-ndis-protocol_bind_adapter_ex.md">ProtocolBindAdapterEx</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20NdisSetOptionalHandlers function%20 RELEASE:%20(1/18/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

