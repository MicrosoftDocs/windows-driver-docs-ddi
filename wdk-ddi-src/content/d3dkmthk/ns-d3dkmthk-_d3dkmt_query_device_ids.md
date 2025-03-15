---
UID: NS:d3dkmthk._D3DKMT_QUERY_DEVICE_IDS
title: D3DKMT_QUERY_DEVICE_IDS (d3dkmthk.h)
description: Used to query for device IDs.
ms.date: 10/19/2018
keywords: ["D3DKMT_QUERY_DEVICE_IDS structure"]
ms.keywords: _D3DKMT_QUERY_DEVICE_IDS, D3DKMT_QUERY_DEVICE_IDS,
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
req.typenames: D3DKMT_QUERY_DEVICE_IDS
targetos: Windows
ms.custom: RS5
tech.root: display
f1_keywords:
 - _D3DKMT_QUERY_DEVICE_IDS
 - d3dkmthk/_D3DKMT_QUERY_DEVICE_IDS
 - D3DKMT_QUERY_DEVICE_IDS
 - d3dkmthk/D3DKMT_QUERY_DEVICE_IDS
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - d3dkmthk.h
api_name:
 - _D3DKMT_QUERY_DEVICE_IDS
 - D3DKMT_QUERY_DEVICE_IDS
dev_langs:
 - c++
---

# D3DKMT_QUERY_DEVICE_IDS structure

## -description

The **D3DKMT_QUERY_DEVICE_IDS** structure is used to query for device IDs.

## -struct-fields

### -field PhysicalAdapterIndex

[in] The physical adapter index in the LDA (linked display adapter) chain.

### -field DeviceIds

[out] A [**D3DKMT_DEVICE_IDS**](ns-d3dkmthk-_d3dkmt_device_ids.md) structure that contains IDs associated with the device.

## -see-also

[**D3DKMTQueryAdapterInfo**](nf-d3dkmthk-d3dkmtqueryadapterinfo.md)
