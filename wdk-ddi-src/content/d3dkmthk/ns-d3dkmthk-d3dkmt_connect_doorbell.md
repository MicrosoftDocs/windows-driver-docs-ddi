---
UID: NS:d3dkmthk._D3DKMT_CONNECT_DOORBELL
tech.root: display
title: D3DKMT_CONNECT_DOORBELL
ms.date: 05/22/2023
targetos: Windows
description: Learn more about the D3DKMT_CONNECT_DOORBELL structure.
prerelease: true
req.construct-type: structure
req.ddi-compliance: 
req.dll: 
req.header: d3dkmthk.h
req.include-header: 
req.kmdf-ver: 
req.lib: 
req.max-support: 
req.redist: 
req.target-min-winverclnt: WIN11_FUTURE
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

## -description

The **D3DKMT_CONNECT_DOORBELL** structure describes the doorbell object that [**D3DKMTConnectDoorbell**](nf-d3dkmthk-d3dkmtconnectdoorbell.md) should connect to a hardware queue.

## -struct-fields

### -field hHwQueue

[in] UMD handle to the hardware queue whose doorbell is to be created. This handle was created in [**D3DKMTCreateHwQueue**](nf-d3dkmthk-d3dkmtcreatehwqueue.md) and passed in a previous call to [**D3DKMTCreateDoorbell**](nf-d3dkmthk-d3dkmtcreatedoorbell.md).

### -field Flags

[in] A D3DKMT_CONNECT_DOORBELL_FLAGS value that specifies how to connect the doorbell to the hardware queue. No flags are currently defined.

## -see-also

[**D3DKMTConnectDoorbell**](nf-d3dkmthk-d3dkmtconnectdoorbell.md)

[**D3DKMTCreateHwQueue**](nf-d3dkmthk-d3dkmtcreatehwqueue.md)
