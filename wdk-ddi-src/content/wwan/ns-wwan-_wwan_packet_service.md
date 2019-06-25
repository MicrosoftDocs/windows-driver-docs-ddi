---
UID: NS:wwan._WWAN_PACKET_SERVICE
title: _WWAN_PACKET_SERVICE (wwan.h)
description: The WWAN_PACKET_SERVICE structure represents the packet service attachment state of the MB device.
old-location: netvista\wwan_packet_service.htm
tech.root: netvista
ms.assetid: 5d444e1c-cbcf-47ab-9c5a-10af1f1915cf
ms.date: 04/05/2019
ms.keywords: "*PWWAN_PACKET_SERVICE, PWWAN_PACKET_SERVICE, PWWAN_PACKET_SERVICE structure pointer [Network Drivers Starting with Windows Vista], WWAN_PACKET_SERVICE, WWAN_PACKET_SERVICE structure [Network Drivers Starting with Windows Vista], WwanRef_ce147c69-a83d-42fd-9b08-7a12e6ecaf1a.xml, _WWAN_PACKET_SERVICE, netvista.wwan_packet_service, wwan/PWWAN_PACKET_SERVICE, wwan/WWAN_PACKET_SERVICE"
ms.topic: struct
req.header: wwan.h
req.include-header: Wwan.h
req.target-type: Windows
req.target-min-winverclnt: Available in Windows 7 and later versions of Windows.
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
- wwan.h
api_name:
- WWAN_PACKET_SERVICE
product:
- Windows
targetos: Windows
req.typenames: WWAN_PACKET_SERVICE, *PWWAN_PACKET_SERVICE
---

# _WWAN_PACKET_SERVICE structure


## -description


The WWAN_PACKET_SERVICE structure represents the packet service attachment state of the MB
  device.


## -struct-fields




### -field uNwError

A network specific error, in the event of a packet-attach or packet-detach failure. For more
     information about this member, see the following 
     "Remarks" section.


### -field PacketServiceState

The packet service state of the device.


### -field AvailableDataClass

A bitmap that represents which data-classes are available to the device in the current network.
     For a detailed list of values, see the 
     <b>WwanDataClass</b> member of 
     <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wwan/ns-wwan-_wwan_device_caps">WWAN_DEVICE_CAPS</a>.
     

Miniport drivers must set this member to WWAN_DATA_CLASS_NONE when the device is not registered to a
     network, or when there is no data-class, or when the supported data-class is not available. Miniport
     drivers must set this member with a valid value when the device is registered to a network.


### -field CurrentDataClass

A single value from the 
     <b>WwanDataClass</b> member in 
     <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wwan/ns-wwan-_wwan_device_caps">WWAN_DEVICE_CAPS</a> that represents which
     data-class is currently being used by the device.
     

For all data services, except HSPA, miniport drivers should set this member to a single
     WWAN_DATA_CLASS_XXX value. For HSPA data services, miniport drivers should specify a bit-wise OR of
     WWAN_DATA_CLASS_HSDPA and WWAN_DATA_CLASS_HSUPA.

Miniport drivers must set this member with a valid value and send the appropriate notification when
     the device changes services, for example, from 1xRTT to 1xEV-DO.

Miniport drivers should set this member to WWAN_DATA_CLASS_CUSTOM if the data-class is not one of the
     predefined values in the 
     <b>WwanDataClass</b> member of 
     <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wwan/ns-wwan-_wwan_device_caps">WWAN_DEVICE_CAPS</a>.

### -field FrequencyRange

A [**WWAN_5G_FREQUENCY_RANGE**](../wwan/ne-wwan-_wwan_5g_frequency_range.md) value that specifies the frequency ranges that the device is using. This member is only valid if **CurrentDataClass** is either **WWAN_DATA_CLASS_5G_NSA** or **WWAN_DATA_CLASS_SA**.

## -remarks



The current packet-attach service state is typically reflected in the device's user interface.

The MB Service combines the data-classes that are represented in 
    <b>AvailableDataClass</b> with the supported data-classes that are reported with the device's capabilities
    to display the intersection of the available choices to the user.

If a device also supports a data-class that is anything other than the predefined values in the 
    <b>WwanDataClass</b> member of 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wwan/ns-wwan-_wwan_device_caps">WWAN_DEVICE_CAPS</a>, the miniport driver
    should set the WWAN_DATA_CLASS_CUSTOM flag along with the appropriate bitmask defined for the data-class
    in this member.

<i>Query</i> and 
    <i>set</i> OID requests as well as unsolicited status events use the 
    <b>uNwError</b> member. If there is no network specific error or the network specific error is not known,
    miniport drivers should set this member to zero. The 
    "Status Indication Structure" section in 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/network/mb-operational-semantics">MB Operational Semantics</a> shows the
    packet-attach or packet-detach cause code failure values that are defined in the 
    <i>3GPP TS 24.008 Specification</i>.

The following points provide guidelines on returning network specific error in different
    scenarios:

<ul>
<li>
If the packet-attach operation fails because of network specific error, miniport drivers should
      return the network specific error in response to 
      <i>query</i> requests. In this case, miniport drivers should set the 
      <b>uStatus</b> member of the NDIS_WWAN_PACKET_SERVICE_STATE structure to WWAN_STATUS_SUCCESS and set the      
      <b>uNwError</b> member to the network specific error code.

</li>
<li>
If a 
      <i>set</i> request fails, miniport drivers should return the network specific error code. In this case,
      miniport drivers should set the 
      <b>uStatus</b> member of the NDIS_WWAN_PACKET_SERVICE_STATE structure to WWAN_STATUS_FAILURE and set the      
      <b>uNwError</b> member to the network specific error code.

</li>
<li>
Whenever the device registration state changes because the network packet-detaches the device then
      unsolicited status events should include the network specific error. In this case, the miniport driver
      should set the 
      <b>uStatus</b> member of the NDIS_WWAN_PACKET_SERVICE_STATE structure to WWAN_STATUS_SUCCESS and set the      
      <b>uNwError</b> member to the network specific error code.

</li>
</ul>
Miniport drivers can provide additional error codes as defined by the GSM standards specification of
    packet-attach error codes returned by the network. For example, miniport drivers can communicate the 3GPP
    specification TS 24.008 packet-attach error codes, such as error code 12 (Location area not allowed), to
    the MB Service through the 
    <b>uNwError</b> member.

Miniport drivers must report the cause code at the earliest possible instance. For example, if the MB
    device encounters one of these codes when attempting to register the device on with a network provider,
    the miniport driver should report it at that time.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ndiswwan/ns-ndiswwan-_ndis_wwan_packet_service_state">
   NDIS_WWAN_PACKET_SERVICE_STATE</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wwan/ne-wwan-_wwan_packet_service_state">WWAN_PACKET_SERVICE_STATE</a>
 

 

