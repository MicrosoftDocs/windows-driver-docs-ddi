---
UID: NE:fwpsk.FWPS_FIELDS_INBOUND_MAC_FRAME_ETHERNET_
title: FWPS_FIELDS_INBOUND_MAC_FRAME_ETHERNET_ (fwpsk.h)
description: The FWPS_FIELDS_INBOUND_MAC_FRAME_ETHERNET enumeration type specifies the data field identifiers for the FWPS_LAYER_INBOUND_MAC_FRAME_ETHERNET run-time filtering layer.
old-location: netvista\fwps_fields_inbound_mac_frame_802_3.htm
tech.root: netvista
ms.assetid: 41313b4e-2f26-42a2-b3ec-d9b8c3041fac
ms.date: 05/02/2018
ms.keywords: FWPS_FIELDS_INBOUND_MAC_FRAME_ETHERNET, FWPS_FIELDS_INBOUND_MAC_FRAME_ETHERNET enumeration [Network Drivers Starting with Windows Vista], FWPS_FIELDS_INBOUND_MAC_FRAME_ETHERNET_, FWPS_FIELD_INBOUND_MAC_FRAME_ETHERNET_ETHER_TYPE, FWPS_FIELD_INBOUND_MAC_FRAME_ETHERNET_INTERFACE, FWPS_FIELD_INBOUND_MAC_FRAME_ETHERNET_INTERFACE_INDEX, FWPS_FIELD_INBOUND_MAC_FRAME_ETHERNET_INTERFACE_MAC_ADDRESS, FWPS_FIELD_INBOUND_MAC_FRAME_ETHERNET_L2_FLAGS, FWPS_FIELD_INBOUND_MAC_FRAME_ETHERNET_MAC_LOCAL_ADDRESS, FWPS_FIELD_INBOUND_MAC_FRAME_ETHERNET_MAC_LOCAL_ADDRESS_TYPE, FWPS_FIELD_INBOUND_MAC_FRAME_ETHERNET_MAC_REMOTE_ADDRESS, FWPS_FIELD_INBOUND_MAC_FRAME_ETHERNET_MAC_REMOTE_ADDRESS_TYPE, FWPS_FIELD_INBOUND_MAC_FRAME_ETHERNET_MAX, FWPS_FIELD_INBOUND_MAC_FRAME_ETHERNET_NDIS_PORT, FWPS_FIELD_INBOUND_MAC_FRAME_ETHERNET_VLAN_ID, fwpsk/FWPS_FIELDS_INBOUND_MAC_FRAME_ETHERNET, fwpsk/FWPS_FIELD_INBOUND_MAC_FRAME_ETHERNET_ETHER_TYPE, fwpsk/FWPS_FIELD_INBOUND_MAC_FRAME_ETHERNET_INTERFACE, fwpsk/FWPS_FIELD_INBOUND_MAC_FRAME_ETHERNET_INTERFACE_INDEX, fwpsk/FWPS_FIELD_INBOUND_MAC_FRAME_ETHERNET_INTERFACE_MAC_ADDRESS, fwpsk/FWPS_FIELD_INBOUND_MAC_FRAME_ETHERNET_L2_FLAGS, fwpsk/FWPS_FIELD_INBOUND_MAC_FRAME_ETHERNET_MAC_LOCAL_ADDRESS, fwpsk/FWPS_FIELD_INBOUND_MAC_FRAME_ETHERNET_MAC_LOCAL_ADDRESS_TYPE, fwpsk/FWPS_FIELD_INBOUND_MAC_FRAME_ETHERNET_MAC_REMOTE_ADDRESS, fwpsk/FWPS_FIELD_INBOUND_MAC_FRAME_ETHERNET_MAC_REMOTE_ADDRESS_TYPE, fwpsk/FWPS_FIELD_INBOUND_MAC_FRAME_ETHERNET_MAX, fwpsk/FWPS_FIELD_INBOUND_MAC_FRAME_ETHERNET_NDIS_PORT, fwpsk/FWPS_FIELD_INBOUND_MAC_FRAME_ETHERNET_VLAN_ID, netvista.fwps_fields_inbound_mac_frame_802_3, wfp_ref_5_const_3_data_fields_ecae0da2-76f4-4c49-a918-44527287417b.xml
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
req.irql: 
topic_type:
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- fwpsk.h
api_name:
- FWPS_FIELDS_INBOUND_MAC_FRAME_ETHERNET
product:
- Windows
targetos: Windows
req.typenames: FWPS_FIELDS_INBOUND_MAC_FRAME_ETHERNET
---

