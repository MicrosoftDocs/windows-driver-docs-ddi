---
UID: NS:windot11._DOT11_INCOMING_ASSOC_REQUEST_RECEIVED_PARAMETERS
title: "_DOT11_INCOMING_ASSOC_REQUEST_RECEIVED_PARAMETERS"
author: windows-driver-content
description: Important  The Native 802.11 Wireless LAN interface is deprecated in Windows 10 and later.
old-location: netvista\dot11_incoming_assoc_request_received_parameters.htm
old-project: netvista
ms.assetid: bd65cac6-ca53-46fc-943f-0f698c531554
ms.author: windowsdriverdev
ms.date: 1/18/2018
ms.keywords: PDOT11_INCOMING_ASSOC_REQUEST_RECEIVED_PARAMETERS, netvista.dot11_incoming_assoc_request_received_parameters, Native_802.11_data_types_00b02485-5af1-4945-a902-cceb1ac2e345.xml, windot11/DOT11_INCOMING_ASSOC_REQUEST_RECEIVED_PARAMETERS, PDOT11_INCOMING_ASSOC_REQUEST_RECEIVED_PARAMETERS structure pointer [Network Drivers Starting with Windows Vista], DOT11_INCOMING_ASSOC_REQUEST_RECEIVED_PARAMETERS, windot11/PDOT11_INCOMING_ASSOC_REQUEST_RECEIVED_PARAMETERS, _DOT11_INCOMING_ASSOC_REQUEST_RECEIVED_PARAMETERS, *PDOT11_INCOMING_ASSOC_REQUEST_RECEIVED_PARAMETERS, DOT11_INCOMING_ASSOC_REQUEST_RECEIVED_PARAMETERS structure [Network Drivers Starting with Windows Vista]
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: windot11.h
req.include-header: Ndis.h
req.target-type: Windows
req.target-min-winverclnt: Available in Windows 7 and later versions of the Windows operating   systems.
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	windot11.h
apiname:
-	DOT11_INCOMING_ASSOC_REQUEST_RECEIVED_PARAMETERS
product: Windows
targetos: Windows
req.typenames: "*PDOT11_INCOMING_ASSOC_REQUEST_RECEIVED_PARAMETERS, DOT11_INCOMING_ASSOC_REQUEST_RECEIVED_PARAMETERS"
req.product: Windows 10 or later.
---

# _DOT11_INCOMING_ASSOC_REQUEST_RECEIVED_PARAMETERS structure


## -description


<div class="alert"><b>Important</b>  The <a href="https://msdn.microsoft.com/library/windows/hardware/ff560689">Native 802.11 Wireless LAN</a> interface is deprecated in Windows 10 and later. Please use the WLAN Device Driver Interface (WDI) instead. For more information about WDI, see <a href="https://msdn.microsoft.com/6EF92E34-7BC9-465E-B05D-2BCB29165A18">WLAN Universal Windows driver model</a>.</div><div> </div>The DOT11_INCOMING_ASSOC_REQUEST_RECEIVED_PARAMETERS structure specifies the results of the
  acceptance procedure of the 802.11 station after it receives an incoming association request, or
  re-association request, from a peer station on an infrastructure BSS.


## -syntax


````
typedef struct _DOT11_INCOMING_ASSOC_REQUEST_RECEIVED_PARAMETERS {
  NDIS_OBJECT_HEADER Header;
  DOT11_MAC_ADDRESS  PeerMacAddr;
  BOOLEAN            bReAssocReq;
  ULONG              uAssocReqOffset;
  ULONG              uAssocReqSize;
} DOT11_INCOMING_ASSOC_REQUEST_RECEIVED_PARAMETERS, *PDOT11_INCOMING_ASSOC_REQUEST_RECEIVED_PARAMETERS;
````


## -struct-fields




### -field Header

The type, revision, and size of the DOT11_INCOMING_ASSOC_REQUEST_RECEIVED_PARAMETERS structure.
     This member is formatted as an 
     <a href="..\ntddndis\ns-ntddndis-_ndis_object_header.md">NDIS_OBJECT_HEADER</a> structure.
     

The miniport driver must set the members of 
     <b>Header</b> to the following values:





#### Type

This member must be set to NDIS_OBJECT_TYPE_DEFAULT.



#### Revision

This member must be set to DOT11_INCOMING_ASSOC_REQUEST_RECEIVED_PARAMETERS_REVISION_1.



#### Size

This member must be set to 
       <b>sizeof</b>(DOT11_INCOMING_ASSOC_REQUEST_RECEIVED_PARAMETERS).

For more information about these members, see 
     <a href="..\ntddndis\ns-ntddndis-_ndis_object_header.md">NDIS_OBJECT_HEADER</a>.


### -field PeerMacAddr

The media access control (MAC) address of the peer station that sent an association
     request.


### -field bReAssocReq

For nonzero values of 
     <b>uStatus</b>, 
     <b>bReAssocReq</b> is <b>TRUE</b> if the request from the peer station is a re-association request.


### -field uAssocReqOffset

For nonzero values of 
     <b>uStatus</b>, this member specifies the offset of the request frame that is used in the association
     operation. The frame includes information elements (IEs) but does not include the 802.11 MAC
     header.


### -field uAssocReqSize

For nonzero values of 
     <b>uStatus</b>, this member specifies the length, in bytes, of the request frame that is used in the
     association operation. The frame includes information elements (IEs) but does not include the 802.11 MAC
     header.


## -remarks



The Native 802.11 miniport driver includes a DOT11_INCOMING_ASSOC_REQUEST_RECEIVED_PARAMETERS
    structure when the driver makes an 
    <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/network/ndis-status-dot11-incoming-assoc-request-received">
    NDIS_STATUS_DOT11_INCOMING_ASSOC_REQUEST_RECEIVED</a> status indication.




## -see-also

<a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/network/ndis-status-dot11-incoming-assoc-request-received">
   NDIS_STATUS_DOT11_INCOMING_ASSOC_REQUEST_RECEIVED</a>



<a href="..\ntddndis\ns-ntddndis-_ndis_object_header.md">NDIS_OBJECT_HEADER</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20DOT11_INCOMING_ASSOC_REQUEST_RECEIVED_PARAMETERS structure%20 RELEASE:%20(1/18/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

