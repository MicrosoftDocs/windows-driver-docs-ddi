---
UID: NS:ksmedia.KSPROPERTY_CAMERACONTROL_REGION_OF_INTEREST_S
title: KSPROPERTY_CAMERACONTROL_REGION_OF_INTEREST_S (ksmedia.h)
description: Describes region of interest (ROI) control properties in the PROPSETID_VIDCAP_CAMERACONTROL_REGION_OF_INTEREST camera control property set.
tech.root: stream
ms.date: 03/10/2023
keywords: ["KSPROPERTY_CAMERACONTROL_REGION_OF_INTEREST_S structure"]
ms.keywords: "*PKSPROPERTY_CAMERACONTROL_REGION_OF_INTEREST_S, KSPROPERTY_CAMERACONTROL_REGION_OF_INTEREST_CONFIG_EXPOSURE, KSPROPERTY_CAMERACONTROL_REGION_OF_INTEREST_CONFIG_FOCUS, KSPROPERTY_CAMERACONTROL_REGION_OF_INTEREST_CONFIG_WB, KSPROPERTY_CAMERACONTROL_REGION_OF_INTEREST_CONVERGEMODE, KSPROPERTY_CAMERACONTROL_REGION_OF_INTEREST_FLAGS_ASYNC, KSPROPERTY_CAMERACONTROL_REGION_OF_INTEREST_FLAGS_AUTO, KSPROPERTY_CAMERACONTROL_REGION_OF_INTEREST_FLAGS_MANUAL, KSPROPERTY_CAMERACONTROL_REGION_OF_INTEREST_S, KSPROPERTY_CAMERACONTROL_REGION_OF_INTEREST_S structure [Streaming Media Devices], PKSPROPERTY_CAMERACONTROL_REGION_OF_INTEREST_S, PKSPROPERTY_CAMERACONTROL_REGION_OF_INTEREST_S structure pointer [Streaming Media Devices], ksmedia/KSPROPERTY_CAMERACONTROL_REGION_OF_INTEREST_S, ksmedia/PKSPROPERTY_CAMERACONTROL_REGION_OF_INTEREST_S, stream.ksproperty_cameracontrol_region_of_interest_s"
req.header: ksmedia.h
req.include-header: Ksmedia.h
req.target-type: Windows
req.target-min-winverclnt: Windows 8
req.target-min-winversvr: Windows Server 2012
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
req.typenames: KSPROPERTY_CAMERACONTROL_REGION_OF_INTEREST_S, *PKSPROPERTY_CAMERACONTROL_REGION_OF_INTEREST_S
f1_keywords:
 - PKSPROPERTY_CAMERACONTROL_REGION_OF_INTEREST_S
 - ksmedia/PKSPROPERTY_CAMERACONTROL_REGION_OF_INTEREST_S
 - KSPROPERTY_CAMERACONTROL_REGION_OF_INTEREST_S
 - ksmedia/KSPROPERTY_CAMERACONTROL_REGION_OF_INTEREST_S
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - Ksmedia.h
api_name:
 - PKSPROPERTY_CAMERACONTROL_REGION_OF_INTEREST_S
 - KSPROPERTY_CAMERACONTROL_REGION_OF_INTEREST_S
---

## -description

Describes region of interest (ROI) control properties in the **PROPSETID_VIDCAP_CAMERACONTROL_REGION_OF_INTEREST** camera control property set. The region of interest is a rectangle in the image that is used to focus the camera. This structure specifies property values that are used in requests to the camera driver.

## -struct-fields

### -field FocusRect

A [**RECT**](/windows/win32/api/windef/ns-windef-rect) structure that specifies the rectangular region in which the device should set the focus. This structure is available only to Windows apps.

If **FocusRect** is not a valid value, or if all members of the [**RECT**](/windows/win32/api/windef/ns-windef-rect) structure are zero, the device should focus the center of the image and the remaining members of this structure can be ignored.

The rectangle's coordinates are with respect to the preview video resolution.

### -field AutoFocusLock

If **TRUE**, the device should lock the focus to the current value.

This member should be ignored if **FocusRect** is not a valid value.

### -field AutoExposureLock

If **TRUE**, the device should lock the exposure to the current value.

This member should be ignored if **FocusRect** is not a valid value.

### -field AutoWhitebalanceLock

If **TRUE**, the device should lock the white balance setting to the current value.

This member should be ignored if **FocusRect** is not a valid value.

### -field Capabilities

Indicates whether the device and driver support setting the region of interest automatically or manually. This member a bitwise **OR** of these possible values:

| Value | Meaning |
|---|---|
| KSPROPERTY_CAMERACONTROL_REGION_OF_INTEREST_FLAGS_AUTO | The device and driver can automatically set the region of interest. |
| KSPROPERTY_CAMERACONTROL_REGION_OF_INTEREST_FLAGS_MANUAL | The user can manually set the region of interest. |
| KSPROPERTY_CAMERACONTROL_REGION_OF_INTEREST_FLAGS_ASYNC | ROI control features execute asynchronously. This capability is available starting with Windows 8.1. |

### -field Configuration

Configuration flags for control operations for the region. This is a bitwise OR combination of the following values.

This member is available starting with Windows 8.1.

| Value | Meaning |
| --- | --- |
| KSPROPERTY_CAMERACONTROL_REGION_OF_INTEREST_CONFIG_FOCUS | Set auto focus for the region. |
| KSPROPERTY_CAMERACONTROL_REGION_OF_INTEREST_CONFIG_EXPOSURE | Set auto exposure for the region. |
| KSPROPERTY_CAMERACONTROL_REGION_OF_INTEREST_CONFIG_WB | Set auto white balance for the region. |
| KSPROPERTY_CAMERACONTROL_REGION_OF_INTEREST_CONVERGEMODE | Enable convergence of objects in the region. |

## -see-also

[KSPROPERTY_CAMERACONTROL_FLASH_PROPERTY](/windows-hardware/drivers/stream/ksproperty-cameracontrol-flash-property)

[**RECT**](/windows/win32/api/windef/ns-windef-rect)
