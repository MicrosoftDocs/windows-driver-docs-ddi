---
UID: NF:d3dkmthk.D3DKMTCreateHwQueue
title: D3DKMTCreateHwQueue function
author: windows-driver-content
description: Used to create a new hardware queue.
old-location: display\d3dkmtcreatehwqueue.htm
old-project: display
ms.assetid: FD4E892F-DDC6-449A-B77F-6C7F8240E467
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: D3DKMTCreateHwQueue
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: d3dkmthk.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: D3DKMTCreateHwQueue
req.alt-loc: d3dkmthk.h
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
req.typenames: D3DKMT_DRIVERVERSION
---

# D3DKMTCreateHwQueue function



## -description
Used to create a new hardware queue.



## -syntax

````
NTSTATUS D3DKMTCreateHwQueue(
  _Inout_ D3DKMT_CREATEHWQUEUE *createHwQueue
);
````


## -parameters

### -param createHwQueue [in, out]

A structure holding the information needed to create a new hardware queue.


## -returns
Returns STATUS_SUCCESS if called successfully. 


## -remarks
