---
UID: NS:ndis._NDIS_PROTOCOL_DRIVER_CHARACTERISTICS
title: _NDIS_PROTOCOL_DRIVER_CHARACTERISTICS (ndis.h)
description: To specify its driver characteristics, a protocol driver initializes an NDIS_PROTOCOL_DRIVER_CHARACTERISTICS structure and passes it to NDIS.
old-location: netvista\ndis_protocol_driver_characteristics.htm
tech.root: netvista
ms.date: 05/03/2019
keywords: ["NDIS_PROTOCOL_DRIVER_CHARACTERISTICS structure"]
ms.keywords: "*PNDIS_PROTOCOL_DRIVER_CHARACTERISTICS, NDIS_PROTOCOL_DRIVER_CHARACTERISTICS, NDIS_PROTOCOL_DRIVER_CHARACTERISTICS structure [Network Drivers Starting with Windows Vista], PNDIS_PROTOCOL_DRIVER_CHARACTERISTICS, PNDIS_PROTOCOL_DRIVER_CHARACTERISTICS structure pointer [Network Drivers Starting with Windows Vista], _NDIS_PROTOCOL_DRIVER_CHARACTERISTICS, ndis/NDIS_PROTOCOL_DRIVER_CHARACTERISTICS, ndis/PNDIS_PROTOCOL_DRIVER_CHARACTERISTICS, netvista.ndis_protocol_driver_characteristics, protocol_structures_ref_57fab3c7-f838-4a3f-a818-04d26e38cdc0.xml"
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
targetos: Windows
req.typenames: NDIS_PROTOCOL_DRIVER_CHARACTERISTICS, *PNDIS_PROTOCOL_DRIVER_CHARACTERISTICS
f1_keywords:
 - _NDIS_PROTOCOL_DRIVER_CHARACTERISTICS
 - ndis/_NDIS_PROTOCOL_DRIVER_CHARACTERISTICS
 - PNDIS_PROTOCOL_DRIVER_CHARACTERISTICS
 - ndis/PNDIS_PROTOCOL_DRIVER_CHARACTERISTICS
 - NDIS_PROTOCOL_DRIVER_CHARACTERISTICS
 - ndis/NDIS_PROTOCOL_DRIVER_CHARACTERISTICS
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - ndis.h
api_name:
 - _NDIS_PROTOCOL_DRIVER_CHARACTERISTICS
 - PNDIS_PROTOCOL_DRIVER_CHARACTERISTICS
 - NDIS_PROTOCOL_DRIVER_CHARACTERISTICS
---

# _NDIS_PROTOCOL_DRIVER_CHARACTERISTICS structure


## -description

To specify its driver characteristics, a protocol driver initializes an
  <b>NDIS_PROTOCOL_DRIVER_CHARACTERISTICS</b> structure and passes it to NDIS.

## -struct-fields

### -field Header

The 
     <a href="/windows-hardware/drivers/ddi/ntddndis/ns-ntddndis-_ndis_object_header">NDIS_OBJECT_HEADER</a> structure for the
     <b>NDIS_PROTOCOL_DRIVER_CHARACTERISTICS</b> structure. Set the 
     <b>Type</b> member of the structure that 
     <b>Header</b> specifies to NDIS_OBJECT_TYPE_PROTOCOL_DRIVER_CHARACTERISTICS.
     

To indicate the version of the <b>NDIS_PROTOCOL_DRIVER_CHARACTERISTICS</b> structure, set the 
     <b>Revision</b> member to one of the following values:





#### NDIS_PROTOCOL_DRIVER_CHARACTERISTICS_REVISION_2

Added the 
        <b>DirectOidRequestCompleteHandler</b> member for NDIS 6.1.

Set the 
        <b>Size</b> member to
        NDIS_SIZEOF_PROTOCOL_DRIVER_CHARACTERISTICS_REVISION_2.



#### NDIS_PROTOCOL_DRIVER_CHARACTERISTICS_REVISION_1

Original version for NDIS 6.0.

Set the 
        <b>Size</b> member to
        NDIS_SIZEOF_PROTOCOL_DRIVER_CHARACTERISTICS_REVISION_1.

### -field MajorNdisVersion

The major version of the NDIS library the protocol driver is using. The current value is
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

Reserved for the major version number of the protocol driver. Protocol drivers can specify any
     value that they require.

### -field MinorDriverVersion

Reserved for the minor version number of the protocol driver. Protocol drivers can specify any
     value that they require.

### -field Flags

Reserved for NDIS. Protocol drivers should set this member to zero.

### -field Name

A Unicode string that is the service name of the protocol driver.

### -field SetOptionsHandler

The entry point for the 
     <a href="/windows-hardware/drivers/ddi/ndis/nc-ndis-set_options">ProtocolSetOptions</a> function.

### -field BindAdapterHandlerEx

The entry point for the 
     <a href="/windows-hardware/drivers/ddi/ndis/nc-ndis-protocol_bind_adapter_ex">
     ProtocolBindAdapterEx</a> function.

### -field UnbindAdapterHandlerEx

