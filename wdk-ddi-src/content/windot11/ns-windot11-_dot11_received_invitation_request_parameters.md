---
UID: NS:windot11._DOT11_RECEIVED_INVITATION_REQUEST_PARAMETERS
title: "_DOT11_RECEIVED_INVITATION_REQUEST_PARAMETERS"
author: windows-driver-content
description: The parameters for a received invitation response are specified in a DOT11_RECEIVED_INVITATION_REQUEST_PARAMETERS structure. This structure is sent with an NDIS_STATUS_DOT11_WFD_RECEIVED_INVITATION_REQUEST indication.
old-location: netvista\dot11_received_invitation_request_parameters.htm
tech.root: netvista
ms.assetid: B0937809-1C8D-45E0-AA33-5997563E894C
ms.date: 2/16/2018
ms.keywords: "*PDOT11_RECEIVED_INVITATION_REQUEST_PARAMETERS, DOT11_RECEIVED_INVITATION_REQUEST_PARAMETERS, DOT11_RECEIVED_INVITATION_REQUEST_PARAMETERS structure [Network Drivers Starting with Windows Vista], PDOT11_RECEIVED_INVITATION_REQUEST_PARAMETERS, PDOT11_RECEIVED_INVITATION_REQUEST_PARAMETERS structure pointer [Network Drivers Starting with Windows Vista], _DOT11_RECEIVED_INVITATION_REQUEST_PARAMETERS, netvista.dot11_received_invitation_request_parameters, windot11/DOT11_RECEIVED_INVITATION_REQUEST_PARAMETERS, windot11/PDOT11_RECEIVED_INVITATION_REQUEST_PARAMETERS"
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
-	DOT11_RECEIVED_INVITATION_REQUEST_PARAMETERS
product:
- Windows
targetos: Windows
req.typenames: DOT11_RECEIVED_INVITATION_REQUEST_PARAMETERS, *PDOT11_RECEIVED_INVITATION_REQUEST_PARAMETERS
product:
- Windows 10 or later.
---

# _DOT11_RECEIVED_INVITATION_REQUEST_PARAMETERS structure


## -description


<div class="alert"><b>Important</b>  The <a href="https://msdn.microsoft.com/library/windows/hardware/ff560689">Native 802.11 Wireless LAN</a> interface is deprecated in Windows 10 and later. Please use the WLAN Device Driver Interface (WDI) instead. For more information about WDI, see <a href="https://msdn.microsoft.com/6EF92E34-7BC9-465E-B05D-2BCB29165A18">WLAN Universal Windows driver model</a>.</div><div> </div>The parameters for a received invitation response are specified in a <b>DOT11_RECEIVED_INVITATION_REQUEST_PARAMETERS</b> structure. This structure is sent with an <a href="https://msdn.microsoft.com/library/windows/hardware/hh439793">NDIS_STATUS_DOT11_WFD_RECEIVED_INVITATION_REQUEST</a> indication.


## -syntax


```
typedef struct _DOT11_RECEIVED_INVITATION_REQUEST_PARAMETERS {
  NDIS_OBJECT_HEADER Header;
  DOT11_MAC_ADDRESS  TransmitterDeviceAddress;
  DOT11_MAC_ADDRESS  BSSID;
  DOT11_DIALOG_TOKEN DialogToken;
  PVOID              RequestContext;
  ULONG              uIEsOffset;
  ULONG              uIEsLength;
} DOT11_RECEIVED_INVITATION_REQUEST_PARAMETERS, *PDOT11_RECEIVED_INVITATION_REQUEST_PARAMETERS;
```


## -struct-fields




### -field Header

The type, revision, and size of the <b>DOT11_RECEIVED_INVITATION_REQUEST_PARAMETERS</b> structure. The required settings for the members of <b>Header</b> are the following.

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
<td>DOT11_RECEIVED_INVITATION_REQUEST_PARAMETERS_REVISION_1</td>
</tr>
<tr>
<td><b>Size</b></td>
<td>DOT11_SIZEOF_RECEIVED_INVITATION_REQUEST_PARAMETERS_REVISION_1</td>
</tr>
</table>
 


### -field TransmitterDeviceAddress

The address of the device that transmitted the invitation request packet.


### -field BSSID

The BSSID in the received invitation request packet.


### -field DialogToken

The dialog token received in the invitation request packet.


### -field RequestContext

The context data from the miniport driver. The system sends this context with the <a href="https://msdn.microsoft.com/library/windows/hardware/hh451807">OID_DOT11_WFD_SEND_INVITATION_RESPONSE</a> request.


### -field uIEsOffset

The offset, in bytes,  of the array of additional information elements (IEs) received in the invitation request packet. This offset is from the start of the buffer that contains this structure.


### -field uIEsLength

The length, in bytes, of the array of IEs provided at <b>uIEsOffset</b>.


## -see-also

<a href="https://msdn.microsoft.com/library/windows/hardware/hh451807">OID_DOT11_WFD_SEND_INVITATION_RESPONSE</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh439793">NDIS_STATUS_DOT11_WFD_RECEIVED_INVITATION_REQUEST</a>



 

 


