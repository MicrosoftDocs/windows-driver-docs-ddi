---
UID: NS:wwan._WWAN_PACKET_SERVICE
title: "_WWAN_PACKET_SERVICE"
author: windows-driver-content
description: The WWAN_PACKET_SERVICE structure represents the packet service attachment state of the MB device.
old-location: netvista\wwan_packet_service.htm
old-project: netvista
ms.assetid: 5d444e1c-cbcf-47ab-9c5a-10af1f1915cf
ms.author: windowsdriverdev
ms.date: 3/26/2018
ms.keywords: "*PWWAN_PACKET_SERVICE, PWWAN_PACKET_SERVICE, PWWAN_PACKET_SERVICE structure pointer [Network Drivers Starting with Windows Vista], WWAN_PACKET_SERVICE, WWAN_PACKET_SERVICE structure [Network Drivers Starting with Windows Vista], WwanRef_ce147c69-a83d-42fd-9b08-7a12e6ecaf1a.xml, _WWAN_PACKET_SERVICE, netvista.wwan_packet_service, wwan/PWWAN_PACKET_SERVICE, wwan/WWAN_PACKET_SERVICE"
ms.prod: windows-hardware
ms.technology: windows-devices
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
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	wwan.h
api_name:
-	WWAN_PACKET_SERVICE
product: Windows
targetos: Windows
req.typenames: WWAN_PACKET_SERVICE, *PWWAN_PACKET_SERVICE
req.product: Windows 10 or later.
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
     <a href="https://msdn.microsoft.com/library/windows/hardware/ff571204">WWAN_DEVICE_CAPS</a>.
     

Miniport drivers must set this member to WWAN_DATA_CLASS_NONE when the device is not registered to a
     network, or when there is no data-class, or when the supported data-class is not available. Miniport
     drivers must set this member with a valid value when the device is registered to a network.


### -field CurrentDataClass

A single value from the 
     <b>WwanDataClass</b> member in 
     <a href="https://msdn.microsoft.com/library/windows/hardware/ff571204">WWAN_DEVICE_CAPS</a> that represents which
     data-class is currently being used by the device.
     

For all data services, except HSPA, miniport drivers should set this member to a single
     WWAN_DATA_CLASS_XXX value. For HSPA data services, miniport drivers should specify a bit-wise OR of
     WWAN_DATA_CLASS_HSDPA and WWAN_DATA_CLASS_HSUPA.

Miniport drivers must set this member with a valid value and send the appropriate notification when
     the device changes services, for example, from 1xRTT to 1xEV-DO.

Miniport drivers should set this member to WWAN_DATA_CLASS_CUSTOM if the data-class is not one of the
     predefined values in the 
     <b>WwanDataClass</b> member of 
     <a href="https://msdn.microsoft.com/library/windows/hardware/ff571204">WWAN_DEVICE_CAPS</a>.


## -remarks



The current packet-attach service state is typically reflected in the device's user interface.

The MB Service combines the data-classes that are represented in 
    <b>AvailableDataClass</b> with the supported data-classes that are reported with the device's capabilities
    to display the intersection of the available choices to the user.

If a device also supports a data-class that is anything other than the predefined values in the 
    <b>WwanDataClass</b> member of 
    <a href="https://msdn.microsoft.com/library/windows/hardware/ff571204">WWAN_DEVICE_CAPS</a>, the miniport driver
    should set the WWAN_DATA_CLASS_CUSTOM flag along with the appropriate bitmask defined for the data-class
    in this member.

<i>Query</i> and 
    <i>set</i> OID requests as well as unsolicited status events use the 
    <b>uNwError</b> member. If there is no network specific error or the network specific error is not known,
    miniport drivers should set this member to zero. The 
    "Status Indication Structure" section in 
    <a href="https://msdn.microsoft.com/5f04b7fd-3df3-4efa-bb26-c7f4cd3c9ebd">MB Operational Semantics</a> shows the
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




<a href="https://msdn.microsoft.com/63dbd674-32b3-4843-8349-706c3c0380e5">
   NDIS_WWAN_PACKET_SERVICE_STATE</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff571212">WWAN_PACKET_SERVICE_STATE</a>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20WWAN_PACKET_SERVICE structure%20 RELEASE:%20(3/26/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