# FWPS_FIELDS_INBOUND_MAC_FRAME_ETHERNET_ enumeration


## -description


The <b>FWPS_FIELDS_INBOUND_MAC_FRAME_ETHERNET</b> enumeration type specifies the data field identifiers for the
  FWPS_LAYER_INBOUND_MAC_FRAME_ETHERNET 
  <a href="https://msdn.microsoft.com/library/windows/desktop/aa366492">run-time filtering layer</a>.
  <div class="alert"><b>Note</b>  In Windows 7 and Windows Server 2008 R2, the name of this enumeration was <b>FWPS_FIELDS_INBOUND_MAC_FRAME_802_3</b>.</div>
<div> </div>



## -enum-fields




### -field FWPS_FIELD_INBOUND_MAC_FRAME_ETHERNET_INTERFACE_MAC_ADDRESS

The inbound MAC frame IEEE 802.3 interface  MAC address field.


### -field FWPS_FIELD_INBOUND_MAC_FRAME_ETHERNET_MAC_LOCAL_ADDRESS

The inbound MAC frame IEEE 802.3 local MAC address field.


### -field FWPS_FIELD_INBOUND_MAC_FRAME_ETHERNET_MAC_REMOTE_ADDRESS

The inbound MAC frame IEEE 802.3 remote MAC address field.


### -field FWPS_FIELD_INBOUND_MAC_FRAME_ETHERNET_MAC_LOCAL_ADDRESS_TYPE

The inbound MAC frame IEEE 802.3 local MAC address type field.


### -field FWPS_FIELD_INBOUND_MAC_FRAME_ETHERNET_MAC_REMOTE_ADDRESS_TYPE

The inbound MAC frame IEEE 802.3 remote MAC address type field.


### -field FWPS_FIELD_INBOUND_MAC_FRAME_ETHERNET_ETHER_TYPE

The inbound MAC frame  IEEE 802.3 EtherType field.


### -field FWPS_FIELD_INBOUND_MAC_FRAME_ETHERNET_VLAN_ID

The inbound MAC frame IEEE 802.3 VLAN identifier field.


### -field FWPS_FIELD_INBOUND_MAC_FRAME_ETHERNET_INTERFACE

The inbound MAC frame  IEEE 802.3 interface field.


### -field FWPS_FIELD_INBOUND_MAC_FRAME_ETHERNET_INTERFACE_INDEX

The inbound MAC frame interface IEEE 802.3 interface index field.


### -field FWPS_FIELD_INBOUND_MAC_FRAME_ETHERNET_NDIS_PORT

The inbound MAC frame IEEE 802.3 NDIS port field.


### -field FWPS_FIELD_INBOUND_MAC_FRAME_ETHERNET_L2_FLAGS

The inbound MAC frame IEEE 802.3 flags field.


### -field FWPS_FIELD_INBOUND_MAC_FRAME_ETHERNET_COMPARTMENT_ID

The compartment that the network interface belongs to.

<div class="alert"><b>Note</b>  Supported starting with Windows 10, version 1703.</div>
<div> </div>

### -field FWPS_FIELD_INBOUND_MAC_FRAME_ETHERNET_MAX

The maximum value for this enumeration. This value might change in future versions of the NDIS
     header files and binaries.


## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff551334">FWPS_FIELDS_OUTBOUND_MAC_FRAME_ETHERNET</a>
 

 

