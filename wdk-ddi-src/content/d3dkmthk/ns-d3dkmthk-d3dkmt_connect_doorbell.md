---
UID: NS:d3dkmthk._D3DKMT_CONNECT_DOORBELL
tech.root: display
title: D3DKMT_CONNECT_DOORBELL
ms.date: 04/08/2024
targetos: Windows
description: Learn more about the D3DKMT_CONNECT_DOORBELL structure.
prerelease: false
req.construct-type: structure
req.ddi-compliance: 
req.dll: 
req.header: d3dkmthk.h
req.include-header: 
req.kmdf-ver: 
req.lib: 
req.max-support: 
req.redist: 
req.target-min-winverclnt: Windows 11, version 24H2 (WDDM 3.2)
req.target-min-winversvr: 
req.target-type: 
req.typenames: D3DKMT_CONNECT_DOORBELL
typedef_isUnnamed: false
req.umdf-ver: 
req.unicode-ansi: 
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - d3dkmthk.h
api_name:
 - _D3DKMT_CONNECT_DOORBELL
 - D3DKMT_CONNECT_DOORBELL
f1_keywords:
 - _D3DKMT_CONNECT_DOORBELL
 - d3dkmthk/_D3DKMT_CONNECT_DOORBELL
 - D3DKMT_CONNECT_DOORBELL
 - d3dkmthk/D3DKMT_CONNECT_DOORBELL
dev_langs:
 - c++
helpviewer_keywords:
 - _D3DKMT_CONNECT_DOORBELL
---

# D3DKMT_CONNECT_DOORBELL structure (d3dkmthk.h)

## -description

The **D3DKMT_CONNECT_DOORBELL** structure describes the doorbell that [**D3DKMTConnectDoorbell**](nf-d3dkmthk-d3dkmtconnectdoorbell.md) should connect to a hardware queue.

## -struct-fields

### -field hDoorbell

[in] UMD handle of the doorbell to be connected. This handle was returned in a prior call to [**D3DKMTCreateDoorbell**](nf-d3dkmthk-d3dkmtcreatedoorbell.md).

### -field Flags

[in] A [**D3DKMT_CONNECT_DOORBELL_FLAGS**](ns-d3dkmthk-d3dkmt_connect_doorbell_flags.md) value that specifies how to connect the doorbell to the hardware queue. No flags are currently defined.

## -remarks

For more information, see [User-mode work submission](/windows-hardware/drivers/display/user-mode-work-submission).

## -see-also

[**D3DKMTConnectDoorbell**](nf-d3dkmthk-d3dkmtconnectdoorbell.md)

[**D3DKMTCreateHwQueue**](nf-d3dkmthk-d3dkmtcreatehwqueue.md)
