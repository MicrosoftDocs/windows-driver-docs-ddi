---
UID: NS:ndis._NDIS_FILTER_DRIVER_CHARACTERISTICS
title: _NDIS_FILTER_DRIVER_CHARACTERISTICS (ndis.h)
description: To specify its driver characteristics, a filter driver initializes an NDIS_FILTER_DRIVER_CHARACTERISTICS structure and passes it to NDIS.
old-location: netvista\ndis_filter_driver_characteristics.htm
tech.root: netvista
ms.assetid: 1eb2bae0-70b9-4bc0-9d93-4fc9467f9532
ms.date: 05/03/2019
ms.keywords: "*PNDIS_FILTER_DRIVER_CHARACTERISTICS, NDIS_FILTER_DRIVER_CHARACTERISTICS, NDIS_FILTER_DRIVER_CHARACTERISTICS structure [Network Drivers Starting with Windows Vista], PNDIS_FILTER_DRIVER_CHARACTERISTICS, PNDIS_FILTER_DRIVER_CHARACTERISTICS structure pointer [Network Drivers Starting with Windows Vista], _NDIS_FILTER_DRIVER_CHARACTERISTICS, filter_structures_ref_8fc4ed95-82fe-47bd-849d-f9733647cacd.xml, ndis/NDIS_FILTER_DRIVER_CHARACTERISTICS, ndis/PNDIS_FILTER_DRIVER_CHARACTERISTICS, netvista.ndis_filter_driver_characteristics"
f1_keywords:
 - "ndis/NDIS_FILTER_DRIVER_CHARACTERISTICS"
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
req.irql: 
topic_type:
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- ndis.h
api_name:
- NDIS_FILTER_DRIVER_CHARACTERISTICS
product:
- Windows
targetos: Windows
req.typenames: NDIS_FILTER_DRIVER_CHARACTERISTICS, *PNDIS_FILTER_DRIVER_CHARACTERISTICS
---

# _NDIS_FILTER_DRIVER_CHARACTERISTICS structure


## -description


To specify its driver characteristics, a filter driver initializes an
  NDIS_FILTER_DRIVER_CHARACTERISTICS structure and passes it to NDIS.


## -struct-fields




### -field Header

The 
     <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddndis/ns-ntddndis-_ndis_object_header">NDIS_OBJECT_HEADER</a> structure for the
     filter driver characteristics structure (NDIS_FILTER_DRIVER_CHARACTERISTICS). Set the 
     <b>Type</b> member of the structure that 
     <b>Header</b> specifies to NDIS_OBJECT_TYPE_FILTER_DRIVER_CHARACTERISTICS.
     

To indicate the version of the NDIS_FILTER_DRIVER_CHARACTERISTICS structure, set the 
     <b>Revision</b> member to one of the following values:





#### NDIS_FILTER_CHARACTERISTICS_REVISION_3

Added the 
        <b>SynchronousOidRequestHandler</b> and <b>SynchronousOidRequestHandlerComplete</b> members for NDIS 6.80.

Set the 
        <b>Size</b> member to NDIS_SIZEOF_FILTER_DRIVER_CHARACTERISTICS_REVISION_3.



#### NDIS_FILTER_CHARACTERISTICS_REVISION_2

Added the 
        <b>DirectOidRequestHandler</b>, 
        <b>DirectOidRequestCompleteHandler</b>, and 
        <b>CancelDirectOidRequestHandler</b> members for NDIS 6.1.

Set the 
        <b>Size</b> member to NDIS_SIZEOF_FILTER_DRIVER_CHARACTERISTICS_REVISION_2.



#### NDIS_FILTER_CHARACTERISTICS_REVISION_1

Original version.

Set the 
        <b>Size</b> member to NDIS_SIZEOF_FILTER_DRIVER_CHARACTERISTICS_REVISION_1.


### -field MajorNdisVersion

The major version of NDIS that the driver is using. The current value is
     0x06.


### -field MinorNdisVersion

The minor NDIS version. The following are the available minor version value settings.

<table>
<tr>
<th>Value</th>
<th>Meaning</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt>0</dt>
</dl>
</td>
<td width="60%">
NDIS 6

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt>20</dt>
</dl>
</td>
<td width="60%">
NDIS 6.20

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt>30</dt>
</dl>
</td>
<td width="60%">
NDIS 6.30

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt>40</dt>
</dl>
</td>
<td width="60%">
NDIS 6.40

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt>50</dt>
</dl>
</td>
<td width="60%">
NDIS 6.50

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt>51</dt>
</dl>
</td>
<td width="60%">
NDIS 6.51

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt>60</dt>
</dl>
</td>
<td width="60%">
NDIS 6.60

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt>70</dt>
</dl>
</td>
<td width="60%">
NDIS 6.70

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt>80</dt>
</dl>
</td>
<td width="60%">
NDIS 6.80

