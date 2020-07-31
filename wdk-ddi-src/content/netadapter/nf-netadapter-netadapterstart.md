---
UID: NF:netadapter.NetAdapterStart
title: NetAdapterStart function (netadapter.h)
description: The NetAdapterStart method starts a NETADAPTER object.
tech.root: netvista
ms.assetid: 7fd514f2-7f1e-449f-9037-636f1c3599d6
ms.date: 08/03/2018
keywords: ["NetAdapterStart function"]
f1_keywords:
 - "netadapter/NetAdapterStart"
 - "NetAdapterStart"
ms.keywords: NetAdapterStart
req.header: netadapter.h
req.include-header: netadaptercx.h
req.target-type: Universal
req.target-min-winverclnt:
req.target-min-winversvr:
req.kmdf-ver: 1.25
req.umdf-ver:
req.lib: netadaptercxstub.lib
req.dll:
req.irql: PASSIVE_LEVEL
req.ddi-compliance:
req.unicode-ansi:
req.idl:
req.max-support:
req.namespace:
req.assembly:
req.type-library: 
topic_type: 
- apiref
api_type: 
- LibDef
api_location:
- netadaptercxstub.lib
api_name: 
- NetAdapterStart
targetos: Windows

---

# NetAdapterStart function

## -description


The **NetAdapterStart** method starts a NETADAPTER object.

## -parameters

### -param Adapter
The **NETADAPTER** object created by a prior call to [**NetAdapterCreate**](nf-netadapter-netadaptercreate.md).

## -returns
The method returns STATUS_SUCCESS if the operation succeeds. Otherwise, this method may return an appropriate NTSTATUS error code.

## -remarks
For this method to succeed, the **NETADAPTER** object must have been previously created by calling [**NetAdapterCreate**](nf-netadapter-netadaptercreate.md).

## -see-also

[**NetAdapterCreate**](nf-netadapter-netadaptercreate.md)

[**NetAdapterStop**](nf-netadapter-netadapterstop.md)
