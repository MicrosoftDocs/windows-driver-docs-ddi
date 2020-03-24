---
UID: NF:icm.WcsAssociateColorProfileWithDevice
title: WcsAssociateColorProfileWithDevice function (icm.h)
description: The WcsAssociateColorProfileWithDevice function associates a specified WCS color profile with a specified device.
old-location: print\wcsassociatecolorprofilewithdevice.htm
tech.root: print
ms.assetid: b1863604-e8a2-4dc7-9f2f-e0eea9baab1a
ms.date: 08/20/2018
keywords: ["WcsAssociateColorProfileWithDevice function"]
ms.keywords: WcsAssociateColorProfileWithDevice, WcsAssociateColorProfileWithDevice function [Print Devices], colorfnc_2d78f2bd-52f8-48c9-a018-30b4fed5746b.xml, icm/WcsAssociateColorProfileWithDevice, print.wcsassociatecolorprofilewithdevice
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
-   WcsAssociateColorProfileWithDevice
product:
- Windows
targetos: Windows
req.typenames: 
---

# WcsAssociateColorProfileWithDevice function


## -description


The <code>WcsAssociateColorProfileWithDevice</code> function associates a specified WCS color profile with a specified device.


## -parameters




### -param scope




### -param pProfileName [in]

A pointer to the file name of the profile to associate.


### -param pDeviceName [in]

A pointer to the name of the device with which the profile is to be associated.

The device name for a monitor can be obtained from [DISPLAY_DEVICE.DeviceID](https://docs.microsoft.com/windows/desktop/api/wingdi/ns-wingdi-_display_devicea).


#### - profileManagementScope [in]

A [WCS_PROFILE_MANAGEMENT_SCOPE](https://docs.microsoft.com/windows-hardware/drivers/ddi/content/icm/ne-icm-wcs_profile_management_scope) value that specifies the scope of this profile management operation.


## -remarks

The <code>WCSAssociateColorProfileWithDevice</code> function will fail if the profile has not been installed on the computer using the <b>InstallColorProfile</b> function (described in the Windows SDK documentation).

If the <i>profileManagementScope</i> parameter is WCS_PROFILE_MANAGEMENT_SCOPE_SYSTEM_WIDE, the profile association is system-wide and applies to all users. If <i>profileManagementScope</i> is WCS_PROFILE_MANAGEMENT_SCOPE_CURRENT_USER, the association is only for the current user.

This function is executable in Least-Privileged User Account (LUA) context if <i>profileManagementScope</i> is WCS_PROFILE_MANAGEMENT_SCOPE_CURRENT_USER. Otherwise, administrative privileges are required..


## -see-also

[WcsDisassociateColorProfileFromDevice](https://docs.microsoft.com/windows-hardware/drivers/ddi/content/icm/nf-icm-wcsdisassociatecolorprofilefromdevice)
