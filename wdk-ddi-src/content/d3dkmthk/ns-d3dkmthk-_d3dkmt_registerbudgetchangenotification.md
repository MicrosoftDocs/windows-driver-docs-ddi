---
UID: NS:d3dkmthk._D3DKMT_REGISTERBUDGETCHANGENOTIFICATION
title: _D3DKMT_REGISTERBUDGETCHANGENOTIFICATION
author: windows-driver-content
description: Used to register budget change notification.
ms.assetid: b68c9dc0-56e6-478c-8624-b4904cedd311
ms.date: 10/19/2018
ms.topic: struct
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
topic_type: 
-	apiref
api_type: 
-	HeaderDef
api_location: 
-	d3dkmthk.h
api_name: 
-	_D3DKMT_REGISTERBUDGETCHANGENOTIFICATION
product:
-	Windows
targetos: Windows
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
