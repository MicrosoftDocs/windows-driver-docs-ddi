---
UID: NA:lamp
ms.assetid: 833c0c85-940a-38d0-b008-ca5d75808679
ms.author: windowsdriverdev
ms.date: 02/26/18
ms.keywords: 
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: portal
---

# Lamp.h header



This header is used by Streaming media devices. For more information, see
- [Streaming media devices](../_stream/index.md)

Lamp.h contain these programming interfaces:


## Structures

| Title   | Description   |
| ---- |:---- |
| [LAMP_CAPABILITIES_COLOR structure](ns-lamp-lamp_capabilities_color.md) | This structure is the I/O parameter type of IOCTL_LAMP_{GET|SET}_INTENSITY_COLOR. |
| [LAMP_CAPABILITIES_WHITE structure](ns-lamp-lamp_capabilities_white.md) | This structure is the I/O parameter type of IOCTL_LAMP_{GET|SET}_INTENSITY_WHITE. |
| [LAMP_INTENSITY_COLOR structure](ns-lamp-lamp_intensity_color.md) | This structure is the I/O parameter type of IOCTL_LAMP_GET_INTENSITY_COLOR and IOCTL_LAMP_SET_INTENSITY_COLOR. |
| [LAMP_INTENSITY_WHITE structure](ns-lamp-lamp_intensity_white.md) | This structure is the I/O parameter type of IOCTL_LAMP_GET_INTENSITY_WHITE and IOCTL_LAMP_SET_INTENSITY_WHITE. |

## I/O control codes

| Title   | Description   |
| ---- |:---- |
| [IOCTL_LAMP_GET_CAPABILITIES_COLOR IOCTL](ni-lamp-ioctl_lamp_get_capabilities_color.md) | The IOCTL_LAMP_GET_CAPABILITIES_COLOR control code queries the capabilities of the lamp when the device is configured to emit color light. |
| [IOCTL_LAMP_GET_CAPABILITIES_WHITE IOCTL](ni-lamp-ioctl_lamp_get_capabilities_white.md) | The IOCTL_LAMP_GET_CAPABILITIES_WHITE control code queries the capabilities of the lamp when the device is configured to emit white light. |
| [IOCTL_LAMP_GET_EMITTING_LIGHT IOCTL](ni-lamp-ioctl_lamp_get_emitting_light.md) | The IOCTL_LAMP_GET_EMITTING_LIGHT control code queries if the lamp is turned on. |
| [IOCTL_LAMP_GET_INTENSITY_COLOR IOCTL](ni-lamp-ioctl_lamp_get_intensity_color.md) | The IOCTL_LAMP_GET_INTENSITY_COLOR control code queries the light intensity when the lamp is configured to emit color light. |
| [IOCTL_LAMP_GET_INTENSITY_WHITE IOCTL](ni-lamp-ioctl_lamp_get_intensity_white.md) | The IOCTL_LAMP_GET_INTENSITY_WHITE control code queries the light intensity when the lamp is configured to emit white light. |
| [IOCTL_LAMP_GET_MODE IOCTL](ni-lamp-ioctl_lamp_get_mode.md) | The IOCTL_LAMP_GET_MODE control code queries the mode with which the lamp is currently configured. |
| [IOCTL_LAMP_SET_EMITTING_LIGHT IOCTL](ni-lamp-ioctl_lamp_set_emitting_light.md) | The IOCTL_LAMP_SET_EMITTING_LIGHT control code turns the lamp on or off. |
| [IOCTL_LAMP_SET_INTENSITY_COLOR IOCTL](ni-lamp-ioctl_lamp_set_intensity_color.md) | The IOCTL_LAMP_SET_INTENSITY_COLOR control code sets the lamp to the specified light intensity. |
| [IOCTL_LAMP_SET_INTENSITY_WHITE IOCTL](ni-lamp-ioctl_lamp_set_intensity_white.md) | The IOCTL_LAMP_SET_INTENSITY_WHITE control code sets the lamp to the specified light intensity. |
| [IOCTL_LAMP_SET_MODE IOCTL](ni-lamp-ioctl_lamp_set_mode.md) | The IOCTL_LAMP_SET_MODE control code sets the mode in which the lamp operates. |

## Enumerations

| Title   | Description   |
| ---- |:---- |
| [LAMP_MODE enumeration](ne-lamp-lamp_mode.md) | This enumeration contains the operating modes of a lamp device. |
