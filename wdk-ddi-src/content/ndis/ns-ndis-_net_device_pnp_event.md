---
UID: NS:ndis._NET_DEVICE_PNP_EVENT
title: _NET_DEVICE_PNP_EVENT (ndis.h)
description: The NET_DEVICE_PNP_EVENT structure defines device plug and play (PnP) events for miniport adapters.
old-location: netvista\net_device_pnp_event.htm
tech.root: netvista
ms.assetid: 79298332-2d34-4ef3-ad43-5d218e3f6612
ms.date: 05/02/2018
ms.keywords: "*PNET_DEVICE_PNP_EVENT, NET_DEVICE_PNP_EVENT, NET_DEVICE_PNP_EVENT structure [Network Drivers Starting with Windows Vista], PNET_DEVICE_PNP_EVENT, PNET_DEVICE_PNP_EVENT structure pointer [Network Drivers Starting with Windows Vista], _NET_DEVICE_PNP_EVENT, miniport_structures_ref_42938d80-a578-40a4-ba12-0285d7c258eb.xml, ndis/NET_DEVICE_PNP_EVENT, ndis/PNET_DEVICE_PNP_EVENT, netvista.net_device_pnp_event"
ms.topic: struct
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
- NET_DEVICE_PNP_EVENT
product:
- Windows
targetos: Windows
req.typenames: NET_DEVICE_PNP_EVENT, *PNET_DEVICE_PNP_EVENT
---

# _NET_DEVICE_PNP_EVENT structure


## -description


The <b>NET_DEVICE_PNP_EVENT</b> structure defines device plug and play (PnP) events for miniport
  adapters.


## -struct-fields




### -field Header

The 
     <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ntddndis/ns-ntddndis-_ndis_object_header">NDIS_OBJECT_HEADER</a> structure for the
     <b>NET_DEVICE_PNP_EVENT</b> structure. NDIS sets the 
     <b>Type</b> member of the structure that 
     <b>Header</b> specifies to <b>NDIS_OBJECT_TYPE_DEFAULT</b>, the 
     <b>Revision</b> member to <b>NET_DEVICE_PNP_EVENT_REVISION_1</b>, and the 
     <b>Size</b> member to <b>NDIS_SIZEOF_NET_DEVICE_PNP_EVENT_REVISION_1</b>.


### -field PortNumber

The source port of the PnP event notification. If the status indication is not specific to a port,     
     <b>PortNumber</b> is zero.


### -field DevicePnPEvent

An event code that describes the PnP event as one of the following: 
     





#### NdisDevicePnPEventSurpriseRemoved

The network interface card (NIC) has been unexpectedly removed from the
       computer. For more information, see <a href="https://docs.microsoft.com/windows-hardware/drivers/network/handling-the-surprise-removal-of-a-nic">Handling the Surprise Removal of a NIC</a>.



#### NdisDevicePnPEventPowerProfileChanged

The power profile of the host system has changed.


### -field InformationBuffer

A pointer to a buffer. If NDIS sets the 
     <b>DevicePnPEvent</b> member to 
     <b>NdisDevicePnPEventPowerProfileChanged</b>, this buffer will contain a ULONG that NDIS sets to one of
     the following values:
     





#### NdisPowerProfileBattery

The host system is running on battery power.



#### NdisPowerProfileAcOnline

The host system is running on AC power.

If NDIS sets 
     <b>DevicePnPEvent</b> to 
     <b>NdisDevicePnPEventSurpriseRemoved</b>, 
     <b>InformationBuffer</b> is <b>NULL</b>.


### -field InformationBufferLength

The length, in bytes, of the buffer in the 
     <b>InformationBuffer</b> member.


### -field NdisReserved

Reserved for NDIS.


## -remarks



To provide a device PnP event notification, NDIS passes a pointer to a <b>NET_DEVICE_PNP_EVENT</b> structure
    to the 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ndis/nc-ndis-miniport_device_pnp_event_notify">
    MiniportDevicePnPEventNotify</a> or 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ndis/nc-ndis-filter_device_pnp_event_notify">
    FilterDevicePnPEventNotify</a> function.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ndis/nc-ndis-filter_device_pnp_event_notify">FilterDevicePnPEventNotify</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ndis/nc-ndis-miniport_device_pnp_event_notify">
   MiniportDevicePnPEventNotify</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ntddndis/ns-ntddndis-_ndis_object_header">NDIS_OBJECT_HEADER</a>
 

 

