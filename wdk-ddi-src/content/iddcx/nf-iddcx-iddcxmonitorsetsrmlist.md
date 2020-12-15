---
UID: NF:iddcx.IddCxMonitorSetSrmList
title: IddCxMonitorSetSrmList
ms.date: 10/02/2020
tech.root: display
ms.topic: language-reference
targetos: Windows
description: IddCxMonitorSetSrmList passes a System Renewability Message (SRM) list to the GPU driver associated with the rendering of the specified monitor.
req.assembly: 
req.construct-type: function
req.ddi-compliance: 
req.dll: 
req.header: iddcx.h
req.idl: 
req.include-header: 
req.irql: 
req.kmdf-ver: 
req.lib: 
req.max-support: 
req.namespace: 
req.redist: 
req.target-min-winverclnt: Windows 10
req.target-min-winversvr: 
req.target-type: 
req.type-library: 
req.umdf-ver: 
req.unicode-ansi: 
topic_type:
 - apiref
api_type:
 - DllExport
api_location:
 - iddcx.h
api_name:
 - IddCxMonitorSetSrmList
f1_keywords:
 - iddcx/IddCxMonitorSetSrmList
dev_langs:
 - c++
---

# IddCxMonitorSetSrmList function

## -description

**IddCxMonitorSetSrmList** passes a System Renewability Message (SRM) list to the GPU driver associated with the rendering of the specified monitor.

## -parameters

### -param MonitorObject

[in] The [IDDCX_MONITOR](/windows-hardware/drivers/display/iddcx-objects) object that the SRM list is associated with.

### -param pInArgs

[in] Pointer to an [**IDARG_IN_SETSRMLIST**](ns-iddcx-idarg_in_setsrmlist.md) structure with input parameters.

## -returns

If the routine succeeds it returns STATUS_SUCCESS; otherwise it returns an appropriate error code such as one of the following:

| Error code | Meaning |
| ---------- | ------- |
| STATUS_GRAPHICS_OPM_NOT_SUPPORTED | The GPU driver does not support this functionality. |
| STATUS_GRAPHICS_OPM_INVALID_SRM | The GPU driver does not recognize the format of the SRM list. This includes whether the driver detected the list had been tampered with. |

## -remarks

An indirect display driver (IDD) calls **IddCxMonitorGetSrmList** to pass a High-Bandwidth Digital Content Protection (HDCP) SRM list to the GPU driver associated with the rendering of the specified monitor. To get the SRM list version, call [**IddCxMonitorGetSrmListVersion**](nf-iddcx-iddcxmonitorgetsrmlistversion.md).

SRMs are used to update the list of revoked High-Bandwidth Digital Content Protection (HDCP) devices, and are delivered with the video content.

## -see-also

[**IDARG_IN_SETSRMLIST**](ns-iddcx-idarg_in_setsrmlist.md)

[**IddCxMonitorGetSrmListVersion**](nf-iddcx-iddcxmonitorgetsrmlistversion.md)
