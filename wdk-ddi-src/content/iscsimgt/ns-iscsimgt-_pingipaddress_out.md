---
UID: NS:iscsimgt._PingIPAddress_OUT
title: "_PingIPAddress_OUT"
author: windows-driver-content
description: The PingIPAddress_OUT structure holds the output data for the PingIPAddress method.
old-location: storage\pingipaddress_out.htm
old-project: storage
ms.assetid: 26512dc5-9d3d-4dd5-bce3-37feb64dded8
ms.author: windowsdriverdev
ms.date: 2/24/2018
ms.keywords: "*PPingIPAddress_OUT, PPingIPAddress_OUT, PPingIPAddress_OUT structure pointer [Storage Devices], PingIPAddress_OUT, PingIPAddress_OUT structure [Storage Devices], _PingIPAddress_OUT, iscsimgt/PPingIPAddress_OUT, iscsimgt/PingIPAddress_OUT, storage.pingipaddress_out, structs-iSCSI_a6cbf3cf-b386-4cab-9193-5b9724e4646e.xml"
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
-	PingIPAddress_OUT
product: Windows
targetos: Windows
req.typenames: PingIPAddress_OUT, *PPingIPAddress_OUT
---

# _PingIPAddress_OUT structure


## -description


The PingIPAddress_OUT structure holds the output data for the PingIPAddress method.


## -syntax


````
typedef struct _PingIPAddress_OUT {
  ULONG Status;
  ULONG ResponsesReceived;
} PingIPAddress_OUT, *PPingIPAddress_OUT;
````


## -struct-fields




### -field Status

A status of type ISDSC_ERROR.


### -field ResponsesReceived

The number of responses that were received.


## -remarks



We recommend that you implement this class.



