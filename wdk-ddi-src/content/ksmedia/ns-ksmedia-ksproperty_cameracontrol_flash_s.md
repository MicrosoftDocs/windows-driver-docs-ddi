---
UID: NS:ksmedia.KSPROPERTY_CAMERACONTROL_FLASH_S
title: KSPROPERTY_CAMERACONTROL_FLASH_S (ksmedia.h)
description: Describes flash control properties in the PROPSETID_VIDCAP_CAMERACONTROL_FLASH camera control property set. This structure specifies property values that are used by applications to configure the camera's flash.
tech.root: stream
ms.date: 03/10/2023
keywords: ["KSPROPERTY_CAMERACONTROL_FLASH_S structure"]
ms.keywords: "*PKSPROPERTY_CAMERACONTROL_FLASH_S, KSPROPERTY_CAMERACONTROL_FLASH_AUTO, KSPROPERTY_CAMERACONTROL_FLASH_FLAGS_AUTO, KSPROPERTY_CAMERACONTROL_FLASH_FLAGS_MANUAL, KSPROPERTY_CAMERACONTROL_FLASH_OFF, KSPROPERTY_CAMERACONTROL_FLASH_ON, KSPROPERTY_CAMERACONTROL_FLASH_S, KSPROPERTY_CAMERACONTROL_FLASH_S structure [Streaming Media Devices], PKSPROPERTY_CAMERACONTROL_FLASH_S, PKSPROPERTY_CAMERACONTROL_FLASH_S structure pointer [Streaming Media Devices], ksmedia/KSPROPERTY_CAMERACONTROL_FLASH_S, ksmedia/PKSPROPERTY_CAMERACONTROL_FLASH_S, stream.ksproperty_cameracontrol_flash_s"
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
req.typenames: KSPROPERTY_CAMERACONTROL_FLASH_S, *PKSPROPERTY_CAMERACONTROL_FLASH_S
f1_keywords:
 - PKSPROPERTY_CAMERACONTROL_FLASH_S
 - ksmedia/PKSPROPERTY_CAMERACONTROL_FLASH_S
 - KSPROPERTY_CAMERACONTROL_FLASH_S
 - ksmedia/KSPROPERTY_CAMERACONTROL_FLASH_S
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - Ksmedia.h
api_name:
 - PKSPROPERTY_CAMERACONTROL_FLASH_S
 - KSPROPERTY_CAMERACONTROL_FLASH_S
---

## -description

Describes flash control properties in the **PROPSETID_VIDCAP_CAMERACONTROL_FLASH** camera control property set. This structure specifies property values that are used by applications to configure the camera's flash.

## -struct-fields

### -field Flash

Indicates requested flash settings. This value must be one of these possible values:

| Value | Meaning |
|---|---|
| KSPROPERTY_CAMERACONTROL_FLASH_OFF | The flash should never activate. |
| KSPROPERTY_CAMERACONTROL_FLASH_ON | The flash should activate regardless of lighting conditions. |
| KSPROPERTY_CAMERACONTROL_FLASH_AUTO | The flash should be controlled by the device and driver based on lighting conditions. |

### -field Capabilities

Indicates the flash modes that the device supports. This value is a bitwise **OR** of these possible values:

| Value | Meaning |
|---|---|
| KSPROPERTY_CAMERACONTROL_FLASH_FLAGS_AUTO | The device and driver automatically control flash settings. |
| KSPROPERTY_CAMERACONTROL_FLASH_FLAGS_MANUAL | The user manually sets the flash settings. |

## -see-also

[KSPROPERTY_CAMERACONTROL_FLASH_PROPERTY](/windows-hardware/drivers/stream/ksproperty-cameracontrol-flash-property)
