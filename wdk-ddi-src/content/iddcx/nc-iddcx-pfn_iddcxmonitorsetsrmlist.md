---
UID: NC:iddcx.PFN_IDDCXMONITORSETSRMLIST
title: PFN_IDDCXMONITORSETSRMLIST (iddcx.h)
description: PFN_IDDCXMONITORSETSRMLIST is a pointer to an OS callback function that passes a High-Bandwidth Digital Content Protection (HDCP) System Renewability Message (SRM) list to the GPU driver associated with the rendering of the specified monitor.
ms.assetid: 38dfb1cf-f2fd-462f-bce0-a95505cead96
ms.date: 10/19/2018
keywords: ["PFN_IDDCXMONITORSETSRMLIST callback function"]
req.header: iddcx.h
req.include-header: 
req.target-type: 
req.target-min-winverclnt: Windows 10
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.lib: 
req.dll: 
req.irql: 
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
targetos: Windows
tech.root: display
f1_keywords:
 - PFN_IDDCXMONITORSETSRMLIST
 - iddcx/PFN_IDDCXMONITORSETSRMLIST
topic_type:
 - apiref
api_type:
 - UserDefined
api_location:
 - iddcx.h
api_name:
 - PFN_IDDCXMONITORSETSRMLIST
product:
 - Windows
---

# PFN_IDDCXMONITORSETSRMLIST callback function

## -description

**PFN_IDDCXMONITORSETSRMLIST** is a pointer to an OS callback function that passes a High-Bandwidth Digital Content Protection (HDCP) System Renewability Message (SRM) list to the GPU driver associated with the rendering of the specified monitor.

## -parameters

### -param DriverGlobals

[in] Contains system-defined per-driver data.

### -param MonitorObject

[in] The monitor object that the SRM list is associated with.

### -param pInArgs

[in] Input arguments of function.

## -returns

Returns NTSTATUS with the following error codes:

| Return value | Description |
| --- | --- |
| STATUS_SUCCESS | The routine succeeded. |
| STATUS_GRAPHICS_OPM_NOT_SUPPORTED | The GPU driver does not support this new functionality. |
| STATUS_GRAPHICS_OPM_INVALID_SRM | the GPU driver does recognize the format of the SRM list, this include if the driver detected the list had been tampered with. |

## -remarks

An indirect display driver (IDD) should not use this pointer to directly call the function that it points to. IDDs should instead call [**IddCxMonitorSetSrmList**](nf-iddcx-iddcxmonitorsetsrmlist.md).

## -see-also

[**IddCxMonitorSetSrmList**](nf-iddcx-iddcxmonitorsetsrmlist.md)