</td>
</tr>

<tr>
<td width="40%">
<dl>
<dt>81</dt>
</dl>
</td>
<td width="60%">
NDIS 6.81

</td>
</tr>

<tr>
<td width="40%">
<dl>
<dt>82</dt>
</dl>
</td>
<td width="60%">
NDIS 6.82

</td>
</tr>

<tr>
<td width="40%">
<dl>
<dt>83</dt>
</dl>
</td>
<td width="60%">
NDIS 6.83

</td>
</tr>

</table>
 


### -field MajorDriverVersion

Reserved for the major version number of the filter driver. Filter drivers can specify any value
     that they require.


### -field MinorDriverVersion

Reserved for the minor version number of the filter driver. Filter drivers can specify any value
     that they require.


### -field Flags

Reserved for NDIS.


### -field FriendlyName

A Unicode string that represents the user-readable description of the filter driver.


### -field UniqueName

A Unicode string that represents the unique name for the filter driver. This string must be a GUID, enclosed in curly braces, for example "{5cbf81bd-5055-47cd-9055-a76b2b4e3697}". This GUID must match the one in the <b>NetCfgInstanceId</b> INF file entry in the filter driver's INF file. For more information, see <a href="https://docs.microsoft.com/windows-hardware/drivers/network/inf-file-settings-for-filter-drivers">INF File Settings for Filter Drivers</a>.


### -field ServiceName

A Unicode string that represents the service name of the filter driver. This string must be the service name
     from the AddService directive in the filter driver's INF file. For more information, see <a href="https://docs.microsoft.com/windows-hardware/drivers/network/inf-file-settings-for-filter-drivers">INF File Settings for Filter Drivers</a>.


### -field SetOptionsHandler

Specifies the entry point of the caller's 
     <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nc-ndis-set_options">FilterSetOptions</a> function.


### -field SetFilterModuleOptionsHandler

The entry point of the caller's 
     <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nc-ndis-filter_set_module_options">
     FilterSetModuleOptions</a> function.


### -field AttachHandler

The entry point of the caller's 
     <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nc-ndis-filter_attach">FilterAttach</a> function.


### -field DetachHandler

The entry point of the caller's 
     <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nc-ndis-filter_detach">FilterDetach</a> function.


### -field RestartHandler

The entry point of the caller's 
     <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nc-ndis-filter_restart">FilterRestart</a> function.


### -field PauseHandler

The entry point of the caller's 
     <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nc-ndis-filter_pause">FilterPause</a> function.


### -field SendNetBufferListsHandler

The entry point of the caller's 
     <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nc-ndis-filter_send_net_buffer_lists">
     FilterSendNetBufferLists</a> function. To bypass this function, set this member to <b>NULL</b>.


### -field SendNetBufferListsCompleteHandler

The entry point of the caller's 
     <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nc-ndis-filter_send_net_buffer_lists_complete">
     FilterSendNetBufferListsComplete</a> function. To bypass this function, set this member to
     <b>NULL</b>.


### -field CancelSendNetBufferListsHandler

The entry point of the caller's 
     <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nc-ndis-filter_cancel_send_net_buffer_lists">
     FilterCancelSendNetBufferLists</a> function. To bypass this function, set this member to <b>NULL</b>.


### -field ReceiveNetBufferListsHandler

The entry point of the caller's 
     <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nc-ndis-filter_receive_net_buffer_lists">
     FilterReceiveNetBufferLists</a> function. To bypass this function, set this member to <b>NULL</b>.


### -field ReturnNetBufferListsHandler

The entry point of the caller's 
     <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nc-ndis-filter_return_net_buffer_lists">
     FilterReturnNetBufferLists</a> function. To bypass this function, set this member to <b>NULL</b>.


### -field OidRequestHandler

The entry point of the caller's 
     <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nc-ndis-filter_oid_request">FilterOidRequest</a> function. To bypass
     this function, set this member to <b>NULL</b>.


### -field OidRequestCompleteHandler

The entry point of the caller's 
     <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nc-ndis-filter_oid_request_complete">
     FilterOidRequestComplete</a> function. To bypass this function, set this member to <b>NULL</b>.


### -field CancelOidRequestHandler

