---
UID: NS:d3dkmthk._D3DKMT_REGISTERTRIMNOTIFICATION
title: _D3DKMT_REGISTERTRIMNOTIFICATION (d3dkmthk.h)
description: D3DKMT_REGISTERTRIMNOTIFICATION is used with D3DKMTRegisterTrimNotification to register a callback for a kernel mode device for notifications from a graphics framework (such as OpenGL).
old-location: display\d3dkmt_registertrimnotification.htm
ms.date: 05/10/2018
keywords: ["D3DKMT_REGISTERTRIMNOTIFICATION structure"]
ms.keywords: D3DKMT_REGISTERTRIMNOTIFICATION, D3DKMT_REGISTERTRIMNOTIFICATION structure [Display Devices], _D3DKMT_REGISTERTRIMNOTIFICATION, d3dkmthk/D3DKMT_REGISTERTRIMNOTIFICATION, display.d3dkmt_registertrimnotification
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
req.typenames: D3DKMT_REGISTERTRIMNOTIFICATION
f1_keywords:
 - _D3DKMT_REGISTERTRIMNOTIFICATION
 - d3dkmthk/_D3DKMT_REGISTERTRIMNOTIFICATION
 - D3DKMT_REGISTERTRIMNOTIFICATION
 - d3dkmthk/D3DKMT_REGISTERTRIMNOTIFICATION
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - D3dkmthk.h
api_name:
 - _D3DKMT_REGISTERTRIMNOTIFICATION
 - D3DKMT_REGISTERTRIMNOTIFICATION
---

# _D3DKMT_REGISTERTRIMNOTIFICATION structure


## -description

<b>D3DKMT_REGISTERTRIMNOTIFICATION</b> is used with <a href="/windows-hardware/drivers/ddi/d3dkmthk/nf-d3dkmthk-d3dkmtregistertrimnotification">D3DKMTRegisterTrimNotification</a> to register a callback for a kernel mode device for notifications from a graphics framework (such as OpenGL).

## -struct-fields

### -field AdapterLuid

[in] Luid of the adapter which the device created.

### -field hDevice

[in] Device to trim the residency list for.

### -field Callback

[in] Pointer to the callback function.

### -field Context

[in] Caller-supplied context for callback.

### -field Handle

[out] Handle that will be used to unregister the callback with <a href="/windows-hardware/drivers/ddi/d3dkmthk/nf-d3dkmthk-d3dkmtunregistertrimnotification">D3DKMTUnregisterTrimNotification</a>.

## -see-also

<a href="/windows-hardware/drivers/ddi/d3dkmthk/nf-d3dkmthk-d3dkmtregistertrimnotification">D3DKMTRegisterTrimNotification</a>



<a href="/windows-hardware/drivers/ddi/d3dkmthk/nf-d3dkmthk-d3dkmtunregistertrimnotification">D3DKMTUnregisterTrimNotification</a>

