---
UID: NF:wdm.ExInitializeDriverRuntime
title: ExInitializeDriverRuntime
ms.date: 11/8/2019
ms.topic: language-reference
targetos: Windows
description: 
req.assembly: 
req.construct-type: function
req.ddi-compliance: 
req.dll: 
req.header: wdm.h
req.idl: 
req.include-header: 
req.irql: 
req.kmdf-ver: 
req.lib: 
req.max-support: 
req.namespace: 
req.redist: 
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.target-type: 
req.type-library: 
req.umdf-ver: 
req.unicode-ansi: 
topic_type:
 - apiref
api_type:
 - DllExport
api_location:
 - wdm.h
api_name:
 - ExInitializeDriverRuntime
f1_keywords:
 - ExInitializeDriverRuntime
 - wdm/ExInitializeDriverRuntime
dev_langs:
 - c++
---

## -description

POOL_NX_OPTIN allows device drivers to dynamically opt-in to making
non-paged pool allocations non-executable by default based on whether or not
this is supported by the version of the operating system.  Device drivers
must call ExInitializeDriverRuntime (DrvRtPoolNxOptIn) during driver
initialization to dynamically opt-in.  This opt-in method should be used by
drivers that are designed to run on versions of Windows that may or may not
support NX non-paged pool allocations.

## -parameters

### -param RuntimeFlags

## -remarks

## -see-also

[Single Binary Opt-In: POOL_NX_OPTIN](https://docs.microsoft.com/windows-hardware/drivers/kernel/single-binary-opt-in-pool-nx-optin)

