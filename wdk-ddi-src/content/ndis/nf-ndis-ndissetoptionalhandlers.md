---
UID: NF:ndis.NdisSetOptionalHandlers
title: NdisSetOptionalHandlers function
author: windows-driver-content
description: NDIS drivers can call the NdisSetOptionalHandlers function to set or change the entry points of driver functions.
old-location: netvista\ndissetoptionalhandlers.htm
old-project: netvista
ms.assetid: 97649f4f-942a-47fc-a541-6f160c8b4eb4
ms.author: windowsdriverdev
ms.date: 3/26/2018
ms.keywords: NdisSetOptionalHandlers, NdisSetOptionalHandlers function [Network Drivers Starting with Windows Vista], ndis/NdisSetOptionalHandlers, ndis_configuration_ref_343cba4f-9651-4f42-b0a9-0a85475cb6bf.xml, netvista.ndissetoptionalhandlers
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	LibDef
api_location:
-	ndis.lib
-	ndis.dll
api_name:
-	NdisSetOptionalHandlers
product:
- Windows
targetos: Windows
req.typenames: NDIS_SHARED_MEMORY_USAGE, *PNDIS_SHARED_MEMORY_USAGE
---

# NdisSetOptionalHandlers function


## -description


NDIS drivers can call the 
  <b>NdisSetOptionalHandlers</b> function to set or change the entry points of driver functions.


## -parameters




### -param NdisHandle

An NDIS handle that identifies a driver or driver instance.
     

For a protocol driver, this is the 
     <i>NdisDriverHandle</i> value passed to the 
     <a href="https://msdn.microsoft.com/342e23ad-d38b-4100-949a-220b8fbdcf6e">ProtocolSetOptions</a> function or the 
     <i>NdisBindingHandle</i> value obtained by calling the 
     <a href="https://msdn.microsoft.com/library/windows/hardware/ff563715">NdisOpenAdapterEx</a> function.

For a miniport driver, this is the 
     <i>NdisDriverHandle</i> value passed to the 
     <a href="https://msdn.microsoft.com/en-us/library/windows/hardware/ff570269">MiniportSetOptions</a> function

For a filter driver, this is the 
     <i>NdisDriverHandle</i> value passed to the 
     <a href="https://msdn.microsoft.com/en-us/library/windows/hardware/ff570269">FilterSetOptions</a> function or the 
     <i>NdisFilterHandle</i> value passed to the 
     <a href="https://msdn.microsoft.com/library/windows/hardware/ff540442">FilterAttach</a> function.


### -param OptionalHandlers

A pointer to one of the following NDIS structures:
     


<a href="https://msdn.microsoft.com/66eb9528-e026-44cd-a775-c8d963036adc">
        NDIS_CLIENT_CHIMNEY_OFFLOAD_GENERIC_CHARACTERISTICS</a>



<a href="https://msdn.microsoft.com/1925cfd4-f83f-48a5-b928-2c663ac0dc61">
        NDIS_CLIENT_CHIMNEY_OFFLOAD_TCP_CHARACTERISTICS</a>



<a href="https://msdn.microsoft.com/12d541e1-04dd-4512-827e-d27f16260fe3">
        NDIS_CO_CALL_MANAGER_OPTIONAL_HANDLERS</a>



<a href="https://msdn.microsoft.com/1f2285bb-be70-4496-905d-89106bf3712a">
        NDIS_CO_CLIENT_OPTIONAL_HANDLERS</a>



<a href="https://msdn.microsoft.com/4a7f365c-a252-4d8e-bddf-684b3298db5c">
        NDIS_FILTER_PARTIAL_CHARACTERISTICS</a>



<a href="https://msdn.microsoft.com/9348c338-9fb4-4eee-a50f-f709748da56b">
        NDIS_MINIPORT_CO_CHARACTERISTICS</a>



<a href="https://msdn.microsoft.com/97820a22-aa20-4d47-a4c2-0c0d50540823">
        NDIS_MINIPORT_PNP_CHARACTERISTICS</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh451559">NDIS_MINIPORT_SS_CHARACTERISTICS</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh451566">NDIS_NDK_PROVIDER_CHARACTERISTICS</a>



<a href="https://msdn.microsoft.com/855e3231-502c-4c6f-99f9-7ad85354ccd5">
        NDIS_PROTOCOL_CO_CHARACTERISTICS</a>



