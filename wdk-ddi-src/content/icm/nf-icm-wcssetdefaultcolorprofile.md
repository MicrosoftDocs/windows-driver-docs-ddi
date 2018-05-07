---
UID: NF:icm.WcsSetDefaultColorProfile
title: WcsSetDefaultColorProfile function
author: windows-driver-content
description: The WcsSetDefaultColorProfile function sets the default color profile name of the specified profile type in the specified profile management scope.
old-location: print\wcssetdefaultcolorprofile.htm
old-project: print
ms.assetid: 302f271c-801e-409c-a0fc-53f01e5e2055
ms.author: windowsdriverdev
ms.date: 4/20/2018
ms.keywords: WcsSetDefaultColorProfile, WcsSetDefaultColorProfile function [Print Devices], colorfnc_31c96c7b-5616-4bdb-8df8-23e2361a9554.xml, icm/WcsSetDefaultColorProfile, print.wcssetdefaultcolorprofile
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


### -param cptColorProfileType [in]

A <a href="https://msdn.microsoft.com/library/windows/hardware/ff546018">COLORPROFILETYPE</a> value that specifies the color profile type.


### -param cpstColorProfileSubType [in]

A <a href="https://msdn.microsoft.com/library/windows/hardware/ff546012">COLORPROFILESUBTYPE</a> value that specifies the color profile subtype.


### -param dwProfileID [in]

The ID of the color space that the color profile represents.


### -param pProfileName [in, optional]

A pointer to a buffer to receive the name of the color profile. See Remarks.


#### - profileManagementScope [in]


      A <a href="https://msdn.microsoft.com/library/windows/hardware/ff563752">WCS_PROFILE_MANAGEMENT_SCOPE</a> value that specifies the scope of this profile management operation.


## -remarks



If the <i>pProfileName</i> parameter is <b>NULL</b> and the <i>profileManagementScope</i> parameter is WCS_PROFILE_MANAGEMENT_SCOPE_CURRENT_USER, subsequent calls to <b>WcsSetDefaultColorProfile</b> will return the system-wide default profile.

This function is executable in Least-Privileged User Account (LUA) context if <i>profileManagementScope</i> is WCS_PROFILE_MANAGEMENT_SCOPE_CURRENT_USER. Otherwise, administrative privileges are required. The specified profile must already be installed, but it need not yet be associated with the specified device in the specified profile management scope..




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff546012">COLORPROFILESUBTYPE</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff546018">COLORPROFILETYPE</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff563752">WCS_PROFILE_MANAGEMENT_SCOPE</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff563730">WcsGetDefaultColorProfileSize</a>
Â

Â

