---
UID: NS:d3dkmthk._D3DKMT_UNREGISTERTRIMNOTIFICATION
title: _D3DKMT_UNREGISTERTRIMNOTIFICATION (d3dkmthk.h)
description: D3DKMT_UNREGISTERTRIMNOTIFICATION is used with D3DKMTUnregisterTrimNotification to remove a callback registration for a kernel mode device receiving notifications from a graphics framework (such as OpenGL).
old-location: display\d3dkmt_unregistertrimnotification.htm
ms.date: 05/10/2018
keywords: ["D3DKMT_UNREGISTERTRIMNOTIFICATION structure"]
ms.keywords: D3DKMT_UNREGISTERTRIMNOTIFICATION, D3DKMT_UNREGISTERTRIMNOTIFICATION structure [Display Devices], _D3DKMT_UNREGISTERTRIMNOTIFICATION, d3dkmthk/D3DKMT_UNREGISTERTRIMNOTIFICATION, display.d3dkmt_unregistertrimnotification
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
req.typenames: D3DKMT_UNREGISTERTRIMNOTIFICATION
f1_keywords:
 - _D3DKMT_UNREGISTERTRIMNOTIFICATION
 - d3dkmthk/_D3DKMT_UNREGISTERTRIMNOTIFICATION
 - D3DKMT_UNREGISTERTRIMNOTIFICATION
 - d3dkmthk/D3DKMT_UNREGISTERTRIMNOTIFICATION
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - D3dkmthk.h
api_name:
 - D3DKMT_UNREGISTERTRIMNOTIFICATION
---

# _D3DKMT_UNREGISTERTRIMNOTIFICATION structure


## -description

<b>D3DKMT_UNREGISTERTRIMNOTIFICATION</b> is used with <a href="/windows-hardware/drivers/ddi/d3dkmthk/nf-d3dkmthk-d3dkmtunregistertrimnotification">D3DKMTUnregisterTrimNotification</a> to remove a callback registration for a kernel mode device receiving notifications from a graphics framework (such as OpenGL).

## -struct-fields

### -field Handle

[out] The callback notification handle received from the call to <a href="/windows-hardware/drivers/ddi/d3dkmthk/nf-d3dkmthk-d3dkmtregistertrimnotification">D3DKMTRegisterTrimNotification</a>.

### -field Callback

## -see-also

<a href="/windows-hardware/drivers/ddi/d3dkmthk/nf-d3dkmthk-d3dkmtregistertrimnotification">D3DKMTRegisterTrimNotification</a>



<a href="/windows-hardware/drivers/ddi/d3dkmthk/nf-d3dkmthk-d3dkmtunregistertrimnotification">D3DKMTUnregisterTrimNotification</a>
