---
UID: NF:icm.WcsDisassociateColorProfileFromDevice
title: WcsDisassociateColorProfileFromDevice function
author: windows-driver-content
description: The WcsDisassociateColorProfileFromDevice function disassociates a specified WCS color profile from a specified device.
old-location: print\wcsdisassociatecolorprofilefromdevice.htm
old-project: print
ms.assetid: d2ab6fe4-131a-4952-864c-7135026cb25c
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: WcsDisassociateColorProfileFromDevice, WcsDisassociateColorProfileFromDevice function [Print Devices], colorfnc_d8888a37-8a72-41a4-8ca6-29326634d9b2.xml, icm/WcsDisassociateColorProfileFromDevice, print.wcsdisassociatecolorprofilefromdevice
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: icm.h
req.include-header: 
req.target-type: Universal
req.target-min-winverclnt: Included in Windows Vista and later.
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
-	APIRef
-	kbSyntax
api_type:
-	DllExport
api_location:
-	Mscms.dll
api_name:
-	WcsDisassociateColorProfileFromDevice
product: Windows
targetos: Windows
req.typenames: WCS_PROFILE_MANAGEMENT_SCOPE
---

# WcsDisassociateColorProfileFromDevice function


## -description


The <code>WcsDisassociateColorProfileFromDevice</code> function disassociates a specified WCS color profile from a specified device.


## -syntax


````
BOOL WcsDisassociateColorProfileFromDevice(
  _In_ WCS_PROFILE_MANAGEMENT_SCOPE profileManagementScope,
  _In_ PCWSTR                       pProfileName,
  _In_ PCWSTR                       pDeviceName
);
````


## -parameters




### -param scope

TBD


### -param pProfileName [in]

A pointer to the file name of the profile to disassociate.


### -param pDeviceName [in]

A pointer to the name of the device from which the profile is to be disassociated.


#### - profileManagementScope [in]

A <a href="..\icm\ne-icm-wcs_profile_management_scope.md">WCS_PROFILE_MANAGEMENT_SCOPE</a> value that specifies the scope of this profile management operation.


## -remarks



The WCS color profile should be installed on the system and must have been associated with the device using the same value for the <i>profileManagementScope</i> parameter.

If <i>profileManagementScope</i> is WCS_PROFILE_MANAGEMENT_SCOPE_SYSTEM_WIDE, the profile disassociation is system-wide and applies to all users. If <i>profileManagementScope</i> is WCS_PROFILE_MANAGEMENT_SCOPE_CURRENT_USER, the disassociation is only for the current user.

If more than one WCS color profile is associated with a device, WCS uses the last one associated as the default. That is, if your application sequentially associates three profiles with a device, WCS will use the last one associated as the default. If your application then calls the <code>WcsDisassociateColorProfileFromDevice</code> function to disassociate the third profile (which is the default in this example), WCS will use the second profile as the default.

If your application disassociates all profiles from a device, WCS uses the sRGB profile as the default.

This function is executable in Least-Privileged User Account (LUA) context if <i>profileManagementScope</i> is WCS_PROFILE_MANAGEMENT_SCOPE_CURRENT_USER. Otherwise, administrative privileges are required..




## -see-also

<a href="..\icm\nf-icm-wcsassociatecolorprofilewithdevice.md">WcsAssociateColorProfileWithDevice</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [print\print]:%20WcsDisassociateColorProfileFromDevice function%20 RELEASE:%20(2/26/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

