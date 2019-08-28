---
UID: NF:netrequestqueue.NET_REQUEST_QUEUE_CONFIG_INIT_DEFAULT_SEQUENTIAL
title: NET_REQUEST_QUEUE_CONFIG_INIT_DEFAULT_SEQUENTIAL function (netrequestqueue.h)
description: Initializes a caller-allocated NET_REQUEST_QUEUE_CONFIG structure to create a default sequential request queue for normal control requests (OIDs).
tech.root: netvista
ms.assetid: cee1dccc-cbe6-49ca-b640-01dd7c0192b0
ms.date: 02/09/2018
ms.topic: function
f1_keywords:
 - "netrequestqueue/NET_REQUEST_QUEUE_CONFIG_INIT_DEFAULT_SEQUENTIAL"
ms.keywords: NET_REQUEST_QUEUE_CONFIG_INIT_DEFAULT_SEQUENTIAL
req.header: netrequestqueue.h
req.include-header:
req.target-type: Universal
req.target-min-winverclnt:
req.target-min-winversvr:
req.kmdf-ver: 1.21
req.umdf-ver:
req.lib:
req.dll:
req.irql: PASSIVE_LEVEL
req.ddi-compliance:
req.unicode-ansi:
req.idl:
req.max-support:
req.namespace:
req.assembly:
req.type-library: 
req.alt-api:
req.alt-loc:
topic_type: 
- apiref
api_type: 
- HeaderDef
api_location:
- netrequestqueue.h
api_name: 
- NET_REQUEST_QUEUE_CONFIG_INIT_DEFAULT_SEQUENTIAL
targetos: Windows
product:
- Windows
---

# NET_REQUEST_QUEUE_CONFIG_INIT_DEFAULT_SEQUENTIAL function


## -description

> [!WARNING]
> Some information in this topic relates to prereleased product, which may be substantially modified before it's commercially released. Microsoft makes no warranties, express or implied, with respect to the information provided here.
>
> NetAdapterCx is preview only in Windows 10, version 1903.

Initializes a caller-allocated [NET_REQUEST_QUEUE_CONFIG](ns-netrequestqueue-_net_request_queue_config.md) structure to create a default sequential request queue for normal control requests (OIDs).

## -parameters

### -param NetRequestQueueConfig
A pointer to a driver-allocated [NET_REQUEST_QUEUE_CONFIG](ns-netrequestqueue-_net_request_queue_config.md) structure.

### -param Adapter
The net adapter object that the client created in a prior call to [NetAdapterCreate](../netadapter/nf-netadapter-netadaptercreate.md).

## -returns
This method does not return a value.

## -remarks


## -see-also