The entry point of the caller's 
     <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nc-ndis-filter_cancel_oid_request">
     FilterCancelOidRequest</a> function. To bypass this function, set this member to <b>NULL</b>.


### -field DevicePnPEventNotifyHandler

The entry point of the caller's 
     <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nc-ndis-filter_device_pnp_event_notify">
     FilterDevicePnPEventNotify</a> function. To bypass this function, set this member to <b>NULL</b>.


### -field NetPnPEventHandler

The entry point of the caller's 
     <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nc-ndis-filter_net_pnp_event">FilterNetPnPEvent</a> function. To
     bypass this function, set this member to <b>NULL</b>.


### -field StatusHandler

The entry point of the caller's 
     <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nc-ndis-filter_status">FilterStatus</a> function. To bypass this
     function, set this member to <b>NULL</b>.


### -field DirectOidRequestHandler

The entry point of the caller's 
      <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nc-ndis-filter_direct_oid_request">
      FilterDirectOidRequest</a> function. To bypass this function, set this member to <b>NULL</b>.


### -field DirectOidRequestCompleteHandler

The entry point of the caller's 
      <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nc-ndis-filter_direct_oid_request_complete">
      FilterDirectOidRequestComplete</a> function. To bypass this function, set this member to <b>NULL</b>.


### -field CancelDirectOidRequestHandler

The entry point of the caller's 
      <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nc-ndis-filter_cancel_direct_oid_request">
      FilterCancelDirectOidRequest</a> function. To bypass this function, set this member to <b>NULL</b>.


### -field SynchronousOidRequestHandler

The entry point of the caller's [*FilterSynchronousOidRequest*](nf-ndis-filter_synchronous_oid_request.md) function. To bypass this function, set this member to **NULL**.

### -field SynchronousOidRequestCompleteHandler

The entry point of the caller's [*FilterSynchronousOidRequestComplete*](nf-ndis-filter_synchronous_oid_request_complete.md) function. To bypass this function, set this member to **NULL**.

## -remarks



A filter driver calls the 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nf-ndis-ndisfregisterfilterdriver">
    NdisFRegisterFilterDriver</a> function to register its characteristics, including the default entry
    points for its filter driver functions (<i>FilterXxx</i>). The filter driver initializes an NDIS_FILTER_DRIVER_CHARACTERISTICS structure and
    passes a pointer to this structure in the 
    <i>FilterCharacteristics</i> parameter of 
    <b>NdisFRegisterFilterDriver</b>.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nc-ndis-filter_attach">FilterAttach</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nc-ndis-filter_cancel_direct_oid_request">
   FilterCancelDirectOidRequest</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nc-ndis-filter_cancel_oid_request">FilterCancelOidRequest</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nc-ndis-filter_cancel_send_net_buffer_lists">
   FilterCancelSendNetBufferLists</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nc-ndis-filter_detach">FilterDetach</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nc-ndis-filter_device_pnp_event_notify">FilterDevicePnPEventNotify</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nc-ndis-filter_direct_oid_request">FilterDirectOidRequest</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nc-ndis-filter_direct_oid_request_complete">
   FilterDirectOidRequestComplete</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nc-ndis-filter_net_pnp_event">FilterNetPnPEvent</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nc-ndis-filter_oid_request">FilterOidRequest</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nc-ndis-filter_oid_request_complete">FilterOidRequestComplete</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nc-ndis-filter_pause">FilterPause</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nc-ndis-filter_receive_net_buffer_lists">FilterReceiveNetBufferLists</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nc-ndis-filter_restart">FilterRestart</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nc-ndis-filter_return_net_buffer_lists">FilterReturnNetBufferLists</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nc-ndis-filter_send_net_buffer_lists">FilterSendNetBufferLists</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nc-ndis-filter_send_net_buffer_lists_complete">
   FilterSendNetBufferListsComplete</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nc-ndis-filter_set_module_options">FilterSetModuleOptions</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nc-ndis-set_options">FilterSetOptions</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nc-ndis-filter_status">FilterStatus</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/network/inf-file-settings-for-filter-drivers">INF File Settings for Filter Drivers</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/network/initializing-a-filter-driver">Initializing a Filter Driver</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/ns-ndis-_ndis_filter_partial_characteristics">
   NDIS_FILTER_PARTIAL_CHARACTERISTICS</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddndis/ns-ntddndis-_ndis_object_header">NDIS_OBJECT_HEADER</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nf-ndis-ndisfregisterfilterdriver">NdisFRegisterFilterDriver</a>
 

 

