---
UID: NF:ucmucsippm.UcmUcsiPpmSetUcsiCommandRequestQueue
title: UcmUcsiPpmSetUcsiCommandRequestQueue function (ucmucsippm.h)
tech.root: usbref
description: Provides a framework queue object that is used to dispatch UCSI commands to the client driver.
ms.assetid: 6f3d5025-84ec-484a-aa88-e4ac86118c73
ms.date: 09/30/2018
keywords: ["UcmUcsiPpmSetUcsiCommandRequestQueue function"]
f1_keywords:
 - "ucmucsippm/UcmUcsiPpmSetUcsiCommandRequestQueue"
ms.keywords: UcmUcsiPpmSetUcsiCommandRequestQueue
req.header: Ucmucsippm.h
req.include-header: UcmUcsiCx.h
req.target-type:
req.target-min-winverclnt:
req.target-min-winversvr:
req.kmdf-ver: 1.27
req.umdf-ver: N/A
req.lib: UcmUcsiCxStub.lib
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
- UcmUcsiCxStub.lib
api_name: 
- UcmUcsiPpmSetUcsiCommandRequestQueue
product:
- Windows
targetos: Windows


ms.custom: RS5
---

# UcmUcsiPpmSetUcsiCommandRequestQueue function


## -description

Provides a framework queue object that is used to dispatch UCSI commands to the client driver.

## -parameters

### -param PpmObject [in]
A handle to a Platform Policy Manager (PPM) object that the client driver received in the previous call to [**UcmUcsiPpmCreate**](nf-ucmucsippm-ucmucsippmcreate.md).

### -param PpmRequestQueue [in]
A WDFQUEUE handle that the client driver in a previous call to [**WdfIoQueueCreate**](../wdfio/nf-wdfio-wdfioqueuecreate.md)

## -remarks
The client driver is expected to call UcmUcsiPpmSetUcsiCommandRequestQueue after calling  [**UcmUcsiPpmCreate**](nf-ucmucsippm-ucmucsippmcreate.md) and before [**UcmUcsiPpmStart**](nf-ucmucsippm-ucmucsippmstart.md).  

## -see-also
