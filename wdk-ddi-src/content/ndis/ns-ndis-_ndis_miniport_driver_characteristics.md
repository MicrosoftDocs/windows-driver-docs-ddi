---
UID: NS:ndis._NDIS_MINIPORT_DRIVER_CHARACTERISTICS
title: _NDIS_MINIPORT_DRIVER_CHARACTERISTICS (ndis.h)
description: An NDIS driver initializes an NDIS_MINIPORT_DRIVER_CHARACTERISTICS structure to define its miniport driver characteristics, including the entry points for its MiniportXxx functions.
old-location: netvista\ndis_miniport_driver_characteristics.htm
tech.root: netvista
ms.assetid: 2e2c8522-127d-49d5-a5d6-97f9403bec89
ms.date: 05/03/2019
ms.keywords: "*PNDIS_MINIPORT_DRIVER_CHARACTERISTICS, NDIS_MINIPORT_DRIVER_CHARACTERISTICS, NDIS_MINIPORT_DRIVER_CHARACTERISTICS structure [Network Drivers Starting with Windows Vista], PNDIS_MINIPORT_DRIVER_CHARACTERISTICS, PNDIS_MINIPORT_DRIVER_CHARACTERISTICS structure pointer [Network Drivers Starting with Windows Vista], _NDIS_MINIPORT_DRIVER_CHARACTERISTICS, miniport_structures_ref_9a538743-5c3f-40c7-a83d-07d5efde350c.xml, ndis/NDIS_MINIPORT_DRIVER_CHARACTERISTICS, ndis/PNDIS_MINIPORT_DRIVER_CHARACTERISTICS, netvista.ndis_miniport_driver_characteristics"
f1_keywords:
 - "ndis/NDIS_MINIPORT_DRIVER_CHARACTERISTICS"
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
- NDIS_MINIPORT_DRIVER_CHARACTERISTICS
product:
- Windows
targetos: Windows
req.typenames: NDIS_MINIPORT_DRIVER_CHARACTERISTICS, *PNDIS_MINIPORT_DRIVER_CHARACTERISTICS
---

# _NDIS_MINIPORT_DRIVER_CHARACTERISTICS structure


## -description


An NDIS driver initializes an <b>NDIS_MINIPORT_DRIVER_CHARACTERISTICS</b> structure to define its miniport
  driver characteristics, including the entry points for its 
  <i>MiniportXxx</i> functions.


## -struct-fields




### -field Header

The 
     <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddndis/ns-ntddndis-_ndis_object_header">NDIS_OBJECT_HEADER</a> structure for the
     <b>NDIS_MINIPORT_DRIVER_CHARACTERISTICS</b> structure. Set the 
     <b>Type</b> member of the structure that 
     <b>Header</b> specifies to NDIS_OBJECT_TYPE_MINIPORT_DRIVER_CHARACTERISTICS.
     

To indicate the version of the <b>NDIS_MINIPORT_DRIVER_CHARACTERISTICS</b> structure, set the 
     <b>Revision</b> member to one of the following values:





#### NDIS_MINIPORT_DRIVER_CHARACTERISTICS_REVISION_3

Added the <b>SynchronousOidRequestHandler</b> member for NDIS 6.80.

Set the 
        <b>Size</b> member to NDIS_SIZEOF_MINIPORT_DRIVER_CHARACTERISTICS_REVISION_3.



#### NDIS_MINIPORT_DRIVER_CHARACTERISTICS_REVISION_2

Added the <b>DirectOidRequestHandler</b>, and <b>CancelDirectOidRequestHandler</b> members for NDIS 6.1.

Set the 
        <b>Size</b> member to NDIS_SIZEOF_MINIPORT_DRIVER_CHARACTERISTICS_REVISION_2.



#### NDIS_MINIPORT_DRIVER_CHARACTERISTICS_REVISION_1

Original version for NDIS 6.0.

Set the 
        <b>Size</b> member to NDIS_SIZEOF_MINIPORT_DRIVER_CHARACTERISTICS_REVISION_1.


### -field MajorNdisVersion

The major version of the NDIS library the driver is using. The current value is 0x06.


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

Reserved for the major version number of the driver. Miniport drivers can specify any value that
     they require.


### -field MinorDriverVersion

Reserved for the minor version number of the driver. Miniport drivers can specify any value that
     they require.


### -field Flags

A bitmask that can be set to zero or any of the following flags, combined with bitwise OR: 
     





#### NDIS_INTERMEDIATE_DRIVER

Set if the caller is an NDIS intermediate driver.



#### NDIS_WDM_DRIVER

Set if the caller is an NDIS-WDM miniport driver.


### -field SetOptionsHandler

The entry point for the caller's 
     <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nc-ndis-set_options">MiniportSetOptions</a> function.

Required for Co-NDIS. Suggested for Ethernet miniport drivers that support RSS using MSI-C over PCI.


### -field InitializeHandlerEx

Required. The entry point for the 
     <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nc-ndis-miniport_initialize">
     MiniportInitializeEx</a> function.


### -field HaltHandlerEx

Required. The entry point for the 
     <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nc-ndis-miniport_halt">MiniportHaltEx</a> function.


### -field UnloadHandler

Required. The entry point for the 
     <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nc-ndis-miniport_unload">
     MiniportDriverUnload</a> function.


### -field PauseHandler

Required. The entry point for the 
     <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nc-ndis-miniport_pause">MiniportPause</a> function.


### -field RestartHandler

Required. The entry point for the 
     <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nc-ndis-miniport_restart">MiniportRestart</a> function.


### -field OidRequestHandler

The entry point for the 
     <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nc-ndis-miniport_oid_request">MiniportOidRequest</a> function. Required for all connection-less miniport drivers, including all Ethernet, WLAN, and IM drivers. Optional for some CoNDIS miniport drivers.


