---
UID: NS:61883._FCP_SEND_RESPONSE
title: "_FCP_SEND_RESPONSE"
author: windows-driver-content
description: This structure is used for a send response.
old-location: ieee\fcp_send_response.htm
old-project: IEEE
ms.assetid: 65C76CA1-F7F2-4DFD-B928-0595A137BF28
ms.author: windowsdriverdev
ms.date: 2/15/2018
ms.keywords: PFCP_SEND_RESPONSE structure pointer [Buses], _FCP_SEND_RESPONSE, FCP_SEND_RESPONSE structure [Buses], *PFCP_SEND_RESPONSE, 61883/FCP_SEND_RESPONSE, PFCP_SEND_RESPONSE, FCP_SEND_RESPONSE, 61883/PFCP_SEND_RESPONSE, IEEE.fcp_send_response
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: 61883.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: 
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
-	61883.h
apiname:
-	FCP_SEND_RESPONSE
product: Windows
targetos: Windows
req.typenames: FCP_SEND_RESPONSE, *PFCP_SEND_RESPONSE
---

# _FCP_SEND_RESPONSE structure


## -description


This structure is used for a send response. 

The request sends an FCP response to the device. The  request is used in conjunction with GetFcpRequest. A client driver should use SendFcpResponse to return an FCP response for a received FCP request. If the protocol driver is being used to represent a virtual device on the machine, the <b>NodeAddress</b> member from GetFcpRequest must be specified in the <b>NodeAddress</b> member of the FCP_SEND_RESPONSE structure. This information is required in order to route the response to the proper node on the 1394 bus.

If the protocol driver is being used to control a physical device, the 1394 bus driver determines the node address dynamically, and <b>NodeAddress</b> is not used. 


## -syntax


````
typedef struct _FCP_SEND_RESPONSE {
  NODE_ADDRESS NodeAddress;
  ULONG        Length;
  PFCP_FRAME   Frame;
} FCP_SEND_RESPONSE, *PFCP_SEND_RESPONSE;
````


## -struct-fields




### -field NodeAddress

On input, if the protocol driver is being used to control a virtual device, <b>NodeAddress</b> must contain the node address of the device that sent the FCP request obtained with GetFcpRequest so the 1394 bus driver can route the response to the correct device. 

If the protocol driver is being used to control a physical device, <b>NodeAddress</b> is not used.


### -field Length

On input, the length of the frame payload in bytes, including the FCP header.


### -field Frame

On input, a pointer to an <a href="https://msdn.microsoft.com/library/windows/hardware/ff537113">FCP_FRAME</a> structure that contains the FCP response to send to the device.


## -remarks



If successful, the IEC-61883 protocol driver sets <b>Irp-&gt;IoStatus.Status </b>to STATUS_SUCCESS. 

If an incorrect parameter is passed in, the protocol driver sets <b>Irp-&gt;IoStatus.Status </b>to STATUS_INVALID_PARAMETER.

If the protocol driver is unable to allocate resources, it sets <b>Irp-&gt;IoStatus.Status </b>to STATUS_INSUFFICIENT_RESOURCES.




## -see-also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff537008">AV_61883_REQUEST</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [IEEE\buses]:%20FCP_SEND_RESPONSE structure%20 RELEASE:%20(2/15/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

