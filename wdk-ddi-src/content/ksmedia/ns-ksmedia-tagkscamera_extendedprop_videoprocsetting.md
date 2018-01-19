---
UID: NS:ksmedia.tagKSCAMERA_EXTENDEDPROP_VIDEOPROCSETTING
title: tagKSCAMERA_EXTENDEDPROP_VIDEOPROCSETTING
author: windows-driver-content
description: The KSCAMERA_EXTENDEDPROP_VIDEOPROCSETTING is a property payload structure for video processing settings related to white balance, exposure mode, and focus mode.
old-location: stream\kscamera_extendedprop_videoprocsetting.htm
old-project: stream
ms.assetid: D4239E72-C57A-45BC-881C-08FF6263874E
ms.author: windowsdriverdev
ms.date: 1/9/2018
ms.keywords: tagKSCAMERA_EXTENDEDPROP_VIDEOPROCSETTING, *PKSCAMERA_EXTENDEDPROP_VIDEOPROCSETTING, KSCAMERA_EXTENDEDPROP_VIDEOPROCSETTING
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: ksmedia.h
req.include-header: Ksmedia.h
req.target-type: Windows
req.target-min-winverclnt: Available starting with Windows 8.1.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: KSCAMERA_EXTENDEDPROP_VIDEOPROCSETTING
req.alt-loc: Ksmedia.h
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
req.typenames: *PKSCAMERA_EXTENDEDPROP_VIDEOPROCSETTING, KSCAMERA_EXTENDEDPROP_VIDEOPROCSETTING
---

# tagKSCAMERA_EXTENDEDPROP_VIDEOPROCSETTING structure



## -description
The <b>KSCAMERA_EXTENDEDPROP_VIDEOPROCSETTING</b> is a property payload structure for video processing settings related to white balance, exposure mode, and focus mode.



## -syntax

````
typedef struct _KSCAMERA_EXTENDEDPROP_VIDEOPROCSETTING {
  ULONG                       Mode;
  LONG                        Min;
  LONG                        Max;
  LONG                        Step;
  KSCAMERA_EXTENDEDPROP_VALUE VideoProc;
  ULONGLONG                   Reserved;
} KSCAMERA_EXTENDEDPROP_VIDEOPROCSETTING, *PKSCAMERA_EXTENDEDPROP_VIDEOPROCSETTING;
````


## -struct-fields

### -field Mode

The video processing mode type. Currently, this member is used to control white balance. The possible values for <b>Mode</b> are the following.

<table>
<tr>
<th>Value</th>
<th>Meaning</th>
</tr>
<tr>

### -field KSCAMERA_EXTENDEDPROP_WHITEBALANCE_TEMPERATURE

</td>
<td width="60%">
A picture temperature value is used to set white balance in degrees Kelvin.

</td>
</tr>
<tr>

### -field KSCAMERA_EXTENDEDPROP_WHITEBALANCE_PRESET

</td>
<td width="60%">
The white balance setting is a preset value specified in <b>VideoProc</b>.

</td>
</tr>
</table>
 

This member is not used for <a href="https://msdn.microsoft.com/library/windows/hardware/dn567573">KSPROPERTY_CAMERACONTROL_EXTENDED_EXPOSUREMODE</a> and <a href="https://msdn.microsoft.com/library/windows/hardware/dn567576">KSPROPERTY_CAMERACONTROL_EXTENDED_FOCUSMODE</a>. In these cases it must be set to 0.


### -field Min

The minum range value for the setting in <b>VideoProc</b>.


### -field Max

The maximum range value for the setting in <b>VideoProc</b>.


### -field Step

The maximum range value for the setting in <b>VideoProc</b>.

The increment in value, when applicable, for the setting in <b>VideoProc</b> when <b>Mode</b> is set to KSCAMERA_EXTENDEDPROP_WHITEBALANCE_TEMPERATURE.

-or-

The increment in value, when applicable, for the setting in <b>VideoProc</b> when setting exposure is set manually with KSCAMERA_EXTENDEDPROP_VIDEOPROCFLAG_MANUAL.


### -field VideoProc

Using the <a href="https://msdn.microsoft.com/library/windows/hardware/dn567588">KSPROPERTY_CAMERACONTROL_EXTENDED_WHITEBALANCEMODE</a> property, when <b>Mode</b> is set to KSCAMERA_EXTENDEDPROP_WHITEBALANCE_PRESET, the <b>VideoProc.Value.ul</b> value is one of the following.

<table>
<tr>
<th>Value</th>
<th>Meaning</th>
</tr>
<tr>

### -field KSCAMERA_EXTENDEDPROP_WBPRESET_CLOUDY

</td>
<td width="60%">
White balance preset for cloudy conditions.

</td>
</tr>
<tr>

### -field KSCAMERA_EXTENDEDPROP_WBPRESET_DAYLIGHT

</td>
<td width="60%">
White balance preset for cloudy daylight.

</td>
</tr>
<tr>

### -field KSCAMERA_EXTENDEDPROP_WBPRESET_FLASH

</td>
<td width="60%">
White balance preset to compensate for flash lighting.

</td>
</tr>
<tr>

### -field KSCAMERA_EXTENDEDPROP_WBPRESET_FLUORESCENT

</td>
<td width="60%">
White balance preset to compensate for fluorescent lighting.

</td>
</tr>
<tr>

### -field KSCAMERA_EXTENDEDPROP_WBPRESET_TUNGSTEN

</td>
<td width="60%">
White balance preset to compensate for tungsten emitted lighting.

</td>
</tr>
<tr>

### -field KSCAMERA_EXTENDEDPROP_WBPRESET_CANDLELIGHT

</td>
<td width="60%">
White balance preset to compensate for candlelight lighting.

</td>
</tr>
</table>
 

Using the <a href="https://msdn.microsoft.com/library/windows/hardware/dn567588">KSPROPERTY_CAMERACONTROL_EXTENDED_WHITEBALANCEMODE</a> property, when <b>Mode</b> is set to KSCAMERA_EXTENDEDPROP_WHITEBALANCE_TEMPERATURE, the <b>VideoProc.Value.ul</b> value is a temperature value in degrees Kelvin.

Using the  <a href="https://msdn.microsoft.com/library/windows/hardware/dn567573">KSPROPERTY_CAMERACONTROL_EXTENDED_EXPOSUREMODE</a> property, when used for manually setting exposure, KSCAMERA_EXTENDEDPROP_VIDEOPROCFLAG_MANUAL, the <b>VideoProc.Value.ul</b> value is a the exposure time in 100 nanosecond units.

Using the <a href="https://msdn.microsoft.com/library/windows/hardware/dn567576">KSPROPERTY_CAMERACONTROL_EXTENDED_FOCUSMODE</a> property, this member contains the focal length value for manual focus mode,  KSCAMERA_EXTENDEDPROP_VIDEOPROCFLAG_MANUAL.


### -field Reserved

Reserved.


## -remarks


## -see-also
<dl>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/dn567573">KSPROPERTY_CAMERACONTROL_EXTENDED_EXPOSUREMODE</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/dn567576">KSPROPERTY_CAMERACONTROL_EXTENDED_FOCUSMODE</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/dn567588">KSPROPERTY_CAMERACONTROL_EXTENDED_WHITEBALANCEMODE</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [stream\stream]:%20KSCAMERA_EXTENDEDPROP_VIDEOPROCSETTING structure%20 RELEASE:%20(1/9/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

