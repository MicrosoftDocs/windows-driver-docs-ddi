---
UID: NS:1394._IRB_REQ_BUS_RESET
title: _IRB_REQ_BUS_RESET
author: windows-driver-content
description: This structure contains the fields necessary for the 1394 bus driver to create a bus reset request.
old-location: ieee\irb_req_bus_reset.htm
old-project: IEEE
ms.assetid: 56B7D001-2EC3-4397-B520-193CCF52A9EE
ms.author: windowsdriverdev
ms.date: 12/14/2017
ms.keywords: _IRB_REQ_BUS_RESET, IRB_REQ_BUS_RESET
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: 1394.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: IRB_REQ_BUS_RESET
req.alt-loc: 1394.h
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
req.typenames: IRB_REQ_BUS_RESET
---

# _IRB_REQ_BUS_RESET structure



## -description
This structure contains the fields necessary for the 1394 bus driver to create a bus reset request.



## -syntax

````
typedef struct _IRB_REQ_BUS_RESET {
  ULONG fulFlags;
} IRB_REQ_BUS_RESET;
````


## -struct-fields

### -field fulFlags

Set this flag to BUS_RESET_FLAGS_FORCE_ROOT to make the local node the root node. All other values indicate that the node is not root.


## -remarks
