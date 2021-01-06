---
UID: NC:ndis.SET_OPTIONS
title: SET_OPTIONS (ndis.h)
description: NDIS calls a driver's XxxSetOptions function to allow the driver to register optional services.
old-location: netvista\protocolsetoptions.htm
tech.root: netvista
ms.date: 05/02/2018
keywords: ["SET_OPTIONS callback function"]
ms.keywords: SET_OPTIONS, SET_OPTIONS callback, SetOptions, SetOptions callback function [Network Drivers Starting with Windows Vista], ndis/SetOptions, netvista.protocolsetoptions, protocol_functions_ref_be1126b7-c5ae-4d43-90d4-8e10d97f422d.xml
req.header: ndis.h
req.include-header: Ndis.h
req.target-type: Windows
req.target-min-winverclnt: Supported in NDIS 6.0 and later.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: PASSIVE_LEVEL
targetos: Windows
req.typenames: 
f1_keywords:
 - SET_OPTIONS
 - ndis/SET_OPTIONS
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - Ndis.h
api_name:
 - SetOptions
---

# SET_OPTIONS callback function


## -description

NDIS calls a driver's 
  <i>XxxSetOptions</i> function to allow the driver to register optional services. This function is defined as <i>MiniportSetOptions</i> for miniport drivers,  <i>ProtocolSetOptions</i> for protocol drivers, or <i>FilterSetOptions</i> for filter drivers.
<div class="alert"><b>Note</b>  You must declare the function by using the <b>Xxx_SET_OPTIONS</b> type. For more
   information, see the Examples section.</div><div> </div>

## -parameters

### -param NdisDriverHandle 

[in]
A handle that identifies a driver. NDIS returns this handle to the driver when it returns from the driver registration function (<a href="/windows-hardware/drivers/ddi/ndis/nf-ndis-ndismregisterminiportdriver">
     NdisMRegisterMiniportDriver</a> for miniport drivers, <a href="/windows-hardware/drivers/ddi/ndis/nf-ndis-ndisregisterprotocoldriver">
     NdisRegisterProtocolDriver</a> for protocol drivers, and <a href="/windows-hardware/drivers/ddi/ndis/nf-ndis-ndisfregisterfilterdriver">
     NdisFRegisterFilterDriver</a> for filter drivers).

### -param DriverContext 

[in]
The handle that the driver passed to 
     <b>NdisRegisterXxxDriver</b> that identifies the driver context area, where Xxx is the type of driver (Miniport, Protocol, or Filter).

## -returns

<i>XxxSetOptions</i> returns one of the following status values:

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
<i>XxxSetOptions</i> successfully registered the driver's optional services and
       resources.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>NDIS_STATUS_RESOURCES</b></dt>
</dl>
</td>
<td width="60%">
<i>XxxSetOptions</i> could not allocate the resources that the driver requires.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>NDIS_STATUS_XXX or NTSTATUS_XXX</b></dt>
</dl>
</td>
<td width="60%">
The driver's attempt to register options failed. Usually, such an error status is
       propagated from an 
       <b>Ndis<i>Xxx</i></b> function or a kernel-mode support routine.

</td>
</tr>
</table>

## -remarks

<i>XxxSetOptions</i> is an optional function. NDIS calls 
    <i>XxxSetOptions</i> within the context of the driver's call to the 
    <b>
    NdisRegisterXxxDriver</b> function, where Xxx is the type of driver (Miniport, Protocol, or Filter).

<i>XxxSetOptions</i> registers optional services and can allocate other driver resources. To register
    optional 
    <i>MiniportXxx</i>, <i>ProtocolXxx</i>, or <i>FilterXxx</i> functions, the driver calls the 
    <a href="/windows-hardware/drivers/ddi/ndis/nf-ndis-ndissetoptionalhandlers">NdisSetOptionalHandlers</a> function.
    The driver passes the handle from the 
    <i>NdisDriverHandle</i> parameter at the 
    <i>NdisHandle</i> parameter of 
    <b>NdisSetOptionalHandlers</b> and passes a characteristics structure at the 
    <i>OptionalHandlers</i> parameter.

