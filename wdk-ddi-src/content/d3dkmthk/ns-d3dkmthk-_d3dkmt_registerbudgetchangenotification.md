---
UID: NS:d3dkmthk._D3DKMT_REGISTERBUDGETCHANGENOTIFICATION
title: _D3DKMT_REGISTERBUDGETCHANGENOTIFICATION (d3dkmthk.h)
description: Used to register budget change notification.
ms.date: 10/19/2018
keywords: ["D3DKMT_REGISTERBUDGETCHANGENOTIFICATION structure"]
ms.keywords: _D3DKMT_REGISTERBUDGETCHANGENOTIFICATION, D3DKMT_REGISTERBUDGETCHANGENOTIFICATION,
req.header: d3dkmthk.h
req.include-header: 
req.target-type: 
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.lib: 
req.dll: 
req.ddi-compliance: 
req.unicode-ansi: 
req.max-support: 
req.typenames: D3DKMT_REGISTERBUDGETCHANGENOTIFICATION
targetos: Windows
ms.custom: RS5
tech.root: display
f1_keywords:
 - _D3DKMT_REGISTERBUDGETCHANGENOTIFICATION
 - d3dkmthk/_D3DKMT_REGISTERBUDGETCHANGENOTIFICATION
 - D3DKMT_REGISTERBUDGETCHANGENOTIFICATION
 - d3dkmthk/D3DKMT_REGISTERBUDGETCHANGENOTIFICATION
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - d3dkmthk.h
api_name:
 - _D3DKMT_REGISTERBUDGETCHANGENOTIFICATION
dev_langs:
 - c++
---

# _D3DKMT_REGISTERBUDGETCHANGENOTIFICATION structure


## -description

Used to register budget change notification.

## -struct-fields

### -field hDevice

[in] A handle to the device.

### -field Callback

[in] Pointer to the [PFND3DKMT_BUDGETCHANGENOTIFICATIONCALLBACK](nc-d3dkmthk-pfnd3dkmt_budgetchangenotificationcallback.md) callback.

### -field Context

[in] The callback context.

### -field Handle

 
[out] A handle to unregister.

## -remarks

## -see-also

