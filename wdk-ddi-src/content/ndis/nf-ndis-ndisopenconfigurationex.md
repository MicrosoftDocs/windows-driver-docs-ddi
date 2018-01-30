---
UID: NF:ndis.NdisOpenConfigurationEx
title: NdisOpenConfigurationEx function
author: windows-driver-content
description: NDIS drivers call the NdisOpenConfigurationEx function to get a configuration handle that allows access to configuration parameters in the registry.
old-location: netvista\ndisopenconfigurationex.htm
old-project: netvista
ms.assetid: 76539106-6d8d-4a80-9c74-a6a4ca37c40e
ms.author: windowsdriverdev
ms.date: 1/18/2018
ms.keywords: ndis_configuration_ref_c1d84b46-85f5-4a0a-9a5f-d553fea94027.xml, ndis/NdisOpenConfigurationEx, netvista.ndisopenconfigurationex, NdisOpenConfigurationEx function [Network Drivers Starting with Windows Vista], NdisOpenConfigurationEx
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	LibDef
apilocation:
-	ndis.lib
-	ndis.dll
apiname:
-	NdisOpenConfigurationEx
product: Windows
targetos: Windows
req.typenames: NDIS_SHARED_MEMORY_USAGE, *PNDIS_SHARED_MEMORY_USAGE
---

# NdisOpenConfigurationEx function


## -description


NDIS drivers call the 
  <b>NdisOpenConfigurationEx</b> function to get a configuration handle that allows access to configuration
  parameters in the registry.


## -syntax


````
NDIS_STATUS NdisOpenConfigurationEx(
  _In_  PNDIS_CONFIGURATION_OBJECT ConfigObject,
  _Out_ PNDIS_HANDLE               ConfigurationHandle
);
````


## -parameters




### -param ConfigObject [in]

A pointer to a caller-supplied and initialized 
     <mshelp:link keywords="netvista.ndis_configuration_object" tabindex="0"><b>
     NDIS_CONFIGURATION_OBJECT</b></mshelp:link> structure.


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


<a href="..\ndis\nf-ndis-ndisreadconfiguration.md">NdisReadConfiguration</a>



<a href="..\ndis\nf-ndis-ndiswriteconfiguration.md">NdisWriteConfiguration</a>



<mshelp:link keywords="netvista.ndisopenconfigurationkeybyname" tabindex="0"><b>
       NdisOpenConfigurationKeyByName</b></mshelp:link>



<mshelp:link keywords="netvista.ndisopenconfigurationkeybyindex" tabindex="0"><b>
       NdisOpenConfigurationKeyByIndex</b></mshelp:link>


The type of registry data that is associated with the configuration handle depends on the type of
    handle that the caller passes to 
    <b>NdisOpenConfigurationEx</b> in the 
    <b>NdisHandle</b> member of the 
    <mshelp:link keywords="netvista.ndis_configuration_object" tabindex="0"><b>
    NDIS_CONFIGURATION_OBJECT</b></mshelp:link> structure that is referenced by the 
    <i>ConfigObject</i> parameter. The handle can identify parameters that are associated with the driver or
    with an instance of the driver.

If the driver obtained the handle in 
    <b>NdisHandle</b> by calling the 
    <mshelp:link keywords="netvista.ndismregisterminiportdriver" tabindex="0"><b>
    NdisMRegisterMiniportDriver</b></mshelp:link> function, 
    <b>NdisOpenConfigurationEx</b> provides a handle to the registry location where the miniport driver's
    configuration parameters are stored. The miniport driver can use the configuration handle until it calls
    the 
    <mshelp:link keywords="netvista.ndismderegisterminiportdriver" tabindex="0"><b>
    NdisMDeregisterMiniportDriver</b></mshelp:link> function.

If the driver obtained the handle in 
    <b>NdisHandle</b> from the 
    <i>MiniportAdapterHandle</i> parameter of the 
    <a href="..\ndis\nc-ndis-miniport_initialize.md">MiniportInitializeEx</a> function, 
    <b>NdisOpenConfigurationEx</b> provides a handle to the registry location where a miniport adapter's
    configuration parameters are stored. A miniport driver can pass the configuration handle to the 
    <a href="..\ndis\nf-ndis-ndisreadnetworkaddress.md">NdisReadNetworkAddress</a> function to
    retrieve network address information that can be configured by software and administered locally.
    Miniport drivers can use the configuration handle until NDIS halts the miniport adapter and the 
    <a href="..\ndis\nc-ndis-miniport_halt.md">MiniportHaltEx</a> function returns.

If the driver obtained the handle in 
    <b>NdisHandle</b> by calling the 
    <mshelp:link keywords="netvista.ndisregisterprotocoldriver" tabindex="0"><b>
    NdisRegisterProtocolDriver</b></mshelp:link> function, 
    <b>NdisOpenConfigurationEx</b> provides a handle to the registry location where the protocol driver's
    configuration parameters are stored. The protocol driver can use the configuration handle until it calls
    the 
    <mshelp:link keywords="netvista.ndisderegisterprotocoldriver" tabindex="0"><b>
    NdisDeregisterProtocolDriver</b></mshelp:link> function.

If the handle in 
    <b>NdisHandle</b> is a pointer to an 
    <a href="..\ndis\ns-ndis-_ndis_bind_parameters.md">NDIS_BIND_PARAMETERS</a> structure that
    NDIS passed at the 
    <i>BindParameters</i> parameter of the 
    <a href="..\ndis\nc-ndis-protocol_bind_adapter_ex.md">ProtocolBindAdapterEx</a> function, 
    <b>NdisOpenConfigurationEx</b> provides a handle to the registry location where configuration parameters
    for a protocol binding are stored. Protocol drivers can use the configuration handle until the bind
    operation is complete.

