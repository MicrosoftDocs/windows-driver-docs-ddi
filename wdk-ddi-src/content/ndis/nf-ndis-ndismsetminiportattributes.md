---
UID: NF:ndis.NdisMSetMiniportAttributes
title: NdisMSetMiniportAttributes function (ndis.h)
description: A miniport driver must call the NdisMSetMiniportAttributes function from its MiniportInitializeEx function to identify a context area for miniport adapter to NDIS, and to provide NDIS with information about the miniport adapter.
old-location: netvista\ndismsetminiportattributes.htm
tech.root: netvista
ms.date: 05/02/2018
keywords: ["NdisMSetMiniportAttributes function"]
ms.keywords: NdisMSetMiniportAttributes, NdisMSetMiniportAttributes function [Network Drivers Starting with Windows Vista], miniport_ndis_functions_ref_2fc47304-466b-4ae0-8450-44c636cecf64.xml, ndis/NdisMSetMiniportAttributes, netvista.ndismsetminiportattributes
req.header: ndis.h
req.include-header: Ndis.h
req.target-type: Universal
req.target-min-winverclnt: Supported in NDIS 6.0 and later.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: Irql_Miniport_Driver_Function, NdisMRegisterIoPortRange
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Ndis.lib
req.dll: 
req.irql: PASSIVE_LEVEL
targetos: Windows
req.typenames: 
f1_keywords:
 - NdisMSetMiniportAttributes
 - ndis/NdisMSetMiniportAttributes
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - LibDef
api_location:
 - ndis.lib
 - ndis.dll
api_name:
 - NdisMSetMiniportAttributes
---

# NdisMSetMiniportAttributes function


## -description

A miniport driver must call the 
  <b>NdisMSetMiniportAttributes</b> function from its 
  <a href="/windows-hardware/drivers/ddi/ndis/nc-ndis-miniport_initialize">MiniportInitializeEx</a> function to
  identify a context area for miniport adapter to NDIS, and to provide NDIS with information about the
  miniport adapter.

## -parameters

### -param NdisMiniportHandle

The miniport adapter handle that NDIS passed to the 
     <i>MiniportAdapterHandle</i> parameter of 
     <a href="/windows-hardware/drivers/ddi/ndis/nc-ndis-miniport_initialize">MiniportInitializeEx</a>.

### -param MiniportAttributes [in]


A pointer to an 
     <a href="/windows-hardware/drivers/ddi/ndis/ns-ndis-_ndis_miniport_adapter_attributes">
     NDIS_MINIPORT_ADAPTER_ATTRIBUTES</a> union which contains a driver-allocated attributes structure. The
     structure defines the attributes of the miniport adapter instance that 
     <i>MiniportAdapterHandle</i> specifies.

## -returns

<b>NdisMSetMiniportAttributes</b> returns one of the following status values:

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

<a href="/windows-hardware/drivers/ddi/ndis/nf-ndis-ndismsetminiportattributes">NdisMSetMiniportAttributes</a> registered the miniport adapter attributes successfully.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>NDIS_STATUS_BAD_VERSION</b></dt>
</dl>
</td>
<td width="60%">
Indicates that NDIS does not support the version that is specified in the 
       <b>Revision</b> member of the structure specified in the 
       <b>Header</b> member at 
       <i>MiniportAttributes</i> .

</td>
</tr>
</table>

## -remarks

A miniport driver must call 
    <b>NdisMSetMiniportAttributes</b> from its 
    <a href="/windows-hardware/drivers/ddi/ndis/nc-ndis-miniport_initialize">MiniportInitializeEx</a> function
    before the driver calls any other 
    <b>Ndis<i>Xxx</i></b> function that depends on the information supplied to 
    <b>NdisMSetMiniportAttributes</b>.

The 
    <a href="/windows-hardware/drivers/ddi/ndis/ns-ndis-_ndis_miniport_adapter_attributes">
    NDIS_MINIPORT_ADAPTER_ATTRIBUTES</a> union is a placeholder for various attributes structures. A
    miniport driver calls 
    <b>NdisMSetMiniportAttributes</b> multiple times with different attributes structures. A miniport driver
    must provide an initialized 
    <a href="/windows-hardware/drivers/ddi/ndis/ns-ndis-_ndis_miniport_adapter_registration_attributes">
    NDIS_MINIPORT_ADAPTER_REGISTRATION_ATTRIBUTES</a> structure from 
    <a href="/windows-hardware/drivers/ddi/ndis/nc-ndis-miniport_initialize">MiniportInitializeEx</a>. The miniport driver must provide these registration attributes before it
    calls any other 
    <b>Ndis<i>Xxx</i></b> function that depends on these attributes or that claims hardware resources.

