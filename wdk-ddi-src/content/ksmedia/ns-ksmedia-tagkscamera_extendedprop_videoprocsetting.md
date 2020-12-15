---
UID: NS:ksmedia.tagKSCAMERA_EXTENDEDPROP_VIDEOPROCSETTING
title: tagKSCAMERA_EXTENDEDPROP_VIDEOPROCSETTING (ksmedia.h)
description: The KSCAMERA_EXTENDEDPROP_VIDEOPROCSETTING is a property payload structure for video processing settings related to white balance, exposure mode, and focus mode.
old-location: stream\kscamera_extendedprop_videoprocsetting.htm
tech.root: stream
ms.date: 04/23/2018
keywords: ["tagKSCAMERA_EXTENDEDPROP_VIDEOPROCSETTING structure"]
ms.keywords: "*PKSCAMERA_EXTENDEDPROP_VIDEOPROCSETTING, KSCAMERA_EXTENDEDPROP_VIDEOPROCSETTING, KSCAMERA_EXTENDEDPROP_VIDEOPROCSETTING structure [Streaming Media Devices], KSCAMERA_EXTENDEDPROP_WBPRESET_CANDLELIGHT, KSCAMERA_EXTENDEDPROP_WBPRESET_CLOUDY, KSCAMERA_EXTENDEDPROP_WBPRESET_DAYLIGHT, KSCAMERA_EXTENDEDPROP_WBPRESET_FLASH, KSCAMERA_EXTENDEDPROP_WBPRESET_FLUORESCENT, KSCAMERA_EXTENDEDPROP_WBPRESET_TUNGSTEN, KSCAMERA_EXTENDEDPROP_WHITEBALANCE_PRESET, KSCAMERA_EXTENDEDPROP_WHITEBALANCE_TEMPERATURE, PKSCAMERA_EXTENDEDPROP_VIDEOPROCSETTING, PKSCAMERA_EXTENDEDPROP_VIDEOPROCSETTING structure pointer [Streaming Media Devices], ksmedia/KSCAMERA_EXTENDEDPROP_VIDEOPROCSETTING, ksmedia/PKSCAMERA_EXTENDEDPROP_VIDEOPROCSETTING, stream.kscamera_extendedprop_videoprocsetting, tagKSCAMERA_EXTENDEDPROP_VIDEOPROCSETTING"
req.header: ksmedia.h
req.include-header: Ksmedia.h
req.target-type: Windows
req.target-min-winverclnt: Available starting with Windows 8.1.
req.target-min-winversvr: 
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
req.typenames: KSCAMERA_EXTENDEDPROP_VIDEOPROCSETTING, *PKSCAMERA_EXTENDEDPROP_VIDEOPROCSETTING
f1_keywords:
 - tagKSCAMERA_EXTENDEDPROP_VIDEOPROCSETTING
 - ksmedia/tagKSCAMERA_EXTENDEDPROP_VIDEOPROCSETTING
 - PKSCAMERA_EXTENDEDPROP_VIDEOPROCSETTING
 - ksmedia/PKSCAMERA_EXTENDEDPROP_VIDEOPROCSETTING
 - KSCAMERA_EXTENDEDPROP_VIDEOPROCSETTING
 - ksmedia/KSCAMERA_EXTENDEDPROP_VIDEOPROCSETTING
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - Ksmedia.h
api_name:
 - KSCAMERA_EXTENDEDPROP_VIDEOPROCSETTING
---

# tagKSCAMERA_EXTENDEDPROP_VIDEOPROCSETTING structure


## -description

The **KSCAMERA_EXTENDEDPROP_VIDEOPROCSETTING** is a property payload structure for video processing settings related to white balance, exposure mode, and focus mode.

## -struct-fields

### -field Mode

The video processing mode type. Currently, this member is used to control white balance. The possible values for **Mode** are the following.

| Value | Description |
| --- | --- |
| KSCAMERA_EXTENDEDPROP_WHITEBALANCE_TEMPERATURE | A picture temperature value is used to set white balance in degrees Kelvin. |
| KSCAMERA_EXTENDEDPROP_WHITEBALANCE_PRESET | The white balance setting is a preset value specified in **VideoProc**. |

