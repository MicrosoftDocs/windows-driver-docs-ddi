---
UID: NC:ndis.SET_OPTIONS
title: SET_OPTIONS
author: windows-driver-content
description: NDIS calls a driver's XxxSetOptions function to allow the driver to register optional services.
old-location: netvista\protocolsetoptions.htm
old-project: netvista
ms.assetid: 342e23ad-d38b-4100-949a-220b8fbdcf6e
ms.author: windowsdriverdev
ms.date: 2/27/2018
ms.keywords: SET_OPTIONS, SetOptions, SetOptions callback function [Network Drivers Starting with Windows Vista], ndis/SetOptions, netvista.protocolsetoptions, protocol_functions_ref_be1126b7-c5ae-4d43-90d4-8e10d97f422d.xml
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	UserDefined
api_location:
-	Ndis.h
api_name:
-	SetOptions
product: Windows
targetos: Windows
req.typenames: VIDEO_STREAM_INIT_PARMS, *LPVIDEO_STREAM_INIT_PARMS
---

# SET_OPTIONS callback


## -description


NDIS calls a driver's 
  <i>XxxSetOptions</i> function to allow the driver to register optional services. This function is defined as <i>MiniportSetOptions</i> for miniport drivers,  <i>ProtocolSetOptions</i> for protocol drivers, or <i>FilterSetOptions</i> for filter drivers.
<div class="alert"><b>Note</b>  You must declare the function by using the <b>Xxx_SET_OPTIONS</b> type. For more
   information, see the Examples section.</div><div> </div>

## -parameters




### -param NdisDriverHandle [in]

A handle that identifies a driver. NDIS returns this handle to the driver when it returns from the driver registration function (<a href="https://msdn.microsoft.com/bed68aa8-499d-41fd-997b-a46316913cc8">
     NdisMRegisterMiniportDriver</a> for miniport drivers, <a href="https://msdn.microsoft.com/b48571eb-13a2-4541-80ac-c8d31f378d37">
     NdisRegisterProtocolDriver</a> for protocol drivers, and <a href="https://msdn.microsoft.com/14381de2-36d9-4ec8-9d4e-7af3e6d8ecf3">
     NdisFRegisterFilterDriver</a> for filter drivers).


### -param DriverContext [in]

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
    <a href="https://msdn.microsoft.com/library/windows/hardware/ff564550">NdisSetOptionalHandlers</a> function.
    The driver passes the handle from the 
    <i>NdisDriverHandle</i> parameter at the 
    <i>NdisHandle</i> parameter of 
    <b>NdisSetOptionalHandlers</b> and passes a characteristics structure at the 
    <i>OptionalHandlers</i> parameter.

Miniport drivers can apply to the optional services defined in the following characteristics structures:<dl>
<dd>

<a href="https://msdn.microsoft.com/9348c338-9fb4-4eee-a50f-f709748da56b">
       NDIS_MINIPORT_CO_CHARACTERISTICS</a>


</dd>
<dd>

<a href="https://msdn.microsoft.com/97820a22-aa20-4d47-a4c2-0c0d50540823">
       NDIS_MINIPORT_PNP_CHARACTERISTICS</a>


</dd>
<dd>

<a href="https://msdn.microsoft.com/12d541e1-04dd-4512-827e-d27f16260fe3">
       NDIS_CO_CALL_MANAGER_OPTIONAL_HANDLERS</a>


</dd>
<dd>

<a href="https://msdn.microsoft.com/e80a9999-2e4e-4da0-8aae-54ee71d9249d">
      NDIS_PROVIDER_CHIMNEY_OFFLOAD_GENERIC_CHARACTERISTICS</a>(see 
      <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/network/full-tcp-offload">NDIS 6.0 TCP chimney offload
      documentation</a>)

</dd>
<dd>

<a href="https://msdn.microsoft.com/3eabbad5-b84b-4034-a0b6-d4d515cbc117">
      NDIS_PROVIDER_CHIMNEY_OFFLOAD_TCP_CHARACTERISTICS</a>(see 
      <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/network/full-tcp-offload">NDIS 6.0 TCP chimney offload
      documentation</a>)

</dd>
</dl>


Protocol drivers can apply to the optional services defined in the following characteristics structures:<dl>
<dd>

<a href="https://msdn.microsoft.com/855e3231-502c-4c6f-99f9-7ad85354ccd5">
       NDIS_PROTOCOL_CO_CHARACTERISTICS</a>


</dd>
<dd>

<a href="https://msdn.microsoft.com/1f2285bb-be70-4496-905d-89106bf3712a">
       NDIS_CO_CLIENT_OPTIONAL_HANDLERS</a>


</dd>
<dd>

