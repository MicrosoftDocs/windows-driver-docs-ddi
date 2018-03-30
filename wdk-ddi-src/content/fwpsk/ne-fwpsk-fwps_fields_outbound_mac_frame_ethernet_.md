---
UID: NE:fwpsk.FWPS_FIELDS_OUTBOUND_MAC_FRAME_ETHERNET_
title: FWPS_FIELDS_OUTBOUND_MAC_FRAME_ETHERNET_
author: windows-driver-content
description: The FWPS_FIELDS_OUTBOUND_MAC_FRAME_ETHERNET enumeration type specifies the data field identifiers for the FWPS_LAYER_OUTBOUND_MAC_FRAME_ETHERNET run-time filtering layer.
old-location: netvista\fwps_fields_outbound_mac_frame_802_3.htm
old-project: netvista
ms.assetid: 954dc1a8-006f-4a78-bc7a-1fef4d7b4186
ms.author: windowsdriverdev
ms.date: 2/27/2018
ms.keywords: FWPS_FIELDS_OUTBOUND_MAC_FRAME_ETHERNET, FWPS_FIELDS_OUTBOUND_MAC_FRAME_ETHERNET enumeration [Network Drivers Starting with Windows Vista], FWPS_FIELDS_OUTBOUND_MAC_FRAME_ETHERNET_, FWPS_FIELD_OUTBOUND_MAC_FRAME_ETHERNET_ETHER_TYPE, FWPS_FIELD_OUTBOUND_MAC_FRAME_ETHERNET_FLAGS, FWPS_FIELD_OUTBOUND_MAC_FRAME_ETHERNET_INTERFACE, FWPS_FIELD_OUTBOUND_MAC_FRAME_ETHERNET_INTERFACE_INDEX, FWPS_FIELD_OUTBOUND_MAC_FRAME_ETHERNET_INTERFACE_MAC_ADDRESS, FWPS_FIELD_OUTBOUND_MAC_FRAME_ETHERNET_MAC_LOCAL_ADDRESS, FWPS_FIELD_OUTBOUND_MAC_FRAME_ETHERNET_MAC_LOCAL_ADDRESS_TYPE, FWPS_FIELD_OUTBOUND_MAC_FRAME_ETHERNET_MAC_REMOTE_ADDRESS, FWPS_FIELD_OUTBOUND_MAC_FRAME_ETHERNET_MAC_REMOTE_ADDRESS_TYPE, FWPS_FIELD_OUTBOUND_MAC_FRAME_ETHERNET_MAX, FWPS_FIELD_OUTBOUND_MAC_FRAME_ETHERNET_NDIS_PORT, FWPS_FIELD_OUTBOUND_MAC_FRAME_ETHERNET_VLAN_ID, fwpsk/FWPS_FIELDS_OUTBOUND_MAC_FRAME_ETHERNET, fwpsk/FWPS_FIELD_OUTBOUND_MAC_FRAME_ETHERNET_ETHER_TYPE, fwpsk/FWPS_FIELD_OUTBOUND_MAC_FRAME_ETHERNET_FLAGS, fwpsk/FWPS_FIELD_OUTBOUND_MAC_FRAME_ETHERNET_INTERFACE, fwpsk/FWPS_FIELD_OUTBOUND_MAC_FRAME_ETHERNET_INTERFACE_INDEX, fwpsk/FWPS_FIELD_OUTBOUND_MAC_FRAME_ETHERNET_INTERFACE_MAC_ADDRESS, fwpsk/FWPS_FIELD_OUTBOUND_MAC_FRAME_ETHERNET_MAC_LOCAL_ADDRESS, fwpsk/FWPS_FIELD_OUTBOUND_MAC_FRAME_ETHERNET_MAC_LOCAL_ADDRESS_TYPE, fwpsk/FWPS_FIELD_OUTBOUND_MAC_FRAME_ETHERNET_MAC_REMOTE_ADDRESS, fwpsk/FWPS_FIELD_OUTBOUND_MAC_FRAME_ETHERNET_MAC_REMOTE_ADDRESS_TYPE, fwpsk/FWPS_FIELD_OUTBOUND_MAC_FRAME_ETHERNET_MAX, fwpsk/FWPS_FIELD_OUTBOUND_MAC_FRAME_ETHERNET_NDIS_PORT, fwpsk/FWPS_FIELD_OUTBOUND_MAC_FRAME_ETHERNET_VLAN_ID, netvista.fwps_fields_outbound_mac_frame_802_3, wfp_ref_5_const_3_data_fields_d53ec059-3f9a-4eef-9994-94e6923145aa.xml
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
req.header: fwpsk.h
req.include-header: Fwpsk.h
req.target-type: Windows
req.target-min-winverclnt: Windows 7
req.target-min-winversvr: Windows Server 2008 R2
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
req.irql: "<= DISPATCH_LEVEL"
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	fwpsk.h
api_name:
-	FWPS_FIELDS_OUTBOUND_MAC_FRAME_ETHERNET
product: Windows
targetos: Windows
req.typenames: FWPS_FIELDS_OUTBOUND_MAC_FRAME_ETHERNET
---

