---
UID: NS:iscsimgt._PingIPAddress_IN
title: "_PingIPAddress_IN"
author: windows-driver-content
description: The PingIPAddress_IN structure holds the input data for the PingIPAddress method.
old-location: storage\pingipaddress_in.htm
old-project: storage
ms.assetid: 2dec9594-727e-44e6-8be8-2416ea77e447
ms.author: windowsdriverdev
ms.date: 1/10/2018
ms.keywords: storage.pingipaddress_in, PingIPAddress_IN structure [Storage Devices], structs-iSCSI_4b2a763e-bb28-4132-9f29-08377e81dd82.xml, PPingIPAddress_IN, PPingIPAddress_IN structure pointer [Storage Devices], iscsimgt/PingIPAddress_IN, *PPingIPAddress_IN, PingIPAddress_IN, iscsimgt/PPingIPAddress_IN, _PingIPAddress_IN
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: iscsimgt.h
req.include-header: Iscsimgt.h
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
-	iscsimgt.h
apiname:
-	PingIPAddress_IN
product: Windows
targetos: Windows
req.typenames: "*PPingIPAddress_IN, PingIPAddress_IN"
---

# _PingIPAddress_IN structure


## -description


The PingIPAddress_IN structure holds the input data for the PingIPAddress method.


## -syntax


````
typedef struct _PingIPAddress_IN {
  ULONG            RequestCount;
  ULONG            RequestSize;
  ULONG            Timeout;
  ISCSI_IP_Address Address;
} PingIPAddress_IN, *PPingIPAddress_IN;
````


## -struct-fields




### -field RequestCount

The number of ping requests to be sent to the specified IP address.


### -field RequestSize

The size of each request (in bytes) to be sent.


### -field Timeout

The timeout (in milliseconds) for each ping request.


### -field Address

The IP address to which the ping request must be sent. The IP address is provided by the <a href="..\iscsidef\ns-iscsidef-_iscsi_ip_address.md">ISCSI_IP_Address</a> structure.


## -remarks


We recommend that you implement this class.



## -see-also

<a href="..\iscsidef\ns-iscsidef-_iscsi_ip_address.md">ISCSI_IP_Address</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20PingIPAddress_IN structure%20 RELEASE:%20(1/10/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

