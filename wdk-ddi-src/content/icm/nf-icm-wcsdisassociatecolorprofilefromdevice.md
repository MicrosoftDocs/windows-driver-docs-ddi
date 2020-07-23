---
UID: NF:icm.WcsDisassociateColorProfileFromDevice
title: WcsDisassociateColorProfileFromDevice function (icm.h)
description: The WcsDisassociateColorProfileFromDevice function disassociates a specified WCS color profile from a specified device.
old-location: print\wcsdisassociatecolorprofilefromdevice.htm
tech.root: print
ms.assetid: d2ab6fe4-131a-4952-864c-7135026cb25c
ms.date: 08/20/2018
keywords: ["WcsDisassociateColorProfileFromDevice function"]
ms.keywords: WcsDisassociateColorProfileFromDevice, WcsDisassociateColorProfileFromDevice function [Print Devices], colorfnc_d8888a37-8a72-41a4-8ca6-29326634d9b2.xml, icm/WcsDisassociateColorProfileFromDevice, print.wcsdisassociatecolorprofilefromdevice
ms.topic: function
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
-   WcsDisassociateColorProfileFromDevice
targetos: Windows
req.typenames: 
---

# WcsDisassociateColorProfileFromDevice function


## -description


The <code>WcsDisassociateColorProfileFromDevice</code> function disassociates a specified WCS color profile from a specified device.


## -parameters




### -param scope




### -param pProfileName [in]

A pointer to the file name of the profile to disassociate.


### -param pDeviceName [in]

A pointer to the name of the device from which the profile is to be disassociated.

The device name for a monitor can be obtained from [DISPLAY_DEVICE.DeviceID](https://docs.microsoft.com/windows/win32/api/wingdi/ns-wingdi-display_devicea).


#### - profileManagementScope [in]

A [WCS_PROFILE_MANAGEMENT_SCOPE](https://docs.microsoft.com/windows-hardware/drivers/ddi/content/icm/ne-icm-wcs_profile_management_scope) value that specifies the scope of this profile management operation.


## -remarks


The WCS color profile should be installed on the system and must have been associated with the device using the same value for the <i>profileManagementScope</i> parameter.

If <i>profileManagementScope</i> is WCS_PROFILE_MANAGEMENT_SCOPE_SYSTEM_WIDE, the profile disassociation is system-wide and applies to all users. If <i>profileManagementScope</i> is WCS_PROFILE_MANAGEMENT_SCOPE_CURRENT_USER, the disassociation is only for the current user.

If more than one WCS color profile is associated with a device, WCS uses the last one associated as the default. That is, if your application sequentially associates three profiles with a device, WCS will use the last one associated as the default. If your application then calls the <code>WcsDisassociateColorProfileFromDevice</code> function to disassociate the third profile (which is the default in this example), WCS will use the second profile as the default.

If your application disassociates all profiles from a device, WCS uses the sRGB profile as the default.

This function is executable in Least-Privileged User Account (LUA) context if <i>profileManagementScope</i> is WCS_PROFILE_MANAGEMENT_SCOPE_CURRENT_USER. Otherwise, administrative privileges are required..

## -see-also

[WcsAssociateColorProfileWithDevice](https://docs.microsoft.com/windows-hardware/drivers/ddi/content/icm/nf-icm-wcsassociatecolorprofilewithdevice)
