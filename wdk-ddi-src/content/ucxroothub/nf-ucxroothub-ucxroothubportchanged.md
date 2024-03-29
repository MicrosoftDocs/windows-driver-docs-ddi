---
UID: NF:ucxroothub.UcxRootHubPortChanged
title: UcxRootHubPortChanged function (ucxroothub.h)
description: Notifies UCX about a new port change event on the host controller.
old-location: buses\_ucxroothubportchanged.htm
tech.root: usbref
ms.date: 05/07/2018
keywords: ["UcxRootHubPortChanged function"]
ms.keywords: UcxRootHubPortChanged, UcxRootHubPortChanged method [Buses], buses._ucxroothubportchanged, ucxroothub/UcxRootHubPortChanged
req.header: ucxroothub.h
req.include-header: Ucxclass.h
req.target-type: Windows
req.target-min-winverclnt: Windows 10
req.target-min-winversvr: 
req.kmdf-ver: 1.0
req.umdf-ver: 2.0
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: <=DISPATCH_LEVEL
targetos: Windows
req.typenames: 
f1_keywords:
 - UcxRootHubPortChanged
 - ucxroothub/UcxRootHubPortChanged
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - COM
api_location:
 - ucxroothub.h
api_name:
 - UcxRootHubPortChanged
---

# UcxRootHubPortChanged function


## -description

Notifies UCX about a new port change event on the host controller.

## -parameters

### -param UcxRootHub [in]


A handle to the root hub object. The client driver retrieved the handle in a previous call to <a href="/previous-versions/windows/hardware/drivers/mt188048(v=vs.85)">UcxRootHubCreate</a>.

## -remarks

This method causes interrupt transfers to be sent to the host controller. UCX invokes the client driver's implementation of the <a href="/windows-hardware/drivers/ddi/ucxroothub/nc-ucxroothub-evt_ucx_roothub_interrupt_tx">EVT_UCX_ROOTHUB_INTERRUPT_TX</a> event callback.

## -see-also

<a href="/previous-versions/windows/hardware/drivers/mt188048(v=vs.85)">UcxRootHubCreate</a>