<a href="https://msdn.microsoft.com/12d541e1-04dd-4512-827e-d27f16260fe3">
       NDIS_CO_CALL_MANAGER_OPTIONAL_HANDLERS</a>


</dd>
</dl>


There are no optional filter driver services in the current Windows version.

NDIS can call the driver's other 
    <i>MiniportXxx</i>,  <i>ProtocolXxx</i>, or <i>FilterXxx</i> functions at any time after 
    <i>XxxSetOptions</i> returns. The driver should be prepared to be called back at its initialization function:(<a href="https://msdn.microsoft.com/b146fa81-005b-4a6c-962d-4cb023ea790e">MiniportInitializeEx</a> for miniport drivers, <a href="https://msdn.microsoft.com/1958722e-012e-4110-a82c-751744bcf9b5">ProtocolBindAdapterEx</a> for protocol drivers, and <a href="https://msdn.microsoft.com/library/windows/hardware/ff540442">FilterAttach</a> for filter drivers).


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
To define a <i>XxxSetOptions</i> function, you must first provide a function declaration that identifies the type of function you're defining. Windows provides a set of function types for drivers. Declaring a function using the function types helps <a href="https://msdn.microsoft.com/2F3549EF-B50F-455A-BDC7-1F67782B8DCA">Code Analysis for Drivers</a>, <a href="https://msdn.microsoft.com/74feeb16-387c-4796-987a-aff3fb79b556">Static Driver Verifier</a> (SDV), and other verification tools find errors, and it's a requirement for writing drivers for the Windows operating system.

In the Ndis.h header file, the SET_OPTIONS callback function is further defined as follows:<pre class="syntax" xml:space="preserve"><code>typedef SET_OPTIONS (*SET_OPTIONS_HANDLER);
typedef SET_OPTIONS (MINIPORT_SET_OPTIONS);
typedef SET_OPTIONS (PROTOCOL_SET_OPTIONS);
typedef SET_OPTIONS (FILTER_SET_OPTIONS);</code></pre>This enables all NDIS drivers to implement their XxxSetOptions callback functions with the same syntax. Miniport drivers use the <b>MINIPORT_SET_OPTIONS</b> type, protocol drivers use the <b>PROTOCOL_SET_OPTIONS</b> type, and filter drivers use the <b>FILTER_SET_OPTIONS</b> type.

For example, to define a <i>MiniportSetOptions</i> function that is named "MySetOptions", use the <b>MINIPORT_SET_OPTIONS</b> type as shown in this code example:

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>MINIPORT_SET_OPTIONS MySetOptions;</pre>
</td>
</tr>
</table></span></div>
Then, implement your function as follows:

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>_Use_decl_annotations_
NDIS_STATUS
 MySetOptions(
    NDIS_HANDLE  NdisDriverHandle,
    NDIS_HANDLE  DriverContext
    )
  {...}</pre>
</td>
</tr>
</table></span></div>
The <b>SET_OPTIONS</b> function type is defined in the Ndis.h header file. To more accurately identify errors when you run the code analysis tools, be sure to add the _Use_decl_annotations_ annotation to your function definition.  The _Use_decl_annotations_ annotation ensures that the annotations that are applied to the <b>SET_OPTIONS</b> function type in the header file are used.  For more information about the requirements for function declarations, see <a href="https://msdn.microsoft.com/232c4272-0bf0-4a4e-9560-3bceeca8a3e3">Declaring Functions by Using Function Role Types for NDIS Drivers</a>.

For information about  _Use_decl_annotations_, see <a href="http://go.microsoft.com/fwlink/p/?linkid=286697">Annotating Function Behavior</a>. 




## -see-also




<a href="https://msdn.microsoft.com/12d541e1-04dd-4512-827e-d27f16260fe3">
   NDIS_CO_CALL_MANAGER_OPTIONAL_HANDLERS</a>



<a href="https://msdn.microsoft.com/1f2285bb-be70-4496-905d-89106bf3712a">
   NDIS_CO_CLIENT_OPTIONAL_HANDLERS</a>



<a href="https://msdn.microsoft.com/855e3231-502c-4c6f-99f9-7ad85354ccd5">
   NDIS_PROTOCOL_CO_CHARACTERISTICS</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff563715">NdisOpenAdapterEx</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff564520">NdisRegisterProtocolDriver</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff564550">NdisSetOptionalHandlers</a>



<a href="https://msdn.microsoft.com/1958722e-012e-4110-a82c-751744bcf9b5">ProtocolBindAdapterEx</a>
 

 

<<<<<<< HEAD
=======
<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20SET_OPTIONS callback function%20 RELEASE:%20(2/27/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

>>>>>>> parent of 2d896a8e266... Added changes
