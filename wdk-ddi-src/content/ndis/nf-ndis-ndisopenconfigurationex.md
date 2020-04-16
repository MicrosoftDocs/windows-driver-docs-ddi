---
UID: NF:ndis.NdisOpenConfigurationEx
title: NdisOpenConfigurationEx function (ndis.h)
description: NDIS drivers call the NdisOpenConfigurationEx function to get a configuration handle that allows access to configuration parameters in the registry.
old-location: netvista\ndisopenconfigurationex.htm
tech.root: netvista
ms.assetid: 76539106-6d8d-4a80-9c74-a6a4ca37c40e
ms.date: 05/02/2018
keywords: ["NdisOpenConfigurationEx function"]
ms.keywords: NdisOpenConfigurationEx, NdisOpenConfigurationEx function [Network Drivers Starting with Windows Vista], ndis/NdisOpenConfigurationEx, ndis_configuration_ref_c1d84b46-85f5-4a0a-9a5f-d553fea94027.xml, netvista.ndisopenconfigurationex
f1_keywords:
 - "ndis/NdisOpenConfigurationEx"
req.header: ndis.h
req.include-header: Ndis.h
req.target-type: Universal
req.target-min-winverclnt: Supported in NDIS 6.0 and later.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: Irql_Miscellaneous_Function, NdisOpenConfigurationEx
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
- NdisOpenConfigurationEx
product:
- Windows
targetos: Windows
req.typenames: 
---

# NdisOpenConfigurationEx function


## -description


NDIS drivers call the 
  <b>NdisOpenConfigurationEx</b> function to get a configuration handle that allows access to configuration
  parameters in the registry.


## -parameters




### -param ConfigObject [in]

A pointer to a caller-supplied and initialized 
     <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/ns-ndis-_ndis_configuration_object">
     NDIS_CONFIGURATION_OBJECT</a> structure.


### -param ConfigurationHandle [out]

A pointer to a caller-supplied variable in which 
     <b>NdisOpenConfigurationEx</b> returns a handle to a registry key. The registry key identifies the
     configuration parameters.


## -returns



<b>NdisOpenConfigurationEx</b> returns one of the following status values:

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
<b>NdisOpenConfigurationEx</b> successfully opened the registry key where the driver's configuration
       parameters are stored.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>NDIS_STATUS_RESOURCES</b></dt>
</dl>
</td>
<td width="60%">
<b>NdisOpenConfigurationEx</b> failed due to insufficient resources.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>NDIS_STATUS_FAILURE</b></dt>
</dl>
</td>
<td width="60%">
<b>NdisOpenConfigurationEx</b> returns NDIS_STATUS_FAILURE if none of the preceding values
       applies.

</td>
</tr>
</table>
 




## -remarks



<b>NdisOpenConfigurationEx</b> returns a configuration handle at the 
    <i>ConfigurationHandle</i> parameter. The configuration handle is associated with a registry key that
    identifies the location of the configuration parameters. The caller can pass the configuration handle to
    other NDIS configuration functions to read or write information in the registry.

To access the configuration information, use the configuration handle with the following
    functions:


<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nf-ndis-ndisreadconfiguration">NdisReadConfiguration</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nf-ndis-ndiswriteconfiguration">NdisWriteConfiguration</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nf-ndis-ndisopenconfigurationkeybyname">
       NdisOpenConfigurationKeyByName</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nf-ndis-ndisopenconfigurationkeybyindex">
       NdisOpenConfigurationKeyByIndex</a>


The type of registry data that is associated with the configuration handle depends on the type of
    handle that the caller passes to 
    <b>NdisOpenConfigurationEx</b> in the 
    <b>NdisHandle</b> member of the 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/ns-ndis-_ndis_configuration_object">
    NDIS_CONFIGURATION_OBJECT</a> structure that is referenced by the 
    <i>ConfigObject</i> parameter. The handle can identify parameters that are associated with the driver or
    with an instance of the driver.

If the driver obtained the handle in 
    <b>NdisHandle</b> by calling the 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nf-ndis-ndismregisterminiportdriver">
    NdisMRegisterMiniportDriver</a> function, 
    <b>NdisOpenConfigurationEx</b> provides a handle to the registry location where the miniport driver's
    configuration parameters are stored. The miniport driver can use the configuration handle until it calls
    the 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nf-ndis-ndismderegisterminiportdriver">
    NdisMDeregisterMiniportDriver</a> function.

If the driver obtained the handle in 
    <b>NdisHandle</b> from the 
    <i>MiniportAdapterHandle</i> parameter of the 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nc-ndis-miniport_initialize">MiniportInitializeEx</a> function, 
    <b>NdisOpenConfigurationEx</b> provides a handle to the registry location where a miniport adapter's
    configuration parameters are stored. A miniport driver can pass the configuration handle to the 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nf-ndis-ndisreadnetworkaddress">NdisReadNetworkAddress</a> function to
    retrieve network address information that can be configured by software and administered locally.
    Miniport drivers can use the configuration handle until NDIS halts the miniport adapter and the 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nc-ndis-miniport_halt">MiniportHaltEx</a> function returns.

