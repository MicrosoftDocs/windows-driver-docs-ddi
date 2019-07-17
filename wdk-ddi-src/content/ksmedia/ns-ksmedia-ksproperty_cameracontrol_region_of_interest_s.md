---
UID: NS:ksmedia.__unnamed_struct_124
title: KSPROPERTY_CAMERACONTROL_REGION_OF_INTEREST_S (ksmedia.h)
description: Describes region of interest (ROI) control properties in the PROPSETID_VIDCAP_CAMERACONTROL_REGION_OF_INTEREST camera control property set.
old-location: stream\ksproperty_cameracontrol_region_of_interest_s.htm
tech.root: stream
ms.assetid: 0a488d9f-1e34-4482-a2a8-7c160b00766c
ms.date: 04/30/2019
ms.keywords: "*PKSPROPERTY_CAMERACONTROL_REGION_OF_INTEREST_S, KSPROPERTY_CAMERACONTROL_REGION_OF_INTEREST_CONFIG_EXPOSURE, KSPROPERTY_CAMERACONTROL_REGION_OF_INTEREST_CONFIG_FOCUS, KSPROPERTY_CAMERACONTROL_REGION_OF_INTEREST_CONFIG_WB, KSPROPERTY_CAMERACONTROL_REGION_OF_INTEREST_CONVERGEMODE, KSPROPERTY_CAMERACONTROL_REGION_OF_INTEREST_FLAGS_ASYNC, KSPROPERTY_CAMERACONTROL_REGION_OF_INTEREST_FLAGS_AUTO, KSPROPERTY_CAMERACONTROL_REGION_OF_INTEREST_FLAGS_MANUAL, KSPROPERTY_CAMERACONTROL_REGION_OF_INTEREST_S, KSPROPERTY_CAMERACONTROL_REGION_OF_INTEREST_S structure [Streaming Media Devices], PKSPROPERTY_CAMERACONTROL_REGION_OF_INTEREST_S, PKSPROPERTY_CAMERACONTROL_REGION_OF_INTEREST_S structure pointer [Streaming Media Devices], ksmedia/KSPROPERTY_CAMERACONTROL_REGION_OF_INTEREST_S, ksmedia/PKSPROPERTY_CAMERACONTROL_REGION_OF_INTEREST_S, stream.ksproperty_cameracontrol_region_of_interest_s"
ms.topic: struct
f1_keywords:
 - "ksmedia/KSPROPERTY_CAMERACONTROL_REGION_OF_INTEREST_S"
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
topic_type:
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- Ksmedia.h
api_name:
- KSPROPERTY_CAMERACONTROL_REGION_OF_INTEREST_S
product:
- Windows
targetos: Windows
req.typenames: KSPROPERTY_CAMERACONTROL_REGION_OF_INTEREST_S, *PKSPROPERTY_CAMERACONTROL_REGION_OF_INTEREST_S
---

# KSPROPERTY_CAMERACONTROL_REGION_OF_INTEREST_S structure


## -description


Describes region of interest (ROI) control properties in the <b>PROPSETID_VIDCAP_CAMERACONTROL_REGION_OF_INTEREST</b> camera control property set. The region of interest is a rectangle in the image that is used to focus the camera. This structure specifies property values that are used in requests to the camera driver.


## -struct-fields




### -field FocusRect

A <a href="https://docs.microsoft.com/windows/desktop/api/windef/ns-windef-tagrect">RECT</a> structure that specifies the rectangular region in which the device should set the focus. This structure is available only to Windows apps.

If <b>FocusRect</b> is not a valid value, or if all members of the <a href="https://docs.microsoft.com/windows/desktop/api/windef/ns-windef-tagrect">RECT</a> structure are zero, the device should focus the center of the image and the remaining members of this structure can be ignored.

The rectangle's coordinates are with respect to the preview video resolution.


### -field AutoFocusLock

If <b>TRUE</b>, the device should lock the focus to the current value.

This member should be ignored if <b>FocusRect</b> is not a valid value.


### -field AutoExposureLock

If <b>TRUE</b>, the device should lock the exposure to the current value.

This member should be ignored if <b>FocusRect</b> is not a valid value.


### -field AutoWhitebalanceLock

If <b>TRUE</b>, the device should lock the white balance setting to the current value.