Miniport drivers can apply to the optional services defined in the following characteristics structures:<dl>
<dd>

<a href="/windows-hardware/drivers/ddi/ndis/ns-ndis-_ndis_miniport_co_characteristics">
       NDIS_MINIPORT_CO_CHARACTERISTICS</a>


</dd>
<dd>

<a href="/windows-hardware/drivers/ddi/ndis/ns-ndis-_ndis_miniport_pnp_characteristics">
       NDIS_MINIPORT_PNP_CHARACTERISTICS</a>


</dd>
<dd>

<a href="/windows-hardware/drivers/ddi/ndis/ns-ndis-_ndis_co_call_manager_optional_handlers">
       NDIS_CO_CALL_MANAGER_OPTIONAL_HANDLERS</a>


</dd>
<dd>

<a href="/windows-hardware/drivers/ddi/ndischimney/ns-ndischimney-_ndis_provider_chimney_offload_generic_characteristics">
      NDIS_PROVIDER_CHIMNEY_OFFLOAD_GENERIC_CHARACTERISTICS</a>(see 
      <a href="/windows-hardware/drivers/network/full-tcp-offload">NDIS 6.0 TCP chimney offload
      documentation</a>)

</dd>
<dd>

<a href="/windows-hardware/drivers/ddi/ndischimney/ns-ndischimney-_ndis_provider_chimney_offload_tcp_characteristics">
      NDIS_PROVIDER_CHIMNEY_OFFLOAD_TCP_CHARACTERISTICS</a>(see 
      <a href="/windows-hardware/drivers/network/full-tcp-offload">NDIS 6.0 TCP chimney offload
      documentation</a>)

</dd>
</dl>


Protocol drivers can apply to the optional services defined in the following characteristics structures:<dl>
<dd>

<a href="/windows-hardware/drivers/ddi/ndis/ns-ndis-_ndis_protocol_co_characteristics">
       NDIS_PROTOCOL_CO_CHARACTERISTICS</a>


</dd>
<dd>

<a href="/windows-hardware/drivers/ddi/ndis/ns-ndis-_ndis_co_client_optional_handlers">
       NDIS_CO_CLIENT_OPTIONAL_HANDLERS</a>


</dd>
<dd>

<a href="/windows-hardware/drivers/ddi/ndis/ns-ndis-_ndis_co_call_manager_optional_handlers">
       NDIS_CO_CALL_MANAGER_OPTIONAL_HANDLERS</a>


</dd>
</dl>


There are no optional filter driver services in the current Windows version.

NDIS can call the driver's other 
    <i>MiniportXxx</i>,  <i>ProtocolXxx</i>, or <i>FilterXxx</i> functions at any time after 
    <i>XxxSetOptions</i> returns. The driver should be prepared to be called back at its initialization function:(<a href="/windows-hardware/drivers/ddi/ndis/nc-ndis-miniport_initialize">MiniportInitializeEx</a> for miniport drivers, <a href="/windows-hardware/drivers/ddi/ndis/nc-ndis-protocol_bind_adapter_ex">ProtocolBindAdapterEx</a> for protocol drivers, and <a href="/windows-hardware/drivers/ddi/ndis/nc-ndis-filter_attach">FilterAttach</a> for filter drivers).

For miniport drivers, the
miniport adapters are in the 
<i>Halted</i> state before the NDIS calls 
<i>MiniportInitializeEx</i>. For protocol drivers, the protocol bindings are in the 
<i>Unbound</i> state before the NDIS calls 
<i>ProtocolBindAdapterEx</i>. For filter drivers, the filter modules
are in the 
<i>Detached</i> state before the NDIS calls 
<i>FilterAttach</i>.

If an attempt to allocate resources or services fails, 
    <i>XxxSetOptions</i> should undo all the allocations that succeeded before it returns control with a
    status other than NDIS_STATUS_SUCCESS.

