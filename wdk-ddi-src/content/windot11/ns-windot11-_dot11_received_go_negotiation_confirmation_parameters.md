---
UID: NS:windot11._DOT11_RECEIVED_GO_NEGOTIATION_CONFIRMATION_PARAMETERS
title: "_DOT11_RECEIVED_GO_NEGOTIATION_CONFIRMATION_PARAMETERS"
author: windows-driver-content
description: The parameters for a received Group Owner (GO) negotiation confirmation are specified in a DOT11_RECEIVED_GO_NEGOTIATION_CONFIRMATION_PARAMETERS structure.
old-location: netvista\dot11_received_go_negotiation_confirmation_parameters.htm
old-project: netvista
ms.assetid: 8FFCA7EB-BD0F-4EAF-BD5F-A98F2127DE77
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: "*PDOT11_RECEIVED_GO_NEGOTIATION_CONFIRMATION_PARAMETERS, DOT11_RECEIVED_GO_NEGOTIATION_CONFIRMATION_PARAMETERS, DOT11_RECEIVED_GO_NEGOTIATION_CONFIRMATION_PARAMETERS structure [Network Drivers Starting with Windows Vista], PDOT11_RECEIVED_GO_NEGOTIATION_CONFIRMATION_PARAMETERS, PDOT11_RECEIVED_GO_NEGOTIATION_CONFIRMATION_PARAMETERS structure pointer [Network Drivers Starting with Windows Vista], _DOT11_RECEIVED_GO_NEGOTIATION_CONFIRMATION_PARAMETERS, netvista.dot11_received_go_negotiation_confirmation_parameters, windot11/DOT11_RECEIVED_GO_NEGOTIATION_CONFIRMATION_PARAMETERS, windot11/PDOT11_RECEIVED_GO_NEGOTIATION_CONFIRMATION_PARAMETERS"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: windot11.h
req.include-header: Windot11.h
req.target-type: Windows
req.target-min-winverclnt: Supported starting with   Windows 8,
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
-	DOT11_RECEIVED_GO_NEGOTIATION_CONFIRMATION_PARAMETERS
product: Windows
targetos: Windows
req.typenames: DOT11_RECEIVED_GO_NEGOTIATION_CONFIRMATION_PARAMETERS, *PDOT11_RECEIVED_GO_NEGOTIATION_CONFIRMATION_PARAMETERS
req.product: Windows 10 or later.
---

# _DOT11_RECEIVED_GO_NEGOTIATION_CONFIRMATION_PARAMETERS structure


## -description


<div class="alert"><b>Important</b>  The <a href="https://msdn.microsoft.com/library/windows/hardware/ff560689">Native 802.11 Wireless LAN</a> interface is deprecated in Windows 10 and later. Please use the WLAN Device Driver Interface (WDI) instead. For more information about WDI, see <a href="https://msdn.microsoft.com/6EF92E34-7BC9-465E-B05D-2BCB29165A18">WLAN Universal Windows driver model</a>.</div><div> </div>The parameters for a received Group Owner (GO) negotiation confirmation are specified in a <b>DOT11_RECEIVED_GO_NEGOTIATION_CONFIRMATION_PARAMETERS</b> structure. This structure is sent with an <a href="https://msdn.microsoft.com/library/windows/hardware/hh439787">NDIS_STATUS_DOT11_WFD_RECEIVED_GO_NEGOTIATION_CONFIRMATION</a> indication.


## -syntax


````
typedef struct _DOT11_RECEIVED_GO_NEGOTIATION_CONFIRMATION_PARAMETERS {
  NDIS_OBJECT_HEADER Header;
  DOT11_MAC_ADDRESS  PeerDeviceAddress;
  DOT11_DIALOG_TOKEN DialogToken;
  ULONG              uIEsOffset;
  ULONG              uIEsLength;
} DOT11_RECEIVED_GO_NEGOTIATION_CONFIRMATION_PARAMETERS, *PDOT11_RECEIVED_GO_NEGOTIATION_CONFIRMATION_PARAMETERS;
````


## -struct-fields




### -field Header

The type, revision, and size of the <b>DOT11_RECEIVED_GO_NEGOTIATION_CONFIRMATION_PARAMETERS</b> structure. The required settings for the members of <b>Header</b> are the following.

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
<td>DOT11_RECEIVED_GO_NEGOTIATION_CONFIRMATION_PARAMETERS_REVISION_1</td>
</tr>
<tr>
<td><b>Size</b></td>
<td>DOT11_SIZEOF_RECEIVED_GO_NEGOTIATION_CONFIRMATION_PARAMETERS_REVISION_1</td>
</tr>
</table>
 


### -field PeerDeviceAddress

The Peer-to-Peer (P2P) device address of the Wi-Fi Direct (WFD) device that sent the GO negotiation confirmation.


### -field DialogToken

The dialog token received in the GO negotiation confirmation packet.


### -field uIEsOffset

The offset, in bytes,  of the array of additional information elements (IEs) received in the GO negotiation confirmation packet. This offset is from the start of the buffer that contains this structure.


### -field uIEsLength

The length, in bytes, of the array of IEs provided at <b>uIEsOffset</b>.


## -see-also

<a href="https://msdn.microsoft.com/library/windows/hardware/hh439787">NDIS_STATUS_DOT11_WFD_RECEIVED_GO_NEGOTIATION_CONFIRMATION</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20DOT11_RECEIVED_GO_NEGOTIATION_CONFIRMATION_PARAMETERS structure%20 RELEASE:%20(2/16/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

