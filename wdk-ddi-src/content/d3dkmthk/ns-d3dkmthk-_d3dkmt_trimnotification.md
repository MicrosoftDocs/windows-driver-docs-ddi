---
UID: NS:d3dkmthk._D3DKMT_TRIMNOTIFICATION
title: _D3DKMT_TRIMNOTIFICATION (d3dkmthk.h)
description: D3DKMT_TRIMNOTIFICATION is used to notify a driver to trim its memory residency list.
old-location: display\d3dkmt_trimnotification.htm
ms.date: 05/10/2018
keywords: ["D3DKMT_TRIMNOTIFICATION structure"]
ms.keywords: D3DKMT_TRIMNOTIFICATION, D3DKMT_TRIMNOTIFICATION structure [Display Devices], _D3DKMT_TRIMNOTIFICATION, d3dkmthk/D3DKMT_TRIMNOTIFICATION, display.d3dkmt_trimnotification
req.header: d3dkmthk.h
req.include-header: D3dkmthk.h
req.target-type: Windows
req.target-min-winverclnt: Windows 10
req.target-min-winversvr: Windows Server 2016
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: 
targetos: Windows
tech.root: display
req.typenames: D3DKMT_TRIMNOTIFICATION
f1_keywords:
 - _D3DKMT_TRIMNOTIFICATION
 - d3dkmthk/_D3DKMT_TRIMNOTIFICATION
 - D3DKMT_TRIMNOTIFICATION
 - d3dkmthk/D3DKMT_TRIMNOTIFICATION
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - D3dkmthk.h
api_name:
 - _D3DKMT_TRIMNOTIFICATION
 - D3DKMT_TRIMNOTIFICATION
---

# _D3DKMT_TRIMNOTIFICATION structure


## -description

<b>D3DKMT_TRIMNOTIFICATION</b> is used to notify a driver to trim its memory residency list.

## -struct-fields

### -field Context [in]

The caller-supplied context for the callback notification.

### -field Flags [in]

A <a href="/windows-hardware/drivers/ddi/d3dukmdt/ns-d3dukmdt-d3dddi_trimresidencyset_flags">D3DDDI_TRIMRESIDENCYSET_FLAGS</a> structure containing the trimming behavior flags.

### -field NumBytesToTrim [in]

When <b>TrimToBudget</b> is set, this value specifies how much the application should evict in order to meet its current memory budget.

## -see-also

<a href="/windows-hardware/drivers/ddi/d3dukmdt/ns-d3dukmdt-d3dddi_trimresidencyset_flags">D3DDDI_TRIMRESIDENCYSET_FLAGS</a>

