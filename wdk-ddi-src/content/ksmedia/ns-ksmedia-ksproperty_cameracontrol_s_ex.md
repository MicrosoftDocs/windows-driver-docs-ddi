---
UID: NS:ksmedia.KSPROPERTY_CAMERACONTROL_S_EX
title: KSPROPERTY_CAMERACONTROL_S_EX (ksmedia.h)
description: Specifies a camera control operation, including setting the flash, the image pin control properties, the region of interest in the image, or video stabilization.
tech.root: stream
ms.date: 03/14/2023
keywords: ["KSPROPERTY_CAMERACONTROL_S_EX structure"]
ms.keywords: "*PKSPROPERTY_CAMERACONTROL_S_EX, KSPROPERTY_CAMERACONTROL_FLAGS_ASYNCHRONOUS, KSPROPERTY_CAMERACONTROL_FLAGS_AUTO, KSPROPERTY_CAMERACONTROL_FLAGS_MANUAL, KSPROPERTY_CAMERACONTROL_S_EX, KSPROPERTY_CAMERACONTROL_S_EX structure [Streaming Media Devices], PKSPROPERTY_CAMERACONTROL_S_EX, PKSPROPERTY_CAMERACONTROL_S_EX structure pointer [Streaming Media Devices], ksmedia/KSPROPERTY_CAMERACONTROL_S_EX, ksmedia/PKSPROPERTY_CAMERACONTROL_S_EX, stream.ksproperty_cameracontrol_s_ex"
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
req.typenames: KSPROPERTY_CAMERACONTROL_S_EX, *PKSPROPERTY_CAMERACONTROL_S_EX
f1_keywords:
 - PKSPROPERTY_CAMERACONTROL_S_EX
 - ksmedia/PKSPROPERTY_CAMERACONTROL_S_EX
 - KSPROPERTY_CAMERACONTROL_S_EX
 - ksmedia/KSPROPERTY_CAMERACONTROL_S_EX
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - Ksmedia.h
api_name:
 - PKSPROPERTY_CAMERACONTROL_S_EX
 - KSPROPERTY_CAMERACONTROL_S_EX
---

## -description

Specifies a camera control operation, including setting the flash, the image pin control properties, the region of interest in the image, or video stabilization. This structure describes filter-based properties in the [PROPSETID_VIDCAP_CAMERACONTROL](/windows-hardware/drivers/stream/propsetid-vidcap-cameracontrol) property set.

Supported starting with Windows 8.

## -struct-fields

### -field Property

Specifies an initialized [KSPROPERTY](/windows-hardware/drivers/stream/ksproperty-structure) structure that describes the property set, property ID, and request type.

### -field Value

Specifies the value of the property. This member is read/write.

### -field Flags

Indicates, for Get requests, the current setting for the specified property from the values listed below. Indicates, for Set requests, the desired setting for the specified property from the values listed below. This member can be a bitwise **OR** of the following values that are defined in *Ksmedia.h*:

| Value | Description |
|---|---|
| **KSPROPERTY_CAMERACONTROL_FLAGS_AUTO** | Indicates that the setting is controlled automatically. If the driver receives this value, it should set the camera control synchronously to automatic mode and then return. |
| **KSPROPERTY_CAMERACONTROL_FLAGS_MANUAL** | Indicates that the setting is controlled manually. If the driver receives this value, it should set the camera control synchronously to manual mode and then return. |
| **KSPROPERTY_CAMERACONTROL_FLAGS_ASYNCHRONOUS** | Indicates whether the driver should perform the camera control operation asynchronously—where the application has issued a command for the driver to set up the camera control settings in advance of taking a picture. This flag must be set only if either **KSPROPERTY_CAMERACONTROL_FLAGS_MANUAL** or **KSPROPERTY_CAMERACONTROL_FLAGS_AUTO** are set. If this flag value and the **KSPROPERTY_CAMERACONTROL_FLAGS_AUTO** flag value are both set, the driver should initiate a worker thread to start one requested control operation and should reject all other requests for the same operation until it has completed the first one. After the operation has successfully completed, the driver should trigger the [KSEVENTSETID_CameraAsyncControl](/windows-hardware/drivers/stream/kseventsetid-cameraasynccontrol) event. |

### -field Capabilities

If set, indicates that when the application submits a query, the driver should return the value of the **Capabilities** member of the appropriate camera control structure from the following list.

- [**KSPROPERTY_CAMERACONTROL_FLASH_S**](/windows-hardware/drivers/ddi/ksmedia/ns-ksmedia-ksproperty_cameracontrol_flash_s)

- [**KSPROPERTY_CAMERACONTROL_IMAGE_PIN_CAPABILITY_S**](/windows-hardware/drivers/ddi/ksmedia/ns-ksmedia-ksproperty_cameracontrol_image_pin_capability_s)

- [**KSPROPERTY_CAMERACONTROL_REGION_OF_INTEREST_S**](/windows-hardware/drivers/ddi/ksmedia/ns-ksmedia-ksproperty_cameracontrol_region_of_interest_s)

- [**KSPROPERTY_CAMERACONTROL_VIDEOSTABILIZATION_MODE_S**](/windows-hardware/drivers/ddi/ksmedia/ns-ksmedia-ksproperty_cameracontrol_videostabilization_mode_s)

### -field FocusRect

A [**RECT**](/windows/win32/api/windef/ns-windef-rect) structure that specifies the rectangular region in which the device should set the focus. This structure is available only to Windows desktop applications.

## -remarks

When a requested camera focus operation is completed or is canceled, the driver should generate an event specified by the **KSEVENT_CAMERACONTROL_FOCUS** enumeration value.

## -see-also

[**KSEVENT_CAMERACONTROL**](/windows-hardware/drivers/ddi/ksmedia/ne-ksmedia-ksevent_cameracontrol)

[KSPROPERTY](/windows-hardware/drivers/stream/ksproperty-structure)

[**KSPROPERTY_CAMERACONTROL_FLASH_S**](/windows-hardware/drivers/ddi/ksmedia/ns-ksmedia-ksproperty_cameracontrol_flash_s)

[**KSPROPERTY_CAMERACONTROL_REGION_OF_INTEREST_S**](/windows-hardware/drivers/ddi/ksmedia/ns-ksmedia-ksproperty_cameracontrol_region_of_interest_s)

[**KSPROPERTY_CAMERACONTROL_VIDEOSTABILIZATION_MODE_S**](/windows-hardware/drivers/ddi/ksmedia/ns-ksmedia-ksproperty_cameracontrol_videostabilization_mode_s)

[**RECT**](/windows/win32/api/windef/ns-windef-rect)