The driver provides a 
    <b>MiniportAdapterContext</b> member to NDIS in the <a href="/windows-hardware/drivers/ddi/ndis/ns-ndis-_ndis_miniport_adapter_registration_attributes">NDIS_MINIPORT_ADAPTER_REGISTRATION_ATTRIBUTES</a>
    structure. The 
    <b>MiniportAdapterContext</b> member identifies a caller-supplied context area that NDIS passes as an
    input parameter to the driver's 
    <i>MiniportXxx</i> functions. This context area contains miniport-adapter-specific state information.

Miniport drivers must set the attributes in the 
    <a href="/windows-hardware/drivers/ddi/ndis/ns-ndis-_ndis_miniport_adapter_general_attributes">
    NDIS_MINIPORT_ADAPTER_GENERAL_ATTRIBUTES</a> structure after they set the registration attributes in
    the <a href="/windows-hardware/drivers/ddi/ndis/ns-ndis-_ndis_miniport_adapter_registration_attributes">NDIS_MINIPORT_ADAPTER_REGISTRATION_ATTRIBUTES</a> structure and before they set any additional
    attributes.

A miniport driver can also call <b>NdisMSetMiniportAttributes</b> from its <a href="/windows-hardware/drivers/ddi/ndis/nc-ndis-miniport_add_device">MiniportAddDevice</a> function. In this case, the <a href="/windows-hardware/drivers/ddi/ndis/ns-ndis-_ndis_miniport_add_device_registration_attributes">NDIS_MINIPORT_ADD_DEVICE_REGISTRATION_ATTRIBUTES</a> structure is used to specify the context area.

## -see-also

<a href="/windows-hardware/drivers/network/initializing-a-miniport-adapter">Initializing a Miniport Adapter</a>



<a href="/windows-hardware/drivers/ddi/ndis/nc-ndis-miniport_initialize">MiniportInitializeEx</a>



<a href="/windows-hardware/drivers/ddi/ndis/ns-ndis-_ndis_miniport_adapter_attributes">
   NDIS_MINIPORT_ADAPTER_ATTRIBUTES</a>



<a href="/windows-hardware/drivers/ddi/ndis/ns-ndis-_ndis_miniport_adapter_general_attributes">
   NDIS_MINIPORT_ADAPTER_GENERAL_ATTRIBUTES</a>



<a href="/windows-hardware/drivers/ddi/ndis/ns-ndis-_ndis_miniport_adapter_hardware_assist_attributes">NDIS_MINIPORT_ADAPTER_HARDWARE_ASSIST_ATTRIBUTES</a>



<a href="/previous-versions/windows/hardware/wireless/ff565926(v=vs.85)">NDIS_MINIPORT_ADAPTER_NATIVE_802_11_ATTRIBUTES</a>



<a href="/windows-hardware/drivers/ddi/ndis/ns-ndis-_ndis_miniport_adapter_ndk_attributes">NDIS_MINIPORT_ADAPTER_NDK_ATTRIBUTES</a>



<a href="/windows-hardware/drivers/ddi/ndis/ns-ndis-_ndis_miniport_adapter_offload_attributes">NDIS_MINIPORT_ADAPTER_OFFLOAD_ATTRIBUTES</a>



<a href="/windows-hardware/drivers/ddi/ndis/ns-ndis-_ndis_miniport_adapter_registration_attributes">
   NDIS_MINIPORT_ADAPTER_REGISTRATION_ATTRIBUTES</a>



<a href="/windows-hardware/drivers/ddi/ndis/ns-ndis-_ndis_miniport_add_device_registration_attributes">NDIS_MINIPORT_ADD_DEVICE_REGISTRATION_ATTRIBUTES</a>



<a href="/windows-hardware/drivers/network/setting-the-ndis-6-0-miniport-adapter-attributes">Setting the NDIS 6.0 Miniport Adapter Attributes</a>
