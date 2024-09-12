---
UID: NS:d3dkmthk._D3DKMT_UNPINDIRECTFLIPRESOURCES
title: D3DKMT_UNPINDIRECTFLIPRESOURCES (d3dkmthk.h)
description: Arguments used to unpin direct flip resources.
ms.date: 07/17/2024
req.header: d3dkmthk.h
req.include-header: 
req.target-type: 
req.target-min-winverclnt: Windows 8
req.target-min-winversvr: Windows Server 2012
req.kmdf-ver: 
req.umdf-ver: 
req.lib: 
req.dll: 
req.ddi-compliance: 
req.unicode-ansi: 
req.max-support: 
req.typenames: D3DKMT_UNPINDIRECTFLIPRESOURCES
targetos: Windows
ms.custom: RS5
tech.root: display
f1_keywords:
 - _D3DKMT_UNPINDIRECTFLIPRESOURCES
 - d3dkmthk/_D3DKMT_UNPINDIRECTFLIPRESOURCES
 - D3DKMT_UNPINDIRECTFLIPRESOURCES
 - d3dkmthk/D3DKMT_UNPINDIRECTFLIPRESOURCES
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - d3dkmthk.h
api_name:
 - _D3DKMT_UNPINDIRECTFLIPRESOURCES
 - D3DKMT_UNPINDIRECTFLIPRESOURCES
dev_langs:
 - c++
---

# D3DKMT_UNPINDIRECTFLIPRESOURCES structure

## -description

The **D3DKMT_UNPINDIRECTFLIPRESOURCES** structure contains arguments used to unpin direct flip resources.

## -struct-fields

### -field hDevice [in]

A handle to the device.

### -field ResourceCount [in]

The number of resources to unpin.

### -field pResourceList [in]

An array of resource handles to unpin.

## -remarks

## -see-also
