---
UID: NF:ucmucsippm.UcmUcsiPpmNotification
title: UcmUcsiPpmNotification function (ucmucsippm.h)
tech.root: usbref
description: Informs the UcmUcsiCx class extension about a UCSI notification.
ms.date: 09/30/2018
keywords: ["UcmUcsiPpmNotification function"]
ms.keywords: UcmUcsiPpmNotification
req.header: ucmucsippm.h
req.include-header: UcmUcsiCx.h
req.target-type: 
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 1.27
req.umdf-ver: N/A
req.lib: UcmUcsiCxStub.lib
req.dll: 
req.irql: <=DISPATCH_LEVEL
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
targetos: Windows
ms.custom: RS5
f1_keywords:
 - UcmUcsiPpmNotification
 - ucmucsippm/UcmUcsiPpmNotification
topic_type:
 - apiref
api_type:
 - LibDef
api_location:
 - UcmUcsiCxStub.lib
api_name:
 - UcmUcsiPpmNotification
---

# UcmUcsiPpmNotification function


## -description

Informs the UcmUcsiCx class extension about a UCSI notification.

## -parameters

### -param PpmObject [in]

A handle to a Platform Policy Manager (PPM) object that the client driver received in the previous call to [**UcmUcsiPpmCreate**](nf-ucmucsippm-ucmucsippmcreate.md).

### -param DataBlock [in]

A pointer to a [**UCSI_DATA_BLOCK**] structure that contains information about the USCI notification.

## -remarks

The client driver calls UcmUcsiPpmNotification in the event of a UCSI notification. The driver must not call more than one instance of this function at the same time to avoid a race condition.  

The client driver should assume that the driver can receive a request before this call returns. Hence, if it keeps a lock around this function and the same lock around handling a request, it will result into a deadlock.

## -see-also

