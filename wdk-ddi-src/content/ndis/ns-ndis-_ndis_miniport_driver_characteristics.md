---
UID: NS:ndis._NDIS_MINIPORT_DRIVER_CHARACTERISTICS
title: _NDIS_MINIPORT_DRIVER_CHARACTERISTICS
author: windows-driver-content
description: An NDIS driver initializes an NDIS_MINIPORT_DRIVER_CHARACTERISTICS structure to define its miniport driver characteristics, including the entry points for its MiniportXxx functions.
old-location: netvista\ndis_miniport_driver_characteristics.htm
old-project: netvista
ms.assetid: 2e2c8522-127d-49d5-a5d6-97f9403bec89
ms.author: windowsdriverdev
ms.date: 1/11/2018
ms.keywords: _NDIS_MINIPORT_DRIVER_CHARACTERISTICS, *PNDIS_MINIPORT_DRIVER_CHARACTERISTICS, NDIS_MINIPORT_DRIVER_CHARACTERISTICS
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: ndis.h
req.include-header: Ndis.h
req.target-type: Windows
req.target-min-winverclnt: Supported in NDIS 6.0 and later.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: NDIS_MINIPORT_DRIVER_CHARACTERISTICS
req.alt-loc: ndis.h
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: See Remarks section
req.typenames: *PNDIS_MINIPORT_DRIVER_CHARACTERISTICS, NDIS_MINIPORT_DRIVER_CHARACTERISTICS
---

# _NDIS_MINIPORT_DRIVER_CHARACTERISTICS structure



## -description
An NDIS driver initializes an <b>NDIS_MINIPORT_DRIVER_CHARACTERISTICS</b> structure to define its miniport
  driver characteristics, including the entry points for its 
  <i>MiniportXxx</i> functions.



## -syntax

````
typedef struct _NDIS_MINIPORT_DRIVER_CHARACTERISTICS {
  NDIS_OBJECT_HEADER                         Header;
  UCHAR                                      MajorNdisVersion;
  UCHAR                                      MinorNdisVersion;
  UCHAR                                      MajorDriverVersion;
  UCHAR                                      MinorDriverVersion;
  ULONG                                      Flags;
  SET_OPTIONS_HANDLER                        SetOptionsHandler;
  MINIPORT_INITIALIZE_HANDLER                InitializeHandlerEx;
  MINIPORT_HALT_HANDLER                      HaltHandlerEx;
  MINIPORT_DRIVER_UNLOAD                     UnloadHandler;
  MINIPORT_PAUSE_HANDLER                     PauseHandler;
  MINIPORT_RESTART_HANDLER                   RestartHandler;
  MINIPORT_OID_REQUEST_HANDLER               OidRequestHandler;
  MINIPORT_SEND_NET_BUFFER_LISTS_HANDLER     SendNetBufferListsHandler;
  MINIPORT_RETURN_NET_BUFFER_LISTS_HANDLER   ReturnNetBufferListsHandler;
  MINIPORT_CANCEL_SEND_HANDLER               CancelSendHandler;
  MINIPORT_CHECK_FOR_HANG_HANDLER            CheckForHangHandlerEx;
  MINIPORT_RESET_HANDLER                     ResetHandlerEx;
  MINIPORT_DEVICE_PNP_EVENT_NOTIFY_HANDLER   DevicePnPEventNotifyHandler;
  MINIPORT_SHUTDOWN_HANDLER                  ShutdownHandlerEx;
  MINIPORT_CANCEL_OID_REQUEST_HANDLER        CancelOidRequestHandler;
#if (NDIS_SUPPORT_NDIS61)
  MINIPORT_DIRECT_OID_REQUEST_HANDLER        DirectOidRequestHandler;
  MINIPORT_CANCEL_DIRECT_OID_REQUEST_HANDLER CancelDirectOidRequestHandler;
#endif 
#if (NDIS_SUPPORT_NDIS680)
  MINIPORT_SYNCHRONOUS_OID_REQUEST_HANDLER   SynchronousOidRequestHandler;
#endif 
} NDIS_MINIPORT_DRIVER_CHARACTERISTICS, *PNDIS_MINIPORT_DRIVER_CHARACTERISTICS;
````


