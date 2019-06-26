---
UID: NS:windot11._DOT11_INVITATION_RESPONSE_SEND_COMPLETE_PARAMETERS
title: _DOT11_INVITATION_RESPONSE_SEND_COMPLETE_PARAMETERS (windot11.h)
description: The parameters for an invitation response send completion are specified in a DOT11_INVITATION_RESPONSE_SEND_COMPLETE_PARAMETERS structure. This structure is sent with an NDIS_STATUS_DOT11_WFD_INVITATION_RESPONSE_SEND_COMPLETE indication.
old-location: netvista\dot11_invitation_response_send_complete_parameters.htm
tech.root: netvista
ms.assetid: EE537A6E-6722-4829-986A-37D41B149E37
ms.date: 02/16/2018
ms.keywords: "*PDOT11_INVITATION_RESPONSE_SEND_COMPLETE_PARAMETERS, DOT11_INVITATION_RESPONSE_SEND_COMPLETE_PARAMETERS, DOT11_INVITATION_RESPONSE_SEND_COMPLETE_PARAMETERS structure [Network Drivers Starting with Windows Vista], PDOT11_INVITATION_RESPONSE_SEND_COMPLETE_PARAMETERS, PDOT11_INVITATION_RESPONSE_SEND_COMPLETE_PARAMETERS structure pointer [Network Drivers Starting with Windows Vista], _DOT11_INVITATION_RESPONSE_SEND_COMPLETE_PARAMETERS, netvista.dot11_invitation_response_send_complete_parameters, windot11/DOT11_INVITATION_RESPONSE_SEND_COMPLETE_PARAMETERS, windot11/PDOT11_INVITATION_RESPONSE_SEND_COMPLETE_PARAMETERS"
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
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- Windot11.h
api_name:
- DOT11_INVITATION_RESPONSE_SEND_COMPLETE_PARAMETERS
product:
- Windows
targetos: Windows
req.typenames: DOT11_INVITATION_RESPONSE_SEND_COMPLETE_PARAMETERS, *PDOT11_INVITATION_RESPONSE_SEND_COMPLETE_PARAMETERS
product:
- Windows 10 or later.
---

# _DOT11_INVITATION_RESPONSE_SEND_COMPLETE_PARAMETERS structure


## -description


<div class="alert"><b>Important</b>  The <a href="https://docs.microsoft.com/previous-versions/windows/hardware/wireless/ff560689(v=vs.85)">Native 802.11 Wireless LAN</a> interface is deprecated in Windows 10 and later. Please use the WLAN Device Driver Interface (WDI) instead. For more information about WDI, see <a href="https://docs.microsoft.com/windows-hardware/drivers/network/wifi-universal-driver-model">WLAN Universal Windows driver model</a>.</div><div> </div>The parameters for an invitation response send completion are specified in a <b>DOT11_INVITATION_RESPONSE_SEND_COMPLETE_PARAMETERS</b> structure. This structure is sent with an <a href="https://docs.microsoft.com/windows-hardware/drivers/network/ndis-status-dot11-wfd-invitation-response-send-complete">NDIS_STATUS_DOT11_WFD_INVITATION_RESPONSE_SEND_COMPLETE</a> indication.


## -syntax


```cpp
typedef struct _DOT11_INVITATION_RESPONSE_SEND_COMPLETE_PARAMETERS {
  NDIS_OBJECT_HEADER  Header;
  DOT11_MAC_ADDRESS   ReceiverDeviceAddress;
  DOT11_DIALOG_TOKEN  DialogToken;
  NDIS_STATUS         Status;
  ULONG               uIEsOffset;
  ULONG               uIEsLength;
} DOT11_INVITATION_RESPONSE_SEND_COMPLETE_PARAMETERS, *PDOT11_INVITATION_RESPONSE_SEND_COMPLETE_PARAMETERS;
```


## -struct-fields




### -field Header

The type, revision, and size of the <b>DOT11_INVITATION_RESPONSE_SEND_COMPLETE_PARAMETERS</b> structure. The required settings for the members of <b>Header</b> are the following.

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
<td>DOT11_INVITATION_RESPONSE_SEND_COMPLETE_PARAMETERS_REVISION_1</td>
</tr>
<tr>
<td><b>Size</b></td>
<td>DOT11_SIZEOF_INVITATION_RESPONSE_SEND_COMPLETE_PARAMETERS_REVISION_1</td>
</tr>
</table>
 


### -field ReceiverDeviceAddress

The address of the device that the invitation response was sent to. This must match the <b>ReceiverDeviceAddress</b> member of <a href="..\windot11\ns-windot11-_dot11_send_invitation_response_parameters.md">DOT11_SEND_INVITATION_RESPONSE_PARAMETERS</a> sent with the <a href="https://docs.microsoft.com/windows-hardware/drivers/network/oid-dot11-wfd-send-invitation-response">OID_DOT11_WFD_SEND_INVITATION_RESPONSE</a> request.


### -field DialogToken

The dialog token from the invitation response packet. This must match the dialog token sent with the <a href="https://docs.microsoft.com/windows-hardware/drivers/network/oid-dot11-wfd-send-invitation-response">OID_DOT11_WFD_SEND_INVITATION_RESPONSE</a> request.


### -field Status

The status of the response send attempt. Set to <b>NDIS_STATUS_SUCCESS</b> if the packet was successfully transmitted.


### -field uIEsOffset

The offset, in bytes,  of the array of additional information elements (IEs) that were included in the invitation response packet. This offset is from the start of the buffer that contains this structure.


### -field uIEsLength

The length, in bytes, of the array of IEs provided at <b>uIEsOffset</b>.


## -see-also

<a href="..\windot11\ns-windot11-_dot11_invitation_response_send_complete_parameters.md">DOT11_INVITATION_RESPONSE_SEND_COMPLETE_PARAMETERS</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/network/oid-dot11-wfd-send-invitation-response">OID_DOT11_WFD_SEND_INVITATION_RESPONSE</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/network/ndis-status-dot11-wfd-invitation-response-send-complete">NDIS_STATUS_DOT11_WFD_INVITATION_RESPONSE_SEND_COMPLETE</a>



 

 