<a href="https://msdn.microsoft.com/e80a9999-2e4e-4da0-8aae-54ee71d9249d">
        NDIS_PROVIDER_CHIMNEY_OFFLOAD_GENERIC_CHARACTERISTICS</a>



<a href="https://msdn.microsoft.com/3eabbad5-b84b-4034-a0b6-d4d515cbc117">
        NDIS_PROVIDER_CHIMNEY_OFFLOAD_TCP_CHARACTERISTICS</a>



<a href="https://msdn.microsoft.com/45001da1-5fe3-4383-8da7-31e3ee115c1f">
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

<a href="https://msdn.microsoft.com/library/windows/hardware/ff564550">NdisSetOptionalHandlers</a> returns <b>NDIS_STATUS_SUCCESS</b> if it set the driver entry points.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>NDIS_STATUS_RESOURCES</b></dt>
</dl>
</td>
<td width="60%">

<a href="https://msdn.microsoft.com/library/windows/hardware/ff564550">NdisSetOptionalHandlers</a> failed due to insufficient resources.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>NDIS_STATUS_NOT_SUPPORTED</b></dt>
</dl>
</td>
<td width="60%">

<a href="https://msdn.microsoft.com/library/windows/hardware/ff564550">NdisSetOptionalHandlers</a> failed because the miniport driver did not specify that it supports NDIS
       6.0 or later. A miniport driver specifies its NDIS version when it calls the 
       <a href="https://msdn.microsoft.com/bed68aa8-499d-41fd-997b-a46316913cc8">
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

<a href="https://msdn.microsoft.com/library/windows/hardware/ff564550">NdisSetOptionalHandlers</a> returns <b>NDIS_STATUS_FAILURE</b> if none of the preceding values
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
    <a href="https://msdn.microsoft.com/342e23ad-d38b-4100-949a-220b8fbdcf6e">ProtocolSetOptions</a> function. As an option, protocol drivers can call 
    <b>NdisSetOptionalHandlers</b> from the 
    <a href="https://msdn.microsoft.com/1958722e-012e-4110-a82c-751744bcf9b5">ProtocolBindAdapterEx</a> function or
    the 
    <a href="https://msdn.microsoft.com/59d18822-8ce2-4506-90d7-9f1cdc7a9e10">
    ProtocolOpenAdapterCompleteEx</a> function after the protocol driver has a valid handle from the 
    <a href="https://msdn.microsoft.com/library/windows/hardware/ff563715">NdisOpenAdapterEx</a> function.

In this case, the valid structures are:


<a href="https://msdn.microsoft.com/855e3231-502c-4c6f-99f9-7ad85354ccd5">
       NDIS_PROTOCOL_CO_CHARACTERISTICS</a>



<a href="https://msdn.microsoft.com/1f2285bb-be70-4496-905d-89106bf3712a">
       NDIS_CO_CLIENT_OPTIONAL_HANDLERS</a>



<a href="https://msdn.microsoft.com/12d541e1-04dd-4512-827e-d27f16260fe3">
       NDIS_CO_CALL_MANAGER_OPTIONAL_HANDLERS</a>



<a href="https://msdn.microsoft.com/45001da1-5fe3-4383-8da7-31e3ee115c1f">
       NDIS_SHARED_MEMORY_PROVIDER_CHARACTERISTICS</a>



<a href="https://msdn.microsoft.com/66eb9528-e026-44cd-a775-c8d963036adc">
       NDIS_CLIENT_CHIMNEY_OFFLOAD_GENERIC_CHARACTERISTICS</a>



<a href="https://msdn.microsoft.com/1925cfd4-f83f-48a5-b928-2c663ac0dc61">
       NDIS_CLIENT_CHIMNEY_OFFLOAD_TCP_CHARACTERISTICS</a>


For more information on the 2 chimney offload structures, see 
    <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/network/full-tcp-offload">NDIS 6.0 TCP chimney offload
    documentation</a>.

Miniport drivers call 
    <b>NdisSetOptionalHandlers</b> in the context of the 
    <a href="https://msdn.microsoft.com/en-us/library/windows/hardware/ff570269">MiniportSetOptions</a> function.

In this case, the valid structures are:


<a href="https://msdn.microsoft.com/9348c338-9fb4-4eee-a50f-f709748da56b">
       NDIS_MINIPORT_CO_CHARACTERISTICS</a>