The entry point for the 
     <a href="/windows-hardware/drivers/ddi/ndis/nc-ndis-protocol_unbind_adapter_ex">
     ProtocolUnbindAdapterEx</a> function.

### -field OpenAdapterCompleteHandlerEx

The entry point for the 
     <a href="/windows-hardware/drivers/ddi/ndis/nc-ndis-protocol_open_adapter_complete_ex">
     ProtocolOpenAdapterCompleteEx</a> function.

### -field CloseAdapterCompleteHandlerEx

The entry point for the 
     <a href="/windows-hardware/drivers/ddi/ndis/nc-ndis-protocol_close_adapter_complete_ex">
     ProtocolCloseAdapterCompleteEx</a> function.

### -field NetPnPEventHandler

The entry point of the caller's 
     <a href="/windows-hardware/drivers/ddi/ndis/nc-ndis-protocol_net_pnp_event">ProtocolNetPnPEvent</a> function.

### -field UninstallHandler

The entry point of the caller's 
     <a href="/windows-hardware/drivers/ddi/ndis/nc-ndis-protocol_uninstall">ProtocolUninstall</a> function, if any,
     or <b>NULL</b>.

### -field OidRequestCompleteHandler

The entry point of the caller's 
     <a href="/windows-hardware/drivers/ddi/ndis/nc-ndis-protocol_oid_request_complete">
     ProtocolOidRequestComplete</a> function.

### -field StatusHandlerEx

The entry point of the caller's 
     <a href="/windows-hardware/drivers/ddi/ndis/nc-ndis-protocol_status_ex">ProtocolStatusEx</a> function, if any, or
     <b>NULL</b>.

### -field ReceiveNetBufferListsHandler

The entry point for the 
     <a href="/windows-hardware/drivers/ddi/ndis/nc-ndis-protocol_receive_net_buffer_lists">
     ProtocolReceiveNetBufferLists</a> function.

### -field SendNetBufferListsCompleteHandler

The entry point for the 
     <a href="/windows-hardware/drivers/ddi/ndis/nc-ndis-protocol_send_net_buffer_lists_complete">
     ProtocolSendNetBufferListsComplete</a> function.

### -field DirectOidRequestCompleteHandler

The entry point of the caller's 
      <a href="/windows-hardware/drivers/ddi/ndis/nc-ndis-protocol_direct_oid_request_complete">
      ProtocolDirectOidRequestComplete</a> function. This is an optional function. Set this entry point to
      <b>NULL</b> if the protocol driver does not support the direct OID request interface.

## -remarks

A protocol driver calls the 
    <a href="/windows-hardware/drivers/ddi/ndis/nf-ndis-ndisregisterprotocoldriver">
    NdisRegisterProtocolDriver</a> function to register its characteristics, including the default entry
    points for its protocol driver functions (<i>ProtocolXxx</i>). The protocol driver initializes an <b>NDIS_PROTOCOL_DRIVER_CHARACTERISTICS</b> structure
    and passes a pointer to this structure in the 
    <i>ProtocolCharacteristics</i> parameter of 
    <b>NdisRegisterProtocolDriver</b>.

## -see-also

<a href="/windows-hardware/drivers/ddi/ndis/nf-ndis-ndisregisterprotocoldriver">NdisRegisterProtocolDriver</a>



<a href="/windows-hardware/drivers/ddi/ndis/nc-ndis-protocol_bind_adapter_ex">ProtocolBindAdapterEx</a>



<a href="/windows-hardware/drivers/ddi/ndis/nc-ndis-protocol_close_adapter_complete_ex">
   ProtocolCloseAdapterCompleteEx</a>



<a href="/windows-hardware/drivers/ddi/ndis/nc-ndis-protocol_direct_oid_request_complete">
   ProtocolDirectOidRequestComplete</a>



<a href="/windows-hardware/drivers/ddi/ndis/nc-ndis-protocol_net_pnp_event">ProtocolNetPnPEvent</a>



<a href="/windows-hardware/drivers/ddi/ndis/nc-ndis-protocol_oid_request_complete">ProtocolOidRequestComplete</a>



<a href="/windows-hardware/drivers/ddi/ndis/nc-ndis-protocol_open_adapter_complete_ex">
   ProtocolOpenAdapterCompleteEx</a>



<a href="/windows-hardware/drivers/ddi/ndis/nc-ndis-protocol_receive_net_buffer_lists">
   ProtocolReceiveNetBufferLists</a>



<a href="/windows-hardware/drivers/ddi/ndis/nc-ndis-protocol_send_net_buffer_lists_complete">
   ProtocolSendNetBufferListsComplete</a>



<a href="/windows-hardware/drivers/ddi/ndis/nc-ndis-set_options">ProtocolSetOptions</a>



<a href="/windows-hardware/drivers/ddi/ndis/nc-ndis-protocol_status_ex">ProtocolStatusEx</a>



<a href="/windows-hardware/drivers/ddi/ndis/nc-ndis-protocol_unbind_adapter_ex">ProtocolUnbindAdapterEx</a>



<a href="/windows-hardware/drivers/ddi/ndis/nc-ndis-protocol_uninstall">ProtocolUninstall</a>