## -struct-fields

### -field Header

The 
     <a href="..\ntddndis\ns-ntddndis-_ndis_object_header.md">NDIS_OBJECT_HEADER</a> structure for the
     <b>NDIS_MINIPORT_DRIVER_CHARACTERISTICS</b> structure. Set the 
     <b>Type</b> member of the structure that 
     <b>Header</b> specifies to NDIS_OBJECT_TYPE_MINIPORT_DRIVER_CHARACTERISTICS.
     

To indicate the version of the <b>NDIS_MINIPORT_DRIVER_CHARACTERISTICS</b> structure, set the 
     <b>Revision</b> member to one of the following values:




### -field NDIS_MINIPORT_DRIVER_CHARACTERISTICS_REVISION_3

Added the <b>SynchronousOidRequestHandler</b> member for NDIS 6.80.

Set the 
        <b>Size</b> member to NDIS_SIZEOF_MINIPORT_DRIVER_CHARACTERISTICS_REVISION_3.


### -field NDIS_MINIPORT_DRIVER_CHARACTERISTICS_REVISION_2

Added the <b>DirectOidRequestHandler</b>, and <b>CancelDirectOidRequestHandler</b> members for NDIS 6.1.

Set the 
        <b>Size</b> member to NDIS_SIZEOF_MINIPORT_DRIVER_CHARACTERISTICS_REVISION_2.


### -field NDIS_MINIPORT_DRIVER_CHARACTERISTICS_REVISION_1

Original version for NDIS 6.0.

Set the 
        <b>Size</b> member to NDIS_SIZEOF_MINIPORT_DRIVER_CHARACTERISTICS_REVISION_1.

</dd>
</dl>

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

### -field 0

</td>
<td width="60%">
NDIS 6

</td>
</tr>
<tr>
<td width="40%">

### -field 20

</td>
<td width="60%">
NDIS 6.20

</td>
</tr>
<tr>
<td width="40%">

### -field 30

</td>
<td width="60%">
NDIS 6.30

</td>
</tr>
<tr>
<td width="40%">

### -field 40

</td>
<td width="60%">
NDIS 6.40

</td>
</tr>
<tr>
<td width="40%">

### -field 50

</td>
<td width="60%">
NDIS 6.50

</td>
</tr>
<tr>
<td width="40%">

### -field 51

</td>
<td width="60%">
NDIS 6.51

</td>
</tr>
<tr>
<td width="40%">

### -field 60

</td>
<td width="60%">
NDIS 6.60

</td>
</tr>
<tr>
<td width="40%">

### -field 70

</td>
<td width="60%">
NDIS 6.70

</td>
</tr>
<tr>
<td width="40%">

### -field 80

</td>
<td width="60%">
NDIS 6.80

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
     




### -field NDIS_INTERMEDIATE_DRIVER

Set if the caller is an NDIS intermediate driver.


### -field NDIS_WDM_DRIVER

Set if the caller is an NDIS-WDM miniport driver.

</dd>
</dl>

### -field SetOptionsHandler

The entry point for the caller's 
     <a href="https://msdn.microsoft.com/en-us/library/windows/hardware/ff570269">MiniportSetOptions</a> function.

Required for Co-NDIS. Suggested for Ethernet miniport drivers that support RSS using MSI-C over PCI.


### -field InitializeHandlerEx

Required. The entry point for the 
     <a href="..\ndis\nc-ndis-miniport_initialize.md">
     MiniportInitializeEx</a> function.


### -field HaltHandlerEx

Required. The entry point for the 
     <a href="..\ndis\nc-ndis-miniport_halt.md">MiniportHaltEx</a> function.


### -field UnloadHandler

Required. The entry point for the 
     <a href="..\ndis\nc-ndis-miniport_unload.md">
     MiniportDriverUnload</a> function.