This member should be ignored if <b>FocusRect</b> is not a valid value.


### -field Capabilities

Indicates whether the device and driver support setting the region of interest automatically or manually. This member a bitwise <b>OR</b> of these possible values:

<table>
<tr>
<th>Value</th>
<th>Meaning</th>
</tr>
<tr>
<td width="40%"><a id="KSPROPERTY_CAMERACONTROL_REGION_OF_INTEREST_FLAGS_AUTO"></a><a id="ksproperty_cameracontrol_region_of_interest_flags_auto"></a><dl>
<dt><b>KSPROPERTY_CAMERACONTROL_REGION_OF_INTEREST_FLAGS_AUTO</b></dt>
</dl>
</td>
<td width="60%">
The device and driver can automatically set the region of interest.

</td>
</tr>
<tr>
<td width="40%"><a id="KSPROPERTY_CAMERACONTROL_REGION_OF_INTEREST_FLAGS_MANUAL"></a><a id="ksproperty_cameracontrol_region_of_interest_flags_manual"></a><dl>
<dt><b>KSPROPERTY_CAMERACONTROL_REGION_OF_INTEREST_FLAGS_MANUAL</b></dt>
</dl>
</td>
<td width="60%">
The user can manually set the region of interest.

</td>
</tr>
<tr>
<td width="40%"><a id="KSPROPERTY_CAMERACONTROL_REGION_OF_INTEREST_FLAGS_ASYNC"></a><a id="ksproperty_cameracontrol_region_of_interest_flags_async"></a><dl>
<dt><b>KSPROPERTY_CAMERACONTROL_REGION_OF_INTEREST_FLAGS_ASYNC</b></dt>
</dl>
</td>
<td width="60%">
ROI control features execute asynchronously.

This capability is available starting with Windows 8.1.

</td>
</tr>
</table>
 


### -field Configuration

Configuration flags for control operations for the region. This is a bitwise OR combination of the following values.

This member is available starting with Windows 8.1.

<table>
<tr>
<th>Value</th>
<th>Meaning</th>
</tr>
<tr>
<td width="40%"><a id="_KSPROPERTY_CAMERACONTROL_REGION_OF_INTEREST_CONFIG_FOCUS"></a><a id="_ksproperty_cameracontrol_region_of_interest_config_focus"></a><dl>
<dt><b> KSPROPERTY_CAMERACONTROL_REGION_OF_INTEREST_CONFIG_FOCUS</b></dt>
</dl>
</td>
<td width="60%">
Set auto focus for the region.

</td>
</tr>
<tr>
<td width="40%"><a id="KSPROPERTY_CAMERACONTROL_REGION_OF_INTEREST_CONFIG_EXPOSURE"></a><a id="ksproperty_cameracontrol_region_of_interest_config_exposure"></a><dl>
<dt><b>KSPROPERTY_CAMERACONTROL_REGION_OF_INTEREST_CONFIG_EXPOSURE</b></dt>
</dl>
</td>
<td width="60%">
Set auto exposure for the region.

</td>
</tr>
<tr>
<td width="40%"><a id="KSPROPERTY_CAMERACONTROL_REGION_OF_INTEREST_CONFIG_WB"></a><a id="ksproperty_cameracontrol_region_of_interest_config_wb"></a><dl>
<dt><b>KSPROPERTY_CAMERACONTROL_REGION_OF_INTEREST_CONFIG_WB</b></dt>
</dl>
</td>
<td width="60%">
Set auto white balance for the region.

</td>
</tr>
<tr>
<td width="40%"><a id="KSPROPERTY_CAMERACONTROL_REGION_OF_INTEREST_CONVERGEMODE"></a><a id="ksproperty_cameracontrol_region_of_interest_convergemode"></a><dl>
<dt><b>KSPROPERTY_CAMERACONTROL_REGION_OF_INTEREST_CONVERGEMODE</b></dt>
</dl>
</td>
<td width="60%">
Enable convergence of objects in the region

</td>
</tr>
</table>
 


## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/stream/ksproperty-cameracontrol-flash-property">KSPROPERTY_CAMERACONTROL_FLASH_PROPERTY</a>



<a href="https://docs.microsoft.com/windows/desktop/api/windef/ns-windef-tagrect">RECT</a>
 

 