### -field SendNetBufferListsHandler

Required. The entry point for the 
     <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nc-ndis-miniport_send_net_buffer_lists">
     MiniportSendNetBufferLists</a> function.


### -field ReturnNetBufferListsHandler

Required. The entry point for the 
     <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nc-ndis-miniport_return_net_buffer_lists">
     MiniportReturnNetBufferLists</a> function.


### -field CancelSendHandler

Required. The entry point for the 
     <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nc-ndis-miniport_cancel_send">MiniportCancelSend</a> function.


### -field CheckForHangHandlerEx

Optional. The entry point for the 
     <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nc-ndis-miniport_check_for_hang">
     MiniportCheckForHangEx</a> function. 
     

<i>MiniportCheckForHangEx</i> is not required for intermediate drivers or virtual miniports because they are not physical devices that can hang, so they must set this entry
     point to <b>NULL</b>. 

<i>MiniportCheckForHangEx</i> is forbidden on any AOAC device due to the impact on battery life, so miniport drivers for these devices must set this entry point to <b>NULL</b>.

<i>MiniportCheckForHangEx</i> is discouraged for miniport drivers intended to be installed on non-AOAC, battery-powered devices due to the impact on battery life, so they should set this entry point to <b>NULL</b>.

<i>MiniportCheckForHangEx</i> is permitted but not required for miniport drivers that are intended to be installed in line-powered (mains-powered) devices. For drivers targeting NDIS 6.30 and later, consider using <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nf-ndis-ndismresetminiport">NdisMResetMiniport</a> instead.


### -field ResetHandlerEx

Optional (required if you provide <b>CheckForHangHandlerEx</b>). The entry point for the 
     <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nc-ndis-miniport_reset">MiniportResetEx</a> function. 
     <i>MiniportResetEx</i> is not required for intermediate drivers, so they should set this entry point to
     <b>NULL</b>.


### -field DevicePnPEventNotifyHandler

Required. The entry point for the 
     <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nc-ndis-miniport_device_pnp_event_notify">
     MiniportDevicePnPEventNotify</a> function.


### -field ShutdownHandlerEx

Required. The entry point for the 
     <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nc-ndis-miniport_shutdown">MiniportShutdownEx</a> function.


### -field CancelOidRequestHandler

Required. The entry point for the 
     <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nc-ndis-miniport_cancel_oid_request">
     MiniportCancelOidRequest</a> function.


### -field DirectOidRequestHandler

The entry point for the 
      <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nc-ndis-miniport_direct_oid_request">
      MiniportDirectOidRequest</a> function. This is an optional entry point. Set this member to <b>NULL</b> if
      the miniport driver does not handle direct OID requests. 

Optional for Ethernet; however, if one is provided, then both must be provided.

Required for WLAN and Ethernet miniports that implement RDMA or IPSec offload.


### -field CancelDirectOidRequestHandler

The entry point for the 
      <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nc-ndis-miniport_cancel_direct_oid_request">
      MiniportCancelDirectOidRequest</a> function. This is an optional entry point. Set this member to <b>NULL</b>
      if the miniport driver does not handle direct OID requests.

Optional for Ethernet; however, if one is provided, then both must be provided.

Required for WLAN and Ethernet miniports that implement RDMA or IPSec offload.


### -field SynchronousOidRequestHandler

The entry point for the 
      <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nf-ndis-miniport_synchronous_oid_request">
      MiniportSynchronousOidRequest</a> function. This is an optional entry point. Set this member to <b>NULL</b> if
      the miniport driver does not handle Synchronous OID requests. 

Required for WLAN and Ethernet miniports that implement RSSv2.


## -remarks



An NDIS driver passes a pointer to its <b>NDIS_MINIPORT_DRIVER_CHARACTERISTICS</b> structure in the 
    <i>MiniportDriverCharacteristics</i> parameter of the 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nf-ndis-ndismregisterminiportdriver">
    NdisMRegisterMiniportDriver</a> function. A miniport driver calls 
    <b>NdisMRegisterMiniportDriver</b> from its 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/storage/driverentry-of-ide-controller-minidriver">DriverEntry</a> routine (see also 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/network/initializing-a-miniport-driver">DriverEntry of NDIS
    Miniport Drivers</a>).




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/storage/driverentry-of-ide-controller-minidriver">DriverEntry</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nc-ndis-miniport_cancel_direct_oid_request">
   MiniportCancelDirectOidRequest</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nc-ndis-miniport_cancel_oid_request">MiniportCancelOidRequest</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nc-ndis-miniport_cancel_send">MiniportCancelSend</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nc-ndis-miniport_check_for_hang">MiniportCheckForHangEx</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nc-ndis-miniport_device_pnp_event_notify">
   MiniportDevicePnPEventNotify</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nc-ndis-miniport_direct_oid_request">MiniportDirectOidRequest</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nc-ndis-miniport_unload">MiniportDriverUnload</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nc-ndis-miniport_halt">MiniportHaltEx</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nc-ndis-miniport_initialize">MiniportInitializeEx</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nc-ndis-miniport_oid_request">MiniportOidRequest</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nc-ndis-miniport_pause">MiniportPause</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nc-ndis-miniport_reset">MiniportResetEx</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nc-ndis-miniport_restart">MiniportRestart</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nc-ndis-miniport_return_net_buffer_lists">
   MiniportReturnNetBufferLists</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nc-ndis-miniport_send_net_buffer_lists">MiniportSendNetBufferLists</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nc-ndis-set_options">MiniportSetOptions</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nc-ndis-miniport_shutdown">MiniportShutdownEx</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nf-ndis-ndismregisterminiportdriver">NdisMRegisterMiniportDriver</a>
 

 