### -field PauseHandler

Required. The entry point for the 
     <a href="..\ndis\nc-ndis-miniport_pause.md">MiniportPause</a> function.


### -field RestartHandler

Required. The entry point for the 
     <a href="..\ndis\nc-ndis-miniport_restart.md">MiniportRestart</a> function.


### -field OidRequestHandler

The entry point for the 
     <a href="..\ndis\nc-ndis-miniport_oid_request.md">MiniportOidRequest</a> function. Required for all connection-less miniport drivers, including all Ethernet, WLAN, and IM drivers. Optional for some CoNDIS miniport drivers.


### -field SendNetBufferListsHandler

Required. The entry point for the 
     <a href="..\ndis\nc-ndis-miniport_send_net_buffer_lists.md">
     MiniportSendNetBufferLists</a> function.


### -field ReturnNetBufferListsHandler

Required. The entry point for the 
     <a href="..\ndis\nc-ndis-miniport_return_net_buffer_lists.md">
     MiniportReturnNetBufferLists</a> function.


### -field CancelSendHandler

Required. The entry point for the 
     <a href="..\ndis\nc-ndis-miniport_cancel_send.md">MiniportCancelSend</a> function.


### -field CheckForHangHandlerEx

Optional. The entry point for the 
     <a href="..\ndis\nc-ndis-miniport_check_for_hang.md">
     MiniportCheckForHangEx</a> function. 
     

<i>MiniportCheckForHangEx</i> is not required for intermediate drivers or virtual miniports because they are not physical devices that can hang, so they must set this entry
     point to <b>NULL</b>. 

<i>MiniportCheckForHangEx</i> is forbidden on any AOAC device due to the impact on battery life, so miniport drivers for these devices must set this entry point to <b>NULL</b>.

<i>MiniportCheckForHangEx</i> is discouraged for miniport drivers intended to be installed on non-AOAC, battery-powered devices due to the impact on battery life, so they should set this entry point to <b>NULL</b>.

<i>MiniportCheckForHangEx</i> is permitted but not required for miniport drivers that are intended to be installed in line-powered (mains-powered) devices. For drivers targeting NDIS 6.30 and later, consider using <a href="..\ndis\nf-ndis-ndismresetminiport.md">NdisMResetMiniport</a> instead.


### -field ResetHandlerEx

Optional (required if you provide <b>CheckForHangHandlerEx</b>). The entry point for the 
     <a href="..\ndis\nc-ndis-miniport_reset.md">MiniportResetEx</a> function. 
     <i>MiniportResetEx</i> is not required for intermediate drivers, so they should set this entry point to
     <b>NULL</b>.


### -field DevicePnPEventNotifyHandler

Required. The entry point for the 
     <a href="..\ndis\nc-ndis-miniport_device_pnp_event_notify.md">
     MiniportDevicePnPEventNotify</a> function.


### -field ShutdownHandlerEx

Required. The entry point for the 
     <a href="..\ndis\nc-ndis-miniport_shutdown.md">MiniportShutdownEx</a> function.


### -field CancelOidRequestHandler

Required. The entry point for the 
     <a href="..\ndis\nc-ndis-miniport_cancel_oid_request.md">
     MiniportCancelOidRequest</a> function.


### -field DirectOidRequestHandler

The entry point for the 
      <a href="..\ndis\nc-ndis-miniport_direct_oid_request.md">
      MiniportDirectOidRequest</a> function. This is an optional entry point. Set this member to <b>NULL</b> if
      the miniport driver does not handle direct OID requests. 

Optional for Ethernet; however, if one is provided, then both must be provided.

Required for WLAN and Ethernet miniports that implement RDMA or IPSec offload.


### -field CancelDirectOidRequestHandler

The entry point for the 
      <a href="..\ndis\nc-ndis-miniport_cancel_direct_oid_request.md">
      MiniportCancelDirectOidRequest</a> function. This is an optional entry point. Set this member to <b>NULL</b>
      if the miniport driver does not handle direct OID requests.

