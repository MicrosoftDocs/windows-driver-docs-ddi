---
UID: NF:netadapter.NetAdapterStart
title: NetAdapterStart function
author: windows-driver-content
description: The NetAdapterStart method starts a NETADAPTER object.
ms.assetid: 7fd514f2-7f1e-449f-9037-636f1c3599d6
ms.author: windowsdriverdev
ms.date: 08/03/2018
ms.topic: function
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
topictype: 
-	apiref
apitype: 
-	LibDef
apilocation: 
-	netadaptercxstub.lib
apiname: 
-	NetAdapterStart
product:
-	Windows
targetos: Windows

---

# NetAdapterStart function

## -description
> [!WARNING]
> Some information in this topic relates to prereleased product, which may be substantially modified before it's commercially released. Microsoft makes no warranties, express or implied, with respect to the information provided here.
>
> NetAdapterCx is preview only in Windows 10, version 1803.

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