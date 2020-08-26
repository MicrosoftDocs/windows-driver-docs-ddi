---
UID: NF:icm.WcsGetDefaultColorProfileSize
title: WcsGetDefaultColorProfileSize function (icm.h)
description: The WcsGetDefaultColorProfileSize function returns the size, in bytes, of the default color profile name for a device, including the NULL terminator.
old-location: print\wcsgetdefaultcolorprofilesize.htm
tech.root: print
ms.assetid: d04306e2-3479-4ba4-ac4d-bf3715487fcf
ms.date: 08/26/2020
keywords: ["WcsGetDefaultColorProfileSize function"]
ms.keywords: WcsGetDefaultColorProfileSize, WcsGetDefaultColorProfileSize function [Print Devices], colorfnc_8259a030-267a-4d53-93fe-73e63f0e5fd7.xml, icm/WcsGetDefaultColorProfileSize, print.wcsgetdefaultcolorprofilesize
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
topic_type:
-   APIRef
-   kbSyntax
api_type:
-   DllExport
api_location:
-   Mscms.dll
api_name:
-   WcsGetDefaultColorProfileSize
targetos: Windows
req.typenames: 
---

# WcsGetDefaultColorProfileSize function

## -description

The **WcsGetDefaultColorProfileSize** function returns the size, in bytes, of the default color profile name for a device, including the **NULL** terminator.

## -parameters

### -param scope

### -param pDeviceName

[in, optional] A pointer to the name of the device for which the default color profile is to be obtained. If **NULL**, a device-independent default profile will be used.

The device name for a monitor can be obtained from [DISPLAY_DEVICE.DeviceID](https://docs.microsoft.com/windows/win32/api/wingdi/ns-wingdi-display_devicea).

### -param cptColorProfileType

[in] A [COLORPROFILETYPE](https://docs.microsoft.com/previous-versions/windows/desktop/wcs/colorprofiletype) value that specifies the color profile type.

### -param cpstColorProfileSubType

[in] A [COLORPROFILESUBTYPE](https://docs.microsoft.com/previous-versions/windows/desktop/wcs/colorprofilesubtype) value that specifies the color profile subtype.

### -param dwProfileID

[in] The ID of the color space that the color profile represents.

### -param pcbProfileName

[out] A pointer to a location that receives the size, in bytes, of the path name of the default color profile, including the null terminator.

#### - profileManagementScope

[in] A [WCS_PROFILE_MANAGEMENT_SCOPE](https://docs.microsoft.com/previous-versions/windows/desktop/wcs/wcs-profile-management-scope) value that specifies the scope of this profile management operation.

## -remarks

Use this function to return the required size of the buffer pointed to by the *pProfileName* parameter in the [WcsGetDefaultColorProfile](https://docs.microsoft.com/windows-hardware/drivers/ddi/content/icm/nf-icm-wcsgetdefaultcolorprofile) function.

This function is executable in Least-Privileged User Account (LUA) context.

## -see-also

[COLORPROFILESUBTYPE](https://docs.microsoft.com/previous-versions/windows/desktop/wcs/colorprofilesubtype)

[COLORPROFILETYPE](https://docs.microsoft.com/previous-versions/windows/desktop/wcs/colorprofiletype)

[WCS_PROFILE_MANAGEMENT_SCOPE](https://docs.microsoft.com/previous-versions/windows/desktop/wcs/wcs-profile-management-scope)

[WcsGetDefaultColorProfile](https://docs.microsoft.com/windows-hardware/drivers/ddi/content/icm/nf-icm-wcsgetdefaultcolorprofile)
