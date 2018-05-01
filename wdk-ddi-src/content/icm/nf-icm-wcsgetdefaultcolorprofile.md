---
UID: NF:icm.WcsGetDefaultColorProfile
title: WcsGetDefaultColorProfile function
author: windows-driver-content
description: The WcsGetDefaultColorProfile function retrieves the default color profile for a device, or the device-independent default if the device is not specified.
old-location: print\wcsgetdefaultcolorprofile.htm
old-project: print
ms.assetid: a5ace7f3-dc61-4799-b129-3c25c392ebf6
ms.author: windowsdriverdev
ms.date: 4/20/2018
ms.keywords: WcsGetDefaultColorProfile, WcsGetDefaultColorProfile function [Print Devices], colorfnc_c7de4cff-ebfb-4392-a2a2-1229a6b08aa1.xml, icm/WcsGetDefaultColorProfile, print.wcsgetdefaultcolorprofile
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
-	WcsGetDefaultColorProfile
product: Windows
targetos: Windows
req.typenames: 
---

# WcsGetDefaultColorProfile function


## -description


The <code>WcsGetDefaultColorProfile</code> function retrieves the default color profile for a device, or the device-independent default if the device is not specified.


## -parameters




### -param scope

TBD


### -param pDeviceName [in, optional]

A pointer to the name of the device for which the default color profile is to be obtained. If <b>NULL</b>, a device-independent default profile will be obtained.


### -param cptColorProfileType [in]

A <a href="https://msdn.microsoft.com/library/windows/hardware/ff546018">COLORPROFILETYPE</a> value that specifies the color profile type.


### -param cpstColorProfileSubType [in]

A <a href="https://msdn.microsoft.com/library/windows/hardware/ff546012">COLORPROFILESUBTYPE</a> value that specifies the color profile subtype.


### -param dwProfileID [in]

The ID of the color space that the color profile represents.


### -param cbProfileName [in]

The buffer size, in bytes, of the buffer pointed to by <i>pProfileName</i>.


### -param pProfileName [out]

A pointer to a buffer to receive the name of the color profile.


#### - profileManagementScope [in]

A <a href="https://msdn.microsoft.com/library/windows/hardware/ff563752">WCS_PROFILE_MANAGEMENT_SCOPE</a> value that specifies the scope of this profile management operation.


## -remarks



Use the <a href="https://msdn.microsoft.com/library/windows/hardware/ff563730">WcsGetDefaultColorProfileSize</a> function to obtain the required size of the buffer pointed to by the <i>pProfileName</i> parameter.

If WCS_PROFILE_MANAGEMENT_SCOPE_CURRENT_USER, the current user setting, is present, it overrides the system-wide default for <i>profileManagementScope</i>.

This function is executable in Least-Privileged User Account (LUA) context.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff546012">COLORPROFILESUBTYPE</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff546018">COLORPROFILETYPE</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff563752">WCS_PROFILE_MANAGEMENT_SCOPE</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff563730">WcsGetDefaultColorProfileSize</a>
 

 