If the driver obtained the handle in 
    <b>NdisHandle</b> by calling the 
    <a href="..\ndis\nf-ndis-ndisopenadapterex.md">NdisOpenAdapterEx</a> function, 
    <b>NdisOpenConfigurationEx</b> provides a handle to the registry location where the configuration
    parameters for a protocol binding are stored. The protocol driver can use the configuration handle until
    it calls the 
    <a href="..\ndis\nf-ndis-ndiscloseadapterex.md">NdisCloseAdapterEx</a> function.

If a filter driver obtained the handle in 
    <b>NdisHandle</b> by calling the 
    <mshelp:link keywords="netvista.ndisfregisterfilterdriver" tabindex="0"><b>
    NdisFRegisterFilterDriver</b></mshelp:link> function, 
    <b>NdisOpenConfigurationEx</b> provides a handle to the registry location where the filter driver's
    configuration parameters are stored. Filter drivers can use the configuration handle until they call the 
    <mshelp:link keywords="netvista.ndisfderegisterfilterdriver" tabindex="0"><b>
    NdisFDeregisterFilterDriver</b></mshelp:link> function.

If a filter driver obtained the handle in 
    <b>NdisHandle</b> from the 
    <i>NdisFilterHandle</i> parameter of the 
    <a href="..\ndis\nc-ndis-filter_attach.md">FilterAttach</a> function, 
    <b>NdisOpenConfigurationEx</b> provides a handle to the registry location where a filter modules
    configuration parameters are stored. The filter driver can use the configuration handle until NDIS
    detaches the filter module and the 
    <a href="..\ndis\nc-ndis-filter_detach.md">FilterDetach</a> function returns. If a
    monitoring filter driver specifies the NDIS_CONFIG_FLAG_FILTER_INSTANCE_CONFIGURATION flag in the 
    <b>Flags</b> member of the 
    <mshelp:link keywords="netvista.ndis_configuration_object" tabindex="0"><b>
    NDIS_CONFIGURATION_OBJECT</b></mshelp:link> structure, the driver can access the filter module configuration for a
    specific filter module when there are multiple filter modules configured over the same miniport adapter.
    Modifying filter drivers must not use this flag.

After a driver is done accessing the configuration information, the driver must call the 
    <a href="..\ndis\nf-ndis-ndiscloseconfiguration.md">NdisCloseConfiguration</a> function to
    release the configuration handle and related resources.
<div class="alert"><b>Note</b>  To be sure that this function runs at IRQL = PASSIVE_LEVEL, a driver can schedule
    an NDIS work item and call this and other configuration functions in the context of the work item
    callback.</div><div> </div>


## -see-also

<mshelp:link keywords="netvista.ndismderegisterminiportdriver" tabindex="0"><b>
   NdisMDeregisterMiniportDriver</b></mshelp:link>

<a href="..\ndis\nf-ndis-ndisfregisterfilterdriver.md">NdisFRegisterFilterDriver</a>

<a href="..\ndis\nf-ndis-ndisreadconfiguration.md">NdisReadConfiguration</a>

<a href="..\ndis\nc-ndis-filter_attach.md">FilterAttach</a>

<a href="..\ndis\nf-ndis-ndisfderegisterfilterdriver.md">NdisFDeregisterFilterDriver</a>

<mshelp:link keywords="netvista.ndisopenconfigurationkeybyindex" tabindex="0"><b>
   NdisOpenConfigurationKeyByIndex</b></mshelp:link>

<a href="..\ndis\nc-ndis-protocol_bind_adapter_ex.md">ProtocolBindAdapterEx</a>

<a href="..\ndis\ns-ndis-_ndis_configuration_object.md">NDIS_CONFIGURATION_OBJECT</a>

<a href="..\ndis\nc-ndis-filter_detach.md">FilterDetach</a>

<a href="..\ndis\nf-ndis-ndisregisterprotocoldriver.md">NdisRegisterProtocolDriver</a>

<a href="..\ndis\nf-ndis-ndisreadnetworkaddress.md">NdisReadNetworkAddress</a>

<a href="..\ndis\nc-ndis-miniport_initialize.md">MiniportInitializeEx</a>

<a href="..\ndis\nf-ndis-ndisopenadapterex.md">NdisOpenAdapterEx</a>

<a href="..\ndis\ns-ndis-_ndis_bind_parameters.md">NDIS_BIND_PARAMETERS</a>

<a href="..\ndis\nf-ndis-ndiscloseconfiguration.md">NdisCloseConfiguration</a>

<a href="..\ndis\nf-ndis-ndiswriteconfiguration.md">NdisWriteConfiguration</a>

<a href="..\ndis\nf-ndis-ndisderegisterprotocoldriver.md">NdisDeregisterProtocolDriver</a>

<a href="..\ndis\nf-ndis-ndiscloseadapterex.md">NdisCloseAdapterEx</a>

<mshelp:link keywords="netvista.ndisopenconfigurationkeybyname" tabindex="0"><b>
   NdisOpenConfigurationKeyByName</b></mshelp:link>

<a href="..\ndis\nf-ndis-ndismregisterminiportdriver.md">NdisMRegisterMiniportDriver</a>

<a href="..\ndis\nc-ndis-miniport_halt.md">MiniportHaltEx</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20NdisOpenConfigurationEx function%20 RELEASE:%20(1/18/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

