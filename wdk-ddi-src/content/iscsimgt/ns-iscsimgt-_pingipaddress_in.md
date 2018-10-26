---
UID: NS:iscsimgt._PingIPAddress_IN
title: "_PingIPAddress_IN"
author: windows-driver-content
description: The PingIPAddress_IN structure holds the input data for the PingIPAddress method.
old-location: storage\pingipaddress_in.htm
tech.root: storage
ms.assetid: 2dec9594-727e-44e6-8be8-2416ea77e447
ms.date: 03/29/2018
ms.keywords: "*PPingIPAddress_IN, PPingIPAddress_IN, PPingIPAddress_IN structure pointer [Storage Devices], PingIPAddress_IN, PingIPAddress_IN structure [Storage Devices], _PingIPAddress_IN, iscsimgt/PPingIPAddress_IN, iscsimgt/PingIPAddress_IN, storage.pingipaddress_in, structs-iSCSI_4b2a763e-bb28-4132-9f29-08377e81dd82.xml"
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	iscsimgt.h
api_name:
-	PingIPAddress_IN
product:
- Windows
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

The IP address to which the ping request must be sent. The IP address is provided by the <a href="https://msdn.microsoft.com/library/windows/hardware/ff561536">ISCSI_IP_Address</a> structure.


## -remarks



We recommend that you implement this class.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff561536">ISCSI_IP_Address</a>
 

 

