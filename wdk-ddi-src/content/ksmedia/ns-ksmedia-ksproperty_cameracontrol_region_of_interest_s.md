---
UID: NS:ksmedia.KSPROPERTY_CAMERACONTROL_REGION_OF_INTEREST_S
title: KSPROPERTY_CAMERACONTROL_REGION_OF_INTEREST_S
author: windows-driver-content
description: Describes region of interest (ROI) control properties in the PROPSETID_VIDCAP_CAMERACONTROL_REGION_OF_INTEREST camera control property set.
old-location: stream\ksproperty_cameracontrol_region_of_interest_s.htm
old-project: stream
ms.assetid: 0a488d9f-1e34-4482-a2a8-7c160b00766c
ms.author: windowsdriverdev
ms.date: 1/9/2018
ms.keywords: KSPROPERTY_CAMERACONTROL_REGION_OF_INTEREST_S, *PKSPROPERTY_CAMERACONTROL_REGION_OF_INTEREST_S, KSPROPERTY_CAMERACONTROL_REGION_OF_INTEREST_S
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: ksmedia.h
req.include-header: Ksmedia.h
req.target-type: Windows
req.target-min-winverclnt: Windows 8
req.target-min-winversvr: Windows Server 2012
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: KSPROPERTY_CAMERACONTROL_REGION_OF_INTEREST_S
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
req.typenames: *PKSPROPERTY_CAMERACONTROL_REGION_OF_INTEREST_S, KSPROPERTY_CAMERACONTROL_REGION_OF_INTEREST_S
---

# KSPROPERTY_CAMERACONTROL_REGION_OF_INTEREST_S structure



## -description
Describes region of interest (ROI) control properties in the <b>PROPSETID_VIDCAP_CAMERACONTROL_REGION_OF_INTEREST</b> camera control property set. The region of interest is a rectangle in the image that is used to focus the camera. This structure specifies property values that are used in requests to the camera driver.



## -syntax

````
typedef struct {
  RECT  FocusRect;
  BOOL  AutoFocusLock;
  BOOL  AutoExposureLock;
  BOOL  AutoWhitebalanceLock;
  union {
    ULONG Capabilities;
    ULONG Configuration;
  };
} KSPROPERTY_CAMERACONTROL_REGION_OF_INTEREST_S, *PKSPROPERTY_CAMERACONTROL_REGION_OF_INTEREST_S;
````


## -struct-fields

### -field FocusRect

A <a href="https://msdn.microsoft.com/library/windows/hardware/ff569234">RECT</a> structure that specifies the rectangular region in which the device should set the focus. This structure is available only to Windows apps.

If <b>FocusRect</b> is not a valid value, or if all members of the <a href="https://msdn.microsoft.com/library/windows/hardware/ff569234">RECT</a> structure are zero, the device should focus the center of the image and the remaining members of this structure can be ignored.

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

### -field KSPROPERTY_CAMERACONTROL_REGION_OF_INTEREST_FLAGS_AUTO

</td>
<td width="60%">
The device and driver can automatically set the region of interest.

</td>
</tr>
<tr>

### -field KSPROPERTY_CAMERACONTROL_REGION_OF_INTEREST_FLAGS_MANUAL

</td>
<td width="60%">
The user can manually set the region of interest.

</td>
</tr>
<tr>

### -field KSPROPERTY_CAMERACONTROL_REGION_OF_INTEREST_FLAGS_ASYNC

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

### -field  KSPROPERTY_CAMERACONTROL_REGION_OF_INTEREST_CONFIG_FOCUS

</td>
<td width="60%">
Set auto focus for the region.

</td>
</tr>
<tr>

### -field KSPROPERTY_CAMERACONTROL_REGION_OF_INTEREST_CONFIG_EXPOSURE

</td>
<td width="60%">
Set auto exposure for the region.

</td>
</tr>
<tr>

### -field KSPROPERTY_CAMERACONTROL_REGION_OF_INTEREST_CONFIG_WB

</td>
<td width="60%">
Set auto white balance for the region.

</td>
</tr>
<tr>

### -field KSPROPERTY_CAMERACONTROL_REGION_OF_INTEREST_CONVERGEMODE

</td>
<td width="60%">
Enable convergence of objects in the region

</td>
</tr>
</table>
 


## -remarks


## -see-also
<dl>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/jj156041">KSPROPERTY_CAMERACONTROL_FLASH_PROPERTY</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff569234">RECT</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [stream\stream]:%20KSPROPERTY_CAMERACONTROL_REGION_OF_INTEREST_S structure%20 RELEASE:%20(1/9/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

