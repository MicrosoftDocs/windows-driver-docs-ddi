---
UID: NF:netadapter.NetAdapterDriverWdmGetHandle
title: NetAdapterDriverWdmGetHandle function
author: windows-driver-content
description: A WDF client driver calls NetAdapterDriverWdmGetHandle to get a handle that can be used to call NDIS APIs.
ms.assetid: ca8d396d-aa0e-4761-bc2d-068e28169301
ms.author: windowsdriverdev
ms.date: 02/06/2018
ms.topic: function
ms.keywords: NetAdapterDriverWdmGetHandle
req.header: netadapter.h
req.include-header: netadaptercx.h
req.target-type: Universal
req.target-min-winverclnt:
req.target-min-winversvr:
req.kmdf-ver: 1.23
req.umdf-ver:
req.lib: NetAdapterCxStub.lib
req.dll:
req.irql: "<= DISPATCH_LEVEL"
req.ddi-compliance:
req.unicode-ansi:
req.idl:
req.max-support:
req.namespace:
req.assembly:
req.type-library: 
req.alt-api:
req.alt-loc:
req.typenames: NetAdapterDriverWdmGetHandle
topictype: 
-	apiref
apitype: 
-	HeaderDef
apilocation: 
-	netadapter.h
apiname: 
-	NetAdapterDriverWdmGetHandle
product:
-	Windows
targetos: Windows
req.product: Windows 10 or later.
---

# NetAdapterDriverWdmGetHandle function


## -description

> [!WARNING]
> Some information in this topic relates to prereleased product, which may be substantially modified before it's commercially released. Microsoft makes no warranties, express or implied, with respect to the information provided here.
>
> NetAdapterCx is preview only in Windows 10, version 1803.

A WDF client driver calls **NetAdapterDriverWdmGetHandle** to get a handle that can be used to call NDIS APIs.

## -parameters

### -param Driver
A handle to the driver's framework driver object, obtained from a previous call to [WdfDriverCreate](../wdfdriver/nf-wdfdriver-wdfdrivercreate.md).

## -returns
**NetAdapterDriverWdmGetHandle** returns a WDM handle to the client driver. The framework's verifier reports an error if no corresponding WDM handle exists.

## -remarks
The driver must have previously called [NetAdapterCreate](nf-netadapter-netadaptercreate.md).



## -see-also