This member is not used for [KSPROPERTY_CAMERACONTROL_EXTENDED_EXPOSUREMODE](/windows-hardware/drivers/stream/ksproperty-cameracontrol-extended-exposuremode) and [KSPROPERTY_CAMERACONTROL_EXTENDED_FOCUSMODE](/windows-hardware/drivers/stream/ksproperty-cameracontrol-extended-focusmode). In these cases it must be set to 0.

### -field Min

The minimum range value for the setting in **VideoProc**.

### -field Max

The maximum range value for the setting in **VideoProc**.

### -field Step

The increment in value, when applicable, for the setting in **VideoProc** when **Mode** is set to KSCAMERA_EXTENDEDPROP_WHITEBALANCE_TEMPERATURE.

-or-

The increment in value, when applicable, for the setting in **VideoProc** when setting exposure is set manually with KSCAMERA_EXTENDEDPROP_VIDEOPROCFLAG_MANUAL.

### -field VideoProc

Using the [KSPROPERTY_CAMERACONTROL_EXTENDED_WHITEBALANCEMODE](/windows-hardware/drivers/stream/ksproperty-cameracontrol-extended-whitebalancemode) property, when **Mode** is set to KSCAMERA_EXTENDEDPROP_WHITEBALANCE_PRESET, the **VideoProc.Value.ul** value is one of the following.

| Value | Description |
| --- | --- |
| KSCAMERA_EXTENDEDPROP_WBPRESET_CLOUDY | White balance preset for cloudy conditions. |
| KSCAMERA_EXTENDEDPROP_WBPRESET_DAYLIGHT | White balance preset for cloudy daylight. |
| KSCAMERA_EXTENDEDPROP_WBPRESET_FLASH | White balance preset to compensate for flash lighting. |
| KSCAMERA_EXTENDEDPROP_WBPRESET_FLUORESCENT | White balance preset to compensate for fluorescent lighting. |
| KSCAMERA_EXTENDEDPROP_WBPRESET_TUNGSTEN | White balance preset to compensate for tungsten emitted lighting. |
| KSCAMERA_EXTENDEDPROP_WBPRESET_CANDLELIGHT | White balance preset to compensate for candlelight lighting. |

Using the [KSPROPERTY_CAMERACONTROL_EXTENDED_WHITEBALANCEMODE](/windows-hardware/drivers/stream/ksproperty-cameracontrol-extended-whitebalancemode) property, when **Mode** is set to KSCAMERA_EXTENDEDPROP_WHITEBALANCE_TEMPERATURE, the **VideoProc.Value.ul** value is a temperature value in degrees Kelvin.

Using the  [KSPROPERTY_CAMERACONTROL_EXTENDED_EXPOSUREMODE](/windows-hardware/drivers/stream/ksproperty-cameracontrol-extended-exposuremode) property, when used for manually setting exposure, KSCAMERA_EXTENDEDPROP_VIDEOPROCFLAG_MANUAL, the **VideoProc.Value.ul** value is a the exposure time in 100 nanosecond units.

Using the [KSPROPERTY_CAMERACONTROL_EXTENDED_FOCUSMODE](/windows-hardware/drivers/stream/ksproperty-cameracontrol-extended-focusmode) property, this member contains the focal length value for manual focus mode,  KSCAMERA_EXTENDEDPROP_VIDEOPROCFLAG_MANUAL.

### -field Reserved

Reserved.

## -see-also

[KSPROPERTY_CAMERACONTROL_EXTENDED_EXPOSUREMODE](/windows-hardware/drivers/stream/ksproperty-cameracontrol-extended-exposuremode)

[KSPROPERTY_CAMERACONTROL_EXTENDED_FOCUSMODE](/windows-hardware/drivers/stream/ksproperty-cameracontrol-extended-focusmode)

[KSPROPERTY_CAMERACONTROL_EXTENDED_WHITEBALANCEMODE](/windows-hardware/drivers/stream/ksproperty-cameracontrol-extended-whitebalancemode)
