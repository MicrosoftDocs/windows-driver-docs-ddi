---
UID: NS:d3dkmddi._DXGKARGCB_NOTIFYCURSORSUPPORTCHANGE
tech.root: display
title: DXGKARGCB_NOTIFYCURSORSUPPORTCHANGE
ms.date: 10/13/2021
targetos: Windows
description: The DXGKARGCB_NOTIFYCURSORSUPPORTCHANGE structure contains arguments for the DxgkCbNotifyCursorSupportChange callback function.
req.construct-type: structure
req.ddi-compliance: 
req.dll: 
req.header: d3dkmddi.h
req.include-header: 
req.kmdf-ver: 
req.lib: 
req.max-support: 
req.redist: 
req.target-min-winverclnt: 
req.target-min-winversvr: Windows Server 2022 (WDDM 2.9)
req.target-type: 
req.typenames: DXGKARGCB_NOTIFYCURSORSUPPORTCHANGE
req.umdf-ver: 
req.unicode-ansi: 
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - d3dkmddi.h
api_name:
 - _DXGKARGCB_NOTIFYCURSORSUPPORTCHANGE
 - DXGKARGCB_NOTIFYCURSORSUPPORTCHANGE
f1_keywords:
 - _DXGKARGCB_NOTIFYCURSORSUPPORTCHANGE
 - d3dkmddi/_DXGKARGCB_NOTIFYCURSORSUPPORTCHANGE
 - DXGKARGCB_NOTIFYCURSORSUPPORTCHANGE
 - d3dkmddi/DXGKARGCB_NOTIFYCURSORSUPPORTCHANGE
dev_langs:
 - c++
---

## -description

The **DXGKARGCB_NOTIFYCURSORSUPPORTCHANGE** structure contains arguments for the [**DXGKCB_NOTIFYCURSORSUPPORTCHANGE**](nc-d3dkmddi-dxgkcb_notifycursorsupportchange.md) callback function.

## -struct-fields

### -field DeviceHandle

[in] A handle to the adapter object for the GPU. The driver receives the handle from the **DeviceHandle** member of the [**DXGKRNL_INTERFACE**](../dispmprt/ns-dispmprt-_dxgkrnl_interface.md) structure in a call to its [**DxgkDdiStartDevice**](../dispmprt/nc-dispmprt-dxgkddi_start_device.md) function.

### -field VidPnSourceId

[in] The [ID of the video present source](../d3dkmdt/ns-d3dkmdt-_d3dkmdt_video_present_source.md) on which cursor support is being changed. The OS fails the [**DXGKCB_NOTIFYCURSORSUPPORTCHANGE**](nc-d3dkmddi-dxgkcb_notifycursorsupportchange.md) callback if **VidPnSourceId** isn't valid.

## -see-also

[**DXGKCB_NOTIFYCURSORSUPPORTCHANGE**](nc-d3dkmddi-dxgkcb_notifycursorsupportchange.md)