Optional for Ethernet; however, if one is provided, then both must be provided.

Required for WLAN and Ethernet miniports that implement RDMA or IPSec offload.


### -field SynchronousOidRequestHandler

The entry point for the 
      <a href="..\ndis\nf-ndis-miniport_synchronous_oid_request.md">
      MiniportSynchronousOidRequest</a> function. This is an optional entry point. Set this member to <b>NULL</b> if
      the miniport driver does not handle Synchronous OID requests. 

Required for WLAN and Ethernet miniports that implement RSSv2.


## -remarks
An NDIS driver passes a pointer to its <b>NDIS_MINIPORT_DRIVER_CHARACTERISTICS</b> structure in the 
    <i>MiniportDriverCharacteristics</i> parameter of the 
    <a href="..\ndis\nf-ndis-ndismregisterminiportdriver.md">
    NdisMRegisterMiniportDriver</a> function. A miniport driver calls 
    <b>NdisMRegisterMiniportDriver</b> from its 
    <a href="..\wdm\nc-wdm-driver_initialize.md">DriverEntry</a> routine (see also 
    <a href="https://msdn.microsoft.com/en-us/library/windows/hardware/ff548818">DriverEntry of NDIS
    Miniport Drivers</a>).


## -see-also
<dl>
<dt>
<a href="..\wdm\nc-wdm-driver_initialize.md">DriverEntry</a>
</dt>
<dt>
<a href="..\ndis\nc-ndis-miniport_cancel_direct_oid_request.md">
   MiniportCancelDirectOidRequest</a>
</dt>
<dt>
<a href="..\ndis\nc-ndis-miniport_cancel_oid_request.md">MiniportCancelOidRequest</a>
</dt>
<dt>
<a href="..\ndis\nc-ndis-miniport_cancel_send.md">MiniportCancelSend</a>
</dt>
<dt>
<a href="..\ndis\nc-ndis-miniport_check_for_hang.md">MiniportCheckForHangEx</a>
</dt>
<dt>
<a href="..\ndis\nc-ndis-miniport_direct_oid_request.md">MiniportDirectOidRequest</a>
</dt>
<dt>
<a href="..\ndis\nc-ndis-miniport_unload.md">MiniportDriverUnload</a>
</dt>
<dt>
<a href="..\ndis\nc-ndis-miniport_halt.md">MiniportHaltEx</a>
</dt>
<dt>
<a href="..\ndis\nc-ndis-miniport_initialize.md">MiniportInitializeEx</a>
</dt>
<dt>
<a href="..\ndis\nc-ndis-miniport_pause.md">MiniportPause</a>
</dt>
<dt>
<a href="..\ndis\nc-ndis-miniport_device_pnp_event_notify.md">
   MiniportDevicePnPEventNotify</a>
</dt>
<dt>
<a href="..\ndis\nc-ndis-miniport_oid_request.md">MiniportOidRequest</a>
</dt>
<dt>
<a href="..\ndis\nc-ndis-miniport_reset.md">MiniportResetEx</a>
</dt>
<dt>
<a href="..\ndis\nc-ndis-miniport_restart.md">MiniportRestart</a>
</dt>
<dt>
<a href="..\ndis\nc-ndis-miniport_return_net_buffer_lists.md">
   MiniportReturnNetBufferLists</a>
</dt>
<dt>
<a href="..\ndis\nc-ndis-miniport_send_net_buffer_lists.md">MiniportSendNetBufferLists</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/en-us/library/windows/hardware/ff570269">MiniportSetOptions</a>
</dt>
<dt>
<a href="..\ndis\nc-ndis-miniport_shutdown.md">MiniportShutdownEx</a>
</dt>
<dt>
<a href="..\ndis\nf-ndis-ndismregisterminiportdriver.md">NdisMRegisterMiniportDriver</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20NDIS_MINIPORT_DRIVER_CHARACTERISTICS structure%20 RELEASE:%20(1/11/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

