---
UID: NS:iscsimgt._PingIPAddress_IN
title: _PingIPAddress_IN (iscsimgt.h)
description: The PingIPAddress_IN structure holds the input data for the PingIPAddress method.
old-location: storage\pingipaddress_in.htm
tech.root: storage
ms.assetid: 2dec9594-727e-44e6-8be8-2416ea77e447
ms.date: 03/29/2018
keywords: ["PingIPAddress_IN structure"]
ms.keywords: "*PPingIPAddress_IN, PPingIPAddress_IN, PPingIPAddress_IN structure pointer [Storage Devices], PingIPAddress_IN, PingIPAddress_IN structure [Storage Devices], _PingIPAddress_IN, iscsimgt/PPingIPAddress_IN, iscsimgt/PingIPAddress_IN, storage.pingipaddress_in, structs-iSCSI_4b2a763e-bb28-4132-9f29-08377e81dd82.xml"
f1_keywords:
 - "iscsimgt/PingIPAddress_IN"
 - "PingIPAddress_IN"
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
topic_type:
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- iscsimgt.h
api_name:
- PingIPAddress_IN
targetos: Windows
req.typenames: PingIPAddress_IN, *PPingIPAddress_IN
---

# _PingIPAddress_IN structure


## -description


The PingIPAddress_IN structure holds the input data for the PingIPAddress method.


## -struct-fields




### -field RequestCount

The number of ping requests to be sent to the specified IP address.


### -field RequestSize

The size of each request (in bytes) to be sent.


### -field Timeout

The timeout (in milliseconds) for each ping request.


### -field Address

The IP address to which the ping request must be sent. The IP address is provided by the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/iscsidef/ns-iscsidef-_iscsi_ip_address">ISCSI_IP_Address</a> structure.


## -remarks



We recommend that you implement this class.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/iscsidef/ns-iscsidef-_iscsi_ip_address">ISCSI_IP_Address</a>
 

 

