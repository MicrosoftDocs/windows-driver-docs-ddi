---
UID: NF:icm.WcsAssociateColorProfileWithDevice
title: WcsAssociateColorProfileWithDevice function
author: windows-driver-content
description: The WcsAssociateColorProfileWithDevice function associates a specified WCS color profile with a specified device.
old-location: print\wcsassociatecolorprofilewithdevice.htm
old-project: print
ms.assetid: b1863604-e8a2-4dc7-9f2f-e0eea9baab1a
ms.author: windowsdriverdev
ms.date: 2/2/2018
ms.keywords: print.wcsassociatecolorprofilewithdevice, WcsAssociateColorProfileWithDevice function [Print Devices], WcsAssociateColorProfileWithDevice, colorfnc_2d78f2bd-52f8-48c9-a018-30b4fed5746b.xml, icm/WcsAssociateColorProfileWithDevice
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	DllExport
apilocation:
-	Mscms.dll
apiname:
-	WcsAssociateColorProfileWithDevice
product: Windows
targetos: Windows
req.typenames: WCS_PROFILE_MANAGEMENT_SCOPE
---

# WcsAssociateColorProfileWithDevice function


## -description


The <code>WcsAssociateColorProfileWithDevice</code> function associates a specified WCS color profile with a specified device.


## -syntax


````
BOOL WcsAssociateColorProfileWithDevice(
  _In_ WCS_PROFILE_MANAGEMENT_SCOPE profileManagementScope,
  _In_ PCWSTR                       pProfileName,
  _In_ PCWSTR                       pDeviceName
);
````


## -parameters




### -param scope

TBD


### -param pProfileName [in]

A pointer to the file name of the profile to associate.


### -param pDeviceName [in]

A pointer to the name of the device with which the profile is to be associated.


#### - profileManagementScope [in]

A <a href="..\icm\ne-icm-wcs_profile_management_scope.md">WCS_PROFILE_MANAGEMENT_SCOPE</a> value that specifies the scope of this profile management operation.


## -remarks



The <code>WCSAssociateColorProfileWithDevice</code> function will fail if the profile has not been installed on the computer using the <b>InstallColorProfile</b> function (described in the Windows SDK documentation).

If the <i>profileManagementScope</i> parameter is WCS_PROFILE_MANAGEMENT_SCOPE_SYSTEM_WIDE, the profile association is system-wide and applies to all users. If <i>profileManagementScope</i> is WCS_PROFILE_MANAGEMENT_SCOPE_CURRENT_USER, the association is only for the current user.

This function is executable in Least-Privileged User Account (LUA) context if <i>profileManagementScope</i> is WCS_PROFILE_MANAGEMENT_SCOPE_CURRENT_USER. Otherwise, administrative privileges are required..




## -see-also

<a href="..\icm\nf-icm-wcsdisassociatecolorprofilefromdevice.md">WcsDisassociateColorProfileFromDevice</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [print\print]:%20WcsAssociateColorProfileWithDevice function%20 RELEASE:%20(2/2/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

