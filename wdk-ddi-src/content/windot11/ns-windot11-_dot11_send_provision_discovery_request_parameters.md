---
UID: NS:windot11._DOT11_SEND_PROVISION_DISCOVERY_REQUEST_PARAMETERS
title: "_DOT11_SEND_PROVISION_DISCOVERY_REQUEST_PARAMETERS"
author: windows-driver-content
description: The request parameters for a provision discovery request are specified in a DOT11_SEND_PROVISION_DISCOVERY_REQUEST_PARAMETERS structure. This structure is sent with an OID_DOT11_WFD_SEND_PROVISION_DISCOVERY_REQUEST request to the miniport.
old-location: netvista\dot11_send_provision_discovery_request_parameters.htm
old-project: netvista
ms.assetid: 1F764A80-71FC-445A-AADE-09660D1C250B
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: "*PDOT11_SEND_PROVISION_DISCOVERY_REQUEST_PARAMETERS, DOT11_SEND_PROVISION_DISCOVERY_REQUEST_PARAMETERS, DOT11_SEND_PROVISION_DISCOVERY_REQUEST_PARAMETERS structure [Network Drivers Starting with Windows Vista], PDOT11_SEND_PROVISION_DISCOVERY_REQUEST_PARAMETERS, PDOT11_SEND_PROVISION_DISCOVERY_REQUEST_PARAMETERS structure pointer [Network Drivers Starting with Windows Vista], _DOT11_SEND_PROVISION_DISCOVERY_REQUEST_PARAMETERS, netvista.dot11_send_provision_discovery_request_parameters, windot11/DOT11_SEND_PROVISION_DISCOVERY_REQUEST_PARAMETERS, windot11/PDOT11_SEND_PROVISION_DISCOVERY_REQUEST_PARAMETERS"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: windot11.h
req.include-header: Windot11.h
req.target-type: Windows
req.target-min-winverclnt: Supported starting with   Windows 8.
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
-	Windot11.h
api_name:
-	DOT11_SEND_PROVISION_DISCOVERY_REQUEST_PARAMETERS
product:
- Windows
targetos: Windows
req.typenames: DOT11_SEND_PROVISION_DISCOVERY_REQUEST_PARAMETERS, *PDOT11_SEND_PROVISION_DISCOVERY_REQUEST_PARAMETERS
req.product: Windows 10 or later.
---

# _DOT11_SEND_PROVISION_DISCOVERY_REQUEST_PARAMETERS structure


## -description


<div class="alert"><b>Important</b>  The <a href="https://msdn.microsoft.com/library/windows/hardware/ff560689">Native 802.11 Wireless LAN</a> interface is deprecated in Windows 10 and later. Please use the WLAN Device Driver Interface (WDI) instead. For more information about WDI, see <a href="https://msdn.microsoft.com/6EF92E34-7BC9-465E-B05D-2BCB29165A18">WLAN Universal Windows driver model</a>.</div><div> </div>The request parameters for a provision discovery request are specified in a <b>DOT11_SEND_PROVISION_DISCOVERY_REQUEST_PARAMETERS</b> structure. This structure is sent with an <a href="https://msdn.microsoft.com/69490609-60CB-426F-8ED7-F8B35CDFCE2A">OID_DOT11_WFD_SEND_PROVISION_DISCOVERY_REQUEST</a> request to the miniport.


## -syntax


````
typedef struct _DOT11_SEND_PROVISION_DISCOVERY_REQUEST_PARAMETERS {
  NDIS_OBJECT_HEADER         Header;
  DOT11_DIALOG_TOKEN         DialogToken;
  DOT11_MAC_ADDRESS          PeerDeviceAddress;
  ULONG                      uSendTimeout;
  DOT11_WFD_GROUP_CAPABILITY GroupCapability;
  DOT11_WFD_GROUP_ID         GroupID;
  BOOLEAN                    bUseGroupID;
  ULONG                      uIEsOffset;
  ULONG                      uIEsLength;
} DOT11_SEND_PROVISION_DISCOVERY_REQUEST_PARAMETERS, *PDOT11_SEND_PROVISION_DISCOVERY_REQUEST_PARAMETERS;
````


## -struct-fields




### -field Header

The type, revision, and size of the <b>DOT11_SEND_PROVISION_DISCOVERY_REQUEST_PARAMETERS</b> structure. The required settings for the members of <b>Header</b> are the following.

<table>
<tr>
<th>Member</th>
<th>Setting</th>
</tr>
<tr>
<td><b>Type</b></td>
<td>NDIS_OBJECT_TYPE_DEFAULT</td>
</tr>
<tr>
<td><b>Revision</b></td>
<td>DOT11_SEND_PROVISION_DISCOVERY_REQUEST_PARAMETERS_REVISION_1</td>
</tr>
<tr>
<td><b>Size</b></td>
<td>DOT11_SIZEOF_SEND_PROVISION_DISCOVERY_REQUEST_PARAMETERS_REVISION_1</td>
</tr>
</table>
 


### -field DialogToken

The dialog token to send  in the provision discovery request packet.


### -field PeerDeviceAddress

The destination address of the WFD device receiving the provision discovery packet.


### -field uSendTimeout

The maximum time, in milliseconds, allowed to send the provision discovery request. If the time-out expires before the miniport has successfully transmitted the provision discovery response, it should indicate the <a href="https://msdn.microsoft.com/library/windows/hardware/hh439783">NDIS_STATUS_DOT11_WFD_PROVISION_DISCOVERY_REQUEST_SEND_COMPLETE</a> with a failure status.


### -field GroupCapability

The capability values that are included in the Group Capability bitmask of the Peer-to-Peer (P2P) Capability Information Element (IE) in  a provision discovery request.


### -field GroupID

The group identifier to include in the provision discovery request.


### -field bUseGroupID

If TRUE, the value in <b>GroupID</b> should be included in the provision discovery request.


### -field uIEsOffset

The offset, in bytes,  of the array of additional information elements (IEs) the Wi-Fi Direct (WFD) port must add to the provision discovery request packet. This offset is from the start of the buffer that contains this structure.


### -field uIEsLength

The length, in bytes, of the array of IEs provided at <b>uIEsOffset</b>.


## -see-also

<a href="https://msdn.microsoft.com/69490609-60CB-426F-8ED7-F8B35CDFCE2A">OID_DOT11_WFD_SEND_PROVISION_DISCOVERY_REQUEST</a>



<a href="..\windot11\ns-windot11-_dot11_send_provision_discovery_request_parameters.md">DOT11_SEND_PROVISION_DISCOVERY_REQUEST_PARAMETERS</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh439783">NDIS_STATUS_DOT11_WFD_PROVISION_DISCOVERY_REQUEST_SEND_COMPLETE</a>



 

 