# FWPS_FIELDS_OUTBOUND_MAC_FRAME_ETHERNET_ enumeration


## -description


The <b>FWPS_FIELDS_OUTBOUND_MAC_FRAME_ETHERNET</b> enumeration type specifies the data field identifiers for the
  FWPS_LAYER_OUTBOUND_MAC_FRAME_ETHERNET 
  <a href="https://msdn.microsoft.com/en-us/library/windows/desktop/aa366492">run-time filtering layer</a>.
  <div class="alert"><b>Note</b>  In Windows 7 and Windows Server 2008 R2, the name of this enumeration was <b>FWPS_FIELDS_OUTBOUND_MAC_FRAME_802_3</b>.</div>
<div> </div>



## -enum-fields




### -field FWPS_FIELD_OUTBOUND_MAC_FRAME_ETHERNET_INTERFACE_MAC_ADDRESS

The outbound MAC frame IEEE 802.3 interface MAC address field.


### -field FWPS_FIELD_OUTBOUND_MAC_FRAME_ETHERNET_MAC_LOCAL_ADDRESS

The outbound MAC frame IEEE 802.3 local MAC address field.


### -field FWPS_FIELD_OUTBOUND_MAC_FRAME_ETHERNET_MAC_REMOTE_ADDRESS

The outbound MAC frame IEEE 802.3 remote MAC address field.


### -field FWPS_FIELD_OUTBOUND_MAC_FRAME_ETHERNET_MAC_LOCAL_ADDRESS_TYPE

The outbound MAC frame IEEE 802.3 local MAC address type field.


### -field FWPS_FIELD_OUTBOUND_MAC_FRAME_ETHERNET_MAC_REMOTE_ADDRESS_TYPE

The outbound MAC frame IEEE 802.3 remote MAC address type field.


### -field FWPS_FIELD_OUTBOUND_MAC_FRAME_ETHERNET_ETHER_TYPE

The outbound MAC frame IEEE 802.3 EtherType field.


### -field FWPS_FIELD_OUTBOUND_MAC_FRAME_ETHERNET_VLAN_ID

The outbound MAC frame IEEE 802.3  VLAN   identifier field.


### -field FWPS_FIELD_OUTBOUND_MAC_FRAME_ETHERNET_INTERFACE

The outbound MAC frame IEEE 802.3 interface field.


### -field FWPS_FIELD_OUTBOUND_MAC_FRAME_ETHERNET_INTERFACE_INDEX

The outbound MAC frame IEEE 802.3 interface index field.


### -field FWPS_FIELD_OUTBOUND_MAC_FRAME_ETHERNET_NDIS_PORT

The outbound MAC frame IEEE 802.3 NDIS port field.


### -field FWPS_FIELD_OUTBOUND_MAC_FRAME_ETHERNET_L2_FLAGS


### -field FWPS_FIELD_OUTBOUND_MAC_FRAME_ETHERNET_COMPARTMENT_ID


### -field FWPS_FIELD_OUTBOUND_MAC_FRAME_ETHERNET_MAX

The maximum value for this enumeration. This value might change in future versions of the NDIS
     header files and binaries.


#### - FWPS_FIELD_OUTBOUND_MAC_FRAME_ETHERNET_FLAGS

The outbound MAC frame IEEE 802.3 flags field.


## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff551291">FWPS_FIELDS_INBOUND_MAC_FRAME_ETHERNET</a>
 

 

<<<<<<< HEAD
=======
<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20FWPS_FIELDS_OUTBOUND_MAC_FRAME_ETHERNET enumeration%20 RELEASE:%20(2/27/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

>>>>>>> parent of 2d896a8e266... Added changes
