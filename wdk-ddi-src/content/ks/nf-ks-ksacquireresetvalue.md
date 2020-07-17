---
UID: NF:ks.KsAcquireResetValue
title: KsAcquireResetValue function (ks.h)
description: The KsAcquireResetValue function retrieves the current reset state from an IOCTL_KS_RESET_STATE IRP.
old-location: stream\ksacquireresetvalue.htm
tech.root: stream
ms.assetid: 80a990e3-3637-4837-8800-42d5848e01cf
ms.date: 04/23/2018
keywords: ["KsAcquireResetValue function"]
ms.keywords: KsAcquireResetValue, KsAcquireResetValue function [Streaming Media Devices], ks/KsAcquireResetValue, ksfunc_fbfd5f64-6842-4559-9829-05797fda4fa2.xml, stream.ksacquireresetvalue
f1_keywords:
 - "ks/KsAcquireResetValue"
 - "KsAcquireResetValue"
req.header: ks.h
req.include-header: Ks.h
req.target-type: Universal
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Ks.lib
req.dll: 
req.irql: 
topic_type:
- APIRef
- kbSyntax
api_type:
- LibDef
api_location:
- Ks.lib
- Ks.dll
api_name:
- KsAcquireResetValue
product:
- Windows
targetos: Windows
req.typenames: 
---

# KsAcquireResetValue function


## -description


The <b>KsAcquireResetValue </b>function retrieves the current reset state from an IOCTL_KS_RESET_STATE IRP.


## -parameters




### -param Irp [in]

Points to the IRP from which to retrieve the reset state.


### -param ResetValue [out]

Points to a caller-allocated buffer, that on successful completion contains the reset value (KSRESET_BEGIN, KSRESET_END) associated with the IRP.


## -returns



The <b>KsAcquireResetValue </b>function returns STATUS_SUCCESS if the reset value was obtained.



