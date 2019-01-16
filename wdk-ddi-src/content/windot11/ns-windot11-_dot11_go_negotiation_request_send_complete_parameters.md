---
UID: NS:windot11._DOT11_GO_NEGOTIATION_REQUEST_SEND_COMPLETE_PARAMETERS
title: "_DOT11_GO_NEGOTIATION_REQUEST_SEND_COMPLETE_PARAMETERS"
description: The completion parameters for a Group Owner (GO) negotiation request are specified in a DOT11_GO_NEGOTIATION_REQUEST_SEND_COMPLETE_PARAMETERS structure.
old-location: netvista\_dot11_go_negotiation_request_send_complete_parameters.htm
tech.root: netvista
ms.assetid: 2F10078E-CE9F-425D-AB48-7A27906830B0
ms.date: 02/16/2018
ms.keywords: "*PDOT11_GO_NEGOTIATION_REQUEST_SEND_COMPLETE_PARAMETERS, DOT11_GO_NEGOTIATION_REQUEST_SEND_COMPLETE_PARAMETERS, DOT11_GO_NEGOTIATION_REQUEST_SEND_COMPLETE_PARAMETERS structure [Network Drivers Starting with Windows Vista], PDOT11_GO_NEGOTIATION_REQUEST_SEND_COMPLETE_PARAMETERS, PDOT11_GO_NEGOTIATION_REQUEST_SEND_COMPLETE_PARAMETERS structure pointer [Network Drivers Starting with Windows Vista], _DOT11_GO_NEGOTIATION_REQUEST_SEND_COMPLETE_PARAMETERS, netvista._dot11_go_negotiation_request_send_complete_parameters, windot11/ DOT11_GO_NEGOTIATION_REQUEST_SEND_COMPLETE_PARAMETERS, windot11/PDOT11_GO_NEGOTIATION_REQUEST_SEND_COMPLETE_PARAMETERS"
ms.topic: struct
req.header: windot11.h
req.include-header: Windot11.h
req.target-type: Windows
req.target-min-winverclnt: Versions:\_Supported in Windows 8
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
-	DOT11_GO_NEGOTIATION_REQUEST_SEND_COMPLETE_PARAMETERS
product:
- Windows
targetos: Windows
req.typenames: DOT11_GO_NEGOTIATION_REQUEST_SEND_COMPLETE_PARAMETERS, *PDOT11_GO_NEGOTIATION_REQUEST_SEND_COMPLETE_PARAMETERS
product:
- Windows 10 or later.
---

# _DOT11_GO_NEGOTIATION_REQUEST_SEND_COMPLETE_PARAMETERS structure


## -description


<div class="alert"><b>Important</b>  The <a href="https://msdn.microsoft.com/library/windows/hardware/ff560689">Native 802.11 Wireless LAN</a> interface is deprecated in Windows 10 and later. Please use the WLAN Device Driver Interface (WDI) instead. For more information about WDI, see <a href="https://msdn.microsoft.com/6EF92E34-7BC9-465E-B05D-2BCB29165A18">WLAN Universal Windows driver model</a>.</div><div> </div>The completion parameters for a Group Owner (GO) negotiation request are specified in a <b>DOT11_GO_NEGOTIATION_REQUEST_SEND_COMPLETE_PARAMETERS</b> structure. This structure is sent with an <a href="https://msdn.microsoft.com/library/windows/hardware/hh439774">NDIS_STATUS_DOT11_WFD_GO_NEGOTIATION_REQUEST_SEND_COMPLETE</a> request to the miniport.


## -syntax


```cpp
typedef struct _DOT11_GO_NEGOTIATION_REQUEST_SEND_COMPLETE_PARAMETERS {
  NDIS_OBJECT_HEADER Header;
  DOT11_MAC_ADDRESS  PeerDeviceAddress;
  DOT11_DIALOG_TOKEN DialogToken;
  NDIS_STATUS        Status;
  ULONG              uIEsOffset;
  ULONG              uIEsLength;
}  DOT11_GO_NEGOTIATION_REQUEST_SEND_COMPLETE_PARAMETERS, *PDOT11_GO_NEGOTIATION_REQUEST_SEND_COMPLETE_PARAMETERS;
```


## -struct-fields




### -field Header

Specifies the type, revision and size of the <b>DOT11_GO_NEGOTIATION_REQUEST_SEND_COMPLETE_PARAMETERS</b> structure. The required settings for the members of <b>Header</b> are the following:

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
<td>DOT11_GO_NEGOTIATION_REQUEST_SEND_COMPLETE_PARAMETERS_REVISION_1</td>
</tr>
<tr>
<td><b>Size</b></td>
<td>DOT11_SIZEOF_GO_NEGOTIATION_REQUEST_SEND_COMPLETE_PARAMETERS_REVISION_1</td>
</tr>
</table>
 


### -field PeerDeviceAddress

The device address of the Peer-to-Peer (P2P) Wi-Fi Direct (WFD) device that the GO negotiation request was sent to.


### -field DialogToken

The dialog token from the GO negotiation  request packet. This must match the dialog token sent with the <a href="https://msdn.microsoft.com/library/windows/hardware/hh451804">OID_DOT11_WFD_SEND_GO_NEGOTIATION_REQUEST</a> request.


### -field Status

The status of the request send attempt. Set to <b>NDIS_STATUS_SUCCESS</b> if the packet was successfully transmitted


### -field uIEsOffset

The offset, in bytes,  of the array of additional information elements (IEs) which were included in the the GO negotiation request packet. This offset is from the start of the buffer that contains this structure.


### -field uIEsLength

The length, in bytes, of the array of IEs provided at <b>uIEsOffset</b>.


## -see-also

<a href="https://msdn.microsoft.com/library/windows/hardware/hh439774">NDIS_STATUS_DOT11_WFD_GO_NEGOTIATION_REQUEST_SEND_COMPLETE</a>



 

 


