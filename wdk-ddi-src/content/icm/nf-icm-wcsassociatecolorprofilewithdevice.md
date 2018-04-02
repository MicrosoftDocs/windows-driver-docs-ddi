---
UID: NF:icm.WcsAssociateColorProfileWithDevice
title: WcsAssociateColorProfileWithDevice function
author: windows-driver-content
description: The WcsAssociateColorProfileWithDevice function associates a specified WCS color profile with a specified device.
old-location: print\wcsassociatecolorprofilewithdevice.htm
old-project: print
ms.assetid: b1863604-e8a2-4dc7-9f2f-e0eea9baab1a
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: WcsAssociateColorProfileWithDevice, WcsAssociateColorProfileWithDevice function [Print Devices], colorfnc_2d78f2bd-52f8-48c9-a018-30b4fed5746b.xml, icm/WcsAssociateColorProfileWithDevice, print.wcsassociatecolorprofilewithdevice
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
-	WcsAssociateColorProfileWithDevice
product: Windows
targetos: Windows
req.typenames: WCS_PROFILE_MANAGEMENT_SCOPE
---

# WcsAssociateColorProfileWithDevice function


## -description


The <code>WcsAssociateColorProfileWithDevice</code> function associates a specified WCS color profile with a specified device.


## -parameters




### -param scope

TBD


### -param pProfileName [in]

A pointer to the file name of the profile to associate.


### -param pDeviceName [in]

A pointer to the name of the device with which the profile is to be associated.


#### - profileManagementScope [in]

A <a href="https://msdn.microsoft.com/library/windows/hardware/ff563752">WCS_PROFILE_MANAGEMENT_SCOPE</a> value that specifies the scope of this profile management operation.


## -remarks



The <code>WCSAssociateColorProfileWithDevice</code> function will fail if the profile has not been installed on the computer using the <b>InstallColorProfile</b> function (described in the Windows SDK documentation).

If the <i>profileManagementScope</i> parameter is WCS_PROFILE_MANAGEMENT_SCOPE_SYSTEM_WIDE, the profile association is system-wide and applies to all users. If <i>profileManagementScope</i> is WCS_PROFILE_MANAGEMENT_SCOPE_CURRENT_USER, the association is only for the current user.

This function is executable in Least-Privileged User Account (LUA) context if <i>profileManagementScope</i> is WCS_PROFILE_MANAGEMENT_SCOPE_CURRENT_USER. Otherwise, administrative privileges are required..




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff563718">WcsDisassociateColorProfileFromDevice</a>
 

 

