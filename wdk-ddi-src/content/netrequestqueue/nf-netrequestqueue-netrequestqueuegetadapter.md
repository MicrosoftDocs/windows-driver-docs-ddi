---
UID: NF:netrequestqueue.NetRequestQueueGetAdapter
title: NetRequestQueueGetAdapter function
author: windows-driver-content
description: Retrieves the NETADAPTER object corresponding to a NETREQUESTQUEUE.
tech.root: netvista
ms.assetid: 638f5dea-d79b-41bb-967b-27339bfae3ab
ms.author: windowsdriverdev
ms.date: 02/09/2018
ms.topic: function
ms.keywords: NetRequestQueueGetAdapter
req.header: netrequestqueue.h
req.include-header: netadaptercx.h
req.target-type: Universal
req.target-min-winverclnt:
req.target-min-winversvr:
req.kmdf-ver: 1.21
req.umdf-ver:
req.lib:
req.dll:
req.irql: <= DISPATCH_LEVEL
req.ddi-compliance:
req.unicode-ansi:
req.idl:
req.max-support:
req.namespace:
req.assembly:
req.type-library: 
req.alt-api:
req.alt-loc:
topictype: 
-	apiref
apitype: 
-	HeaderDef
apilocation: 
-	netrequestqueue.h
apiname: 
-	NetRequestQueueGetAdapter
product:
-	Windows
targetos: Windows
product:
- Windows
---

# NetRequestQueueGetAdapter function


## -description

> [!WARNING]
> Some information in this topic relates to prereleased product, which may be substantially modified before it's commercially released. Microsoft makes no warranties, express or implied, with respect to the information provided here.
>
> NetAdapterCx is preview only in Windows 10, version 1809.

Retrieves the NETADAPTER object corresponding to a NETREQUESTQUEUE.

## -parameters

### -param NetRequestQueue
A handle to the NETREQUESTQUEUE object.

## -returns
Returns the net adapter object that the client created in a prior call to [NetAdapterCreate](../netadapter/nf-netadapter-netadaptercreate.md).

## -remarks


## -see-also
