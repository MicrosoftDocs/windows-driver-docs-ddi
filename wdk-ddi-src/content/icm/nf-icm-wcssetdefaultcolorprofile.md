---
UID: NF:icm.WcsSetDefaultColorProfile
title: WcsSetDefaultColorProfile function
description: The WcsSetDefaultColorProfile function sets the default color profile name of the specified profile type in the specified profile management scope.
old-location: print\wcssetdefaultcolorprofile.htm
tech.root: print
ms.assetid: 302f271c-801e-409c-a0fc-53f01e5e2055
ms.date: 08/20/2018
ms.keywords: WcsSetDefaultColorProfile, WcsSetDefaultColorProfile function [Print Devices], colorfnc_31c96c7b-5616-4bdb-8df8-23e2361a9554.xml, icm/WcsSetDefaultColorProfile, print.wcssetdefaultcolorprofile
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
-   WcsSetDefaultColorProfile
product:
- Windows
targetos: Windows
req.typenames: 
---

# WcsSetDefaultColorProfile function


## -description


The <code>WcsSetDefaultColorProfile</code> function sets the default color profile name of the specified profile type in the specified profile management scope.


## -parameters




### -param scope




### -param pDeviceName [in, optional]

A pointer to the name of the device for which the default color profile is to be set. If <b>NULL</b>, a device-independent default profile will be used. 

The device name for a monitor can be obtained from [DISPLAY_DEVICE.DeviceID](https://docs.microsoft.com/windows/desktop/api/wingdi/ns-wingdi-_display_devicea).



### -param cptColorProfileType [in]

A [COLORPROFILETYPE](https://docs.microsoft.com/windows-hardware/drivers/ddi/content/icm/ne-icm-colorprofiletype) value that specifies the color profile type.


### -param cpstColorProfileSubType [in]

A [COLORPROFILESUBTYPE](https://docs.microsoft.com/windows-hardware/drivers/ddi/content/icm/ne-icm-colorprofilesubtype) value that specifies the color profile subtype.


### -param dwProfileID [in]

The ID of the color space that the color profile represents.


### -param pProfileName [in, optional]

A pointer to a buffer to receive the name of the color profile. See Remarks.


#### - profileManagementScope [in]

A [WCS_PROFILE_MANAGEMENT_SCOPE](https://docs.microsoft.com/windows-hardware/drivers/ddi/content/icm/ne-icm-wcs_profile_management_scope) value that specifies the scope of this profile management operation.


## -remarks


If the <i>pProfileName</i> parameter is <b>NULL</b> and the <i>profileManagementScope</i> parameter is WCS_PROFILE_MANAGEMENT_SCOPE_CURRENT_USER, subsequent calls to <b>WcsSetDefaultColorProfile</b> will return the system-wide default profile.

This function is executable in Least-Privileged User Account (LUA) context if <i>profileManagementScope</i> is WCS_PROFILE_MANAGEMENT_SCOPE_CURRENT_USER. Otherwise, administrative privileges are required. The specified profile must already be installed, but it need not yet be associated with the specified device in the specified profile management scope..


## -see-also

[COLORPROFILESUBTYPE](https://docs.microsoft.com/windows-hardware/drivers/ddi/content/icm/ne-icm-colorprofilesubtype)

[COLORPROFILETYPE](https://docs.microsoft.com/windows-hardware/drivers/ddi/content/icm/ne-icm-colorprofiletype)

[WCS_PROFILE_MANAGEMENT_SCOPE](https://docs.microsoft.com/windows-hardware/drivers/ddi/content/icm/ne-icm-wcs_profile_management_scope)

[WcsGetDefaultColorProfileSize](https://docs.microsoft.com/windows-hardware/drivers/ddi/content/icm/nf-icm-wcsgetdefaultcolorprofilesize)
