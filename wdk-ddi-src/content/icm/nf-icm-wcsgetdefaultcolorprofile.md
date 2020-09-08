---
UID: NF:icm.WcsGetDefaultColorProfile
title: WcsGetDefaultColorProfile function (icm.h)
description: The WcsGetDefaultColorProfile function retrieves the default color profile for a device, or the device-independent default if the device is not specified.
old-location: print\wcsgetdefaultcolorprofile.htm
tech.root: print
ms.assetid: a5ace7f3-dc61-4799-b129-3c25c392ebf6
ms.date: 08/26/2020
keywords: ["WcsGetDefaultColorProfile function"]
ms.keywords: WcsGetDefaultColorProfile, WcsGetDefaultColorProfile function [Print Devices], colorfnc_c7de4cff-ebfb-4392-a2a2-1229a6b08aa1.xml, icm/WcsGetDefaultColorProfile, print.wcsgetdefaultcolorprofile
req.header: icm.h
req.include-header: 
req.target-type: Universal
req.target-min-winverclnt: 
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
req.lib: Mscms.lib
req.dll: Mscms.dll
req.irql: 
targetos: Windows
req.typenames: 
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - DllExport
api_location:
 - Mscms.dll
api_name:
 - WcsGetDefaultColorProfile
f1_keywords:
 - WcsGetDefaultColorProfile
 - icm/WcsGetDefaultColorProfile
---

# WcsGetDefaultColorProfile function


## -description

The **WcsGetDefaultColorProfile** function retrieves the default color profile for a device, or the device-independent default if the device is not specified.

## -parameters

### -param scope

### -param pDeviceName

[in, optional] A pointer to the name of the device for which the default color profile is to be obtained. If **NULL**, a device-independent default profile will be obtained.

The device name for a monitor can be obtained from [DISPLAY_DEVICE.DeviceID](https://docs.microsoft.com/windows/win32/api/wingdi/ns-wingdi-display_devicea).

### -param cptColorProfileType

[in] A [COLORPROFILETYPE](https://docs.microsoft.com/previous-versions/windows/desktop/wcs/colorprofiletype) value that specifies the color profile type.

### -param cpstColorProfileSubType

[in] A [COLORPROFILESUBTYPE](https://docs.microsoft.com/previous-versions/windows/desktop/wcs/colorprofilesubtype) value that specifies the color profile subtype.

### -param dwProfileID [in]

The ID of the color space that the color profile represents.

### -param cbProfileName [in]

The buffer size, in bytes, of the buffer pointed to by *pProfileName*.

### -param pProfileName

[out] A pointer to a buffer to receive the name of the color profile.

#### - profileManagementScope [in]

A [WCS_PROFILE_MANAGEMENT_SCOPE](https://docs.microsoft.com/previous-versions/windows/desktop/wcs/wcs-profile-management-scope) value that specifies the scope of this profile management operation.

## -remarks

Use the [WcsGetDefaultColorProfileSize](https://docs.microsoft.com/windows-hardware/drivers/ddi/content/icm/nf-icm-wcsgetdefaultcolorprofilesize) function to obtain the required size of the buffer pointed to by the *pProfileName* parameter.

If WCS_PROFILE_MANAGEMENT_SCOPE_CURRENT_USER, the current user setting, is present, it overrides the system-wide default for *profileManagementScope*.

This function is executable in Least-Privileged User Account (LUA) context.

## -see-also

[COLORPROFILESUBTYPE](https://docs.microsoft.com/previous-versions/windows/desktop/wcs/colorprofilesubtype)

[COLORPROFILETYPE](https://docs.microsoft.com/previous-versions/windows/desktop/wcs/colorprofiletype)

[WCS_PROFILE_MANAGEMENT_SCOPE](https://docs.microsoft.com/previous-versions/windows/desktop/wcs/wcs-profile-management-scope)

[WcsGetDefaultColorProfileSize](https://docs.microsoft.com/windows-hardware/drivers/ddi/content/icm/nf-icm-wcsgetdefaultcolorprofilesize)

