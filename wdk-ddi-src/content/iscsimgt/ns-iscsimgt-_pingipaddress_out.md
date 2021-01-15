---
UID: NS:iscsimgt._PingIPAddress_OUT
title: _PingIPAddress_OUT (iscsimgt.h)
description: The PingIPAddress_OUT structure holds the output data for the PingIPAddress method.
old-location: storage\pingipaddress_out.htm
tech.root: storage
ms.date: 03/29/2018
keywords: ["PingIPAddress_OUT structure"]
ms.keywords: "*PPingIPAddress_OUT, PPingIPAddress_OUT, PPingIPAddress_OUT structure pointer [Storage Devices], PingIPAddress_OUT, PingIPAddress_OUT structure [Storage Devices], _PingIPAddress_OUT, iscsimgt/PPingIPAddress_OUT, iscsimgt/PingIPAddress_OUT, storage.pingipaddress_out, structs-iSCSI_a6cbf3cf-b386-4cab-9193-5b9724e4646e.xml"
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
targetos: Windows
req.typenames: PingIPAddress_OUT, *PPingIPAddress_OUT
f1_keywords:
 - _PingIPAddress_OUT
 - iscsimgt/_PingIPAddress_OUT
 - PPingIPAddress_OUT
 - iscsimgt/PPingIPAddress_OUT
 - PingIPAddress_OUT
 - iscsimgt/PingIPAddress_OUT
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - iscsimgt.h
api_name:
 - _PingIPAddress_OUT
 - PPingIPAddress_OUT
 - PingIPAddress_OUT
---

# _PingIPAddress_OUT structure


## -description

The PingIPAddress_OUT structure holds the output data for the PingIPAddress method.

## -struct-fields

### -field Status

A status of type ISDSC_ERROR.

### -field ResponsesReceived

The number of responses that were received.

## -remarks

We recommend that you implement this class.