Miniport and filter drivers' <i>XxxDriverUnload</i> should undo all the operations that were performed in <i>XxxSetOptions</i>

NDIS calls 
    <i>XxxSetOptions</i> at IRQL = PASSIVE_LEVEL.

<h3><a id="Examples"></a><a id="examples"></a><a id="EXAMPLES"></a>Examples</h3>
To define a <i>XxxSetOptions</i> function, you must first provide a function declaration that identifies the type of function you're defining. Windows provides a set of function types for drivers. Declaring a function using the function types helps <a href="/windows-hardware/drivers/devtest/code-analysis-for-drivers">Code Analysis for Drivers</a>, <a href="/windows-hardware/drivers/devtest/static-driver-verifier">Static Driver Verifier</a> (SDV), and other verification tools find errors, and it's a requirement for writing drivers for the Windows operating system.

In the Ndis.h header file, the SET_OPTIONS callback function is further defined as follows:<pre class="syntax" xml:space="preserve"><code>typedef SET_OPTIONS (*SET_OPTIONS_HANDLER);
typedef SET_OPTIONS (MINIPORT_SET_OPTIONS);
typedef SET_OPTIONS (PROTOCOL_SET_OPTIONS);
typedef SET_OPTIONS (FILTER_SET_OPTIONS);</code></pre>This enables all NDIS drivers to implement their XxxSetOptions callback functions with the same syntax. Miniport drivers use the <b>MINIPORT_SET_OPTIONS</b> type, protocol drivers use the <b>PROTOCOL_SET_OPTIONS</b> type, and filter drivers use the <b>FILTER_SET_OPTIONS</b> type.

For example, to define a <i>MiniportSetOptions</i> function that is named "MySetOptions", use the <b>MINIPORT_SET_OPTIONS</b> type as shown in this code example:


```
MINIPORT_SET_OPTIONS MySetOptions;
```

Then, implement your function as follows:


```
_Use_decl_annotations_
NDIS_STATUS
 MySetOptions(
    NDIS_HANDLE  NdisDriverHandle,
    NDIS_HANDLE  DriverContext
    )
  {...}
```

The <b>SET_OPTIONS</b> function type is defined in the Ndis.h header file. To more accurately identify errors when you run the code analysis tools, be sure to add the _Use_decl_annotations_ annotation to your function definition.  The _Use_decl_annotations_ annotation ensures that the annotations that are applied to the <b>SET_OPTIONS</b> function type in the header file are used.  For more information about the requirements for function declarations, see <a href="/windows-hardware/drivers/devtest/declaring-functions-by-using-function-role-types-for-ndis-drivers">Declaring Functions by Using Function Role Types for NDIS Drivers</a>.

For information about  _Use_decl_annotations_, see <a href="/visualstudio/code-quality/annotating-function-behavior">Annotating Function Behavior</a>.

## -see-also

<a href="/windows-hardware/drivers/ddi/ndis/ns-ndis-_ndis_co_call_manager_optional_handlers">
   NDIS_CO_CALL_MANAGER_OPTIONAL_HANDLERS</a>



<a href="/windows-hardware/drivers/ddi/ndis/ns-ndis-_ndis_co_client_optional_handlers">
   NDIS_CO_CLIENT_OPTIONAL_HANDLERS</a>



<a href="/windows-hardware/drivers/ddi/ndis/ns-ndis-_ndis_protocol_co_characteristics">
   NDIS_PROTOCOL_CO_CHARACTERISTICS</a>



<a href="/windows-hardware/drivers/ddi/ndis/nf-ndis-ndisopenadapterex">NdisOpenAdapterEx</a>



<a href="/windows-hardware/drivers/ddi/ndis/nf-ndis-ndisregisterprotocoldriver">NdisRegisterProtocolDriver</a>



<a href="/windows-hardware/drivers/ddi/ndis/nf-ndis-ndissetoptionalhandlers">NdisSetOptionalHandlers</a>



<a href="/windows-hardware/drivers/ddi/ndis/nc-ndis-protocol_bind_adapter_ex">ProtocolBindAdapterEx</a>
