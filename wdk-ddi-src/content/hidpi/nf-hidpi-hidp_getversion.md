---
UID: NF:hidpi.HidP_GetVersion
tech.root: hid
title: HidP_GetVersion
ms.date: 11/11/2021
targetos: Windows
description: The HidP_GetVersion function gets the version of the HID driver.
prerelease: false
req.assembly: 
req.construct-type: function
req.ddi-compliance: 
req.dll: 
req.header: hidpi.h
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
 - LibDef
api_location:
 - hidpi.h
api_name:
 - HidP_GetVersion
f1_keywords:
 - HidP_GetVersion
 - hidpi/HidP_GetVersion
dev_langs:
 - c++
---

## -description

The **HidP_GetVersion** function gets the version of the HID driver.

## -parameters

### -param Version [out]

The version of the HID driver.

## -returns

**HidP_GetVersion** returns STATUS_SUCCESS if the call was successful. Otherwise, it returns an [NTSTATUS](/windows-hardware/drivers/kernel/using-ntstatus-values) error code.

## -remarks

## -see-also