If the driver obtained the handle in 
    <b>NdisHandle</b> by calling the 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nf-ndis-ndisregisterprotocoldriver">
    NdisRegisterProtocolDriver</a> function, 
    <b>NdisOpenConfigurationEx</b> provides a handle to the registry location where the protocol driver's
    configuration parameters are stored. The protocol driver can use the configuration handle until it calls
    the 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nf-ndis-ndisderegisterprotocoldriver">
    NdisDeregisterProtocolDriver</a> function.

If the handle in 
    <b>NdisHandle</b> is a pointer to an 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/ns-ndis-_ndis_bind_parameters">NDIS_BIND_PARAMETERS</a> structure that
    NDIS passed at the 
    <i>BindParameters</i> parameter of the 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nc-ndis-protocol_bind_adapter_ex">ProtocolBindAdapterEx</a> function, 
    <b>NdisOpenConfigurationEx</b> provides a handle to the registry location where configuration parameters
    for a protocol binding are stored. Protocol drivers can use the configuration handle until the bind
    operation is complete.

If the driver obtained the handle in 
    <b>NdisHandle</b> by calling the 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nf-ndis-ndisopenadapterex">NdisOpenAdapterEx</a> function, 
    <b>NdisOpenConfigurationEx</b> provides a handle to the registry location where the configuration
    parameters for a protocol binding are stored. The protocol driver can use the configuration handle until
    it calls the 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nf-ndis-ndiscloseadapterex">NdisCloseAdapterEx</a> function.

If a filter driver obtained the handle in 
    <b>NdisHandle</b> by calling the 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nf-ndis-ndisfregisterfilterdriver">
    NdisFRegisterFilterDriver</a> function, 
    <b>NdisOpenConfigurationEx</b> provides a handle to the registry location where the filter driver's
    configuration parameters are stored. Filter drivers can use the configuration handle until they call the 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nf-ndis-ndisfderegisterfilterdriver">
    NdisFDeregisterFilterDriver</a> function.

If a filter driver obtained the handle in 
    <b>NdisHandle</b> from the 
    <i>NdisFilterHandle</i> parameter of the 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nc-ndis-filter_attach">FilterAttach</a> function, 
    <b>NdisOpenConfigurationEx</b> provides a handle to the registry location where a filter modules
    configuration parameters are stored. The filter driver can use the configuration handle until NDIS
    detaches the filter module and the 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nc-ndis-filter_detach">FilterDetach</a> function returns. If a
    monitoring filter driver specifies the NDIS_CONFIG_FLAG_FILTER_INSTANCE_CONFIGURATION flag in the 
    <b>Flags</b> member of the 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/ns-ndis-_ndis_configuration_object">
    NDIS_CONFIGURATION_OBJECT</a> structure, the driver can access the filter module configuration for a
    specific filter module when there are multiple filter modules configured over the same miniport adapter.
    Modifying filter drivers must not use this flag.

After a driver is done accessing the configuration information, the driver must call the 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nf-ndis-ndiscloseconfiguration">NdisCloseConfiguration</a> function to
    release the configuration handle and related resources.

<div class="alert"><b>Note</b>  To be sure that this function runs at IRQL = PASSIVE_LEVEL, a driver can schedule
    an NDIS work item and call this and other configuration functions in the context of the work item
    callback.</div>
<div> </div>



## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nc-ndis-filter_attach">FilterAttach</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nc-ndis-filter_detach">FilterDetach</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nc-ndis-miniport_halt">MiniportHaltEx</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nc-ndis-miniport_initialize">MiniportInitializeEx</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/ns-ndis-_ndis_bind_parameters">NDIS_BIND_PARAMETERS</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/ns-ndis-_ndis_configuration_object">NDIS_CONFIGURATION_OBJECT</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nf-ndis-ndiscloseadapterex">NdisCloseAdapterEx</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nf-ndis-ndiscloseconfiguration">NdisCloseConfiguration</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nf-ndis-ndisderegisterprotocoldriver">NdisDeregisterProtocolDriver</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nf-ndis-ndisfderegisterfilterdriver">NdisFDeregisterFilterDriver</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nf-ndis-ndisfregisterfilterdriver">NdisFRegisterFilterDriver</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nf-ndis-ndismderegisterminiportdriver">
   NdisMDeregisterMiniportDriver</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nf-ndis-ndismregisterminiportdriver">NdisMRegisterMiniportDriver</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nf-ndis-ndisopenadapterex">NdisOpenAdapterEx</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nf-ndis-ndisopenconfigurationkeybyindex">
   NdisOpenConfigurationKeyByIndex</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nf-ndis-ndisopenconfigurationkeybyname">
   NdisOpenConfigurationKeyByName</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nf-ndis-ndisreadconfiguration">NdisReadConfiguration</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nf-ndis-ndisreadnetworkaddress">NdisReadNetworkAddress</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nf-ndis-ndisregisterprotocoldriver">NdisRegisterProtocolDriver</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nf-ndis-ndiswriteconfiguration">NdisWriteConfiguration</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nc-ndis-protocol_bind_adapter_ex">ProtocolBindAdapterEx</a>
 

 