<a href="https://msdn.microsoft.com/97820a22-aa20-4d47-a4c2-0c0d50540823">
       NDIS_MINIPORT_PNP_CHARACTERISTICS</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh451559">NDIS_MINIPORT_SS_CHARACTERISTICS</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh451566">NDIS_NDK_PROVIDER_CHARACTERISTICS</a>



<a href="https://msdn.microsoft.com/12d541e1-04dd-4512-827e-d27f16260fe3">
       NDIS_CO_CALL_MANAGER_OPTIONAL_HANDLERS</a>



<a href="https://msdn.microsoft.com/45001da1-5fe3-4383-8da7-31e3ee115c1f">
       NDIS_SHARED_MEMORY_PROVIDER_CHARACTERISTICS</a>



<a href="https://msdn.microsoft.com/66eb9528-e026-44cd-a775-c8d963036adc">
       NDIS_CLIENT_CHIMNEY_OFFLOAD_GENERIC_CHARACTERISTICS</a>



<a href="https://msdn.microsoft.com/1925cfd4-f83f-48a5-b928-2c663ac0dc61">
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
    <a href="https://msdn.microsoft.com/04b7ac32-8996-4648-8c88-aa9f630b1bc4">
    FilterSetModuleOptions</a> function.

In this case, the valid structures are:


<a href="https://msdn.microsoft.com/4a7f365c-a252-4d8e-bddf-684b3298db5c">
       NDIS_FILTER_PARTIAL_CHARACTERISTICS</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff564840">NDIS_CLIENT_CHIMNEY_OFFLOAD_GENERIC_CHARACTERISTICS</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff564846">NDIS_CLIENT_CHIMNEY_OFFLOAD_TCP_CHARACTERISTICS</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff566846">NDIS_PROVIDER_CHIMNEY_OFFLOAD_GENERIC_CHARACTERISTICS</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff566852">NDIS_PROVIDER_CHIMNEY_OFFLOAD_TCP_CHARACTERISTICS</a>


For more information on the 4 chimney offload structures, see 
    <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/network/full-tcp-offload">NDIS 6.0 TCP chimney offload
    documentation</a>.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff540442">FilterAttach</a>



<a href="https://msdn.microsoft.com/4a917824-eef1-4945-b45e-1c940bc8a50d">FilterRestart</a>



<a href="https://msdn.microsoft.com/en-us/library/windows/hardware/ff570269">FilterSetOptions</a>



<a href="https://msdn.microsoft.com/en-us/library/windows/hardware/ff570269">MiniportSetOptions</a>



<a href="https://msdn.microsoft.com/12d541e1-04dd-4512-827e-d27f16260fe3">
   NDIS_CO_CALL_MANAGER_OPTIONAL_HANDLERS</a>



<a href="https://msdn.microsoft.com/1f2285bb-be70-4496-905d-89106bf3712a">
   NDIS_CO_CLIENT_OPTIONAL_HANDLERS</a>



<a href="https://msdn.microsoft.com/4a7f365c-a252-4d8e-bddf-684b3298db5c">
   NDIS_FILTER_PARTIAL_CHARACTERISTICS</a>



<a href="https://msdn.microsoft.com/9348c338-9fb4-4eee-a50f-f709748da56b">
   NDIS_MINIPORT_CO_CHARACTERISTICS</a>



<a href="https://msdn.microsoft.com/97820a22-aa20-4d47-a4c2-0c0d50540823">
   NDIS_MINIPORT_PNP_CHARACTERISTICS</a>



<a href="https://msdn.microsoft.com/855e3231-502c-4c6f-99f9-7ad85354ccd5">
   NDIS_PROTOCOL_CO_CHARACTERISTICS</a>



<a href="https://msdn.microsoft.com/45001da1-5fe3-4383-8da7-31e3ee115c1f">
   NDIS_SHARED_MEMORY_PROVIDER_CHARACTERISTICS</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff563654">NdisMRegisterMiniportDriver</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff563715">NdisOpenAdapterEx</a>



<a href="https://msdn.microsoft.com/1958722e-012e-4110-a82c-751744bcf9b5">ProtocolBindAdapterEx</a>



<a href="https://msdn.microsoft.com/59d18822-8ce2-4506-90d7-9f1cdc7a9e10">
   ProtocolOpenAdapterCompleteEx</a>



<a href="https://msdn.microsoft.com/342e23ad-d38b-4100-949a-220b8fbdcf6e">ProtocolSetOptions</a>
 

 

