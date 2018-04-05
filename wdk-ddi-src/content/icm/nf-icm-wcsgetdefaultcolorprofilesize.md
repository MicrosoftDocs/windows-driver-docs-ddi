---
UID: NF:icm.WcsGetDefaultColorProfileSize
title: WcsGetDefaultColorProfileSize function
author: windows-driver-content
description: The WcsGetDefaultColorProfileSize function returns the size, in bytes, of the default color profile name for a device, including the NULL terminator.
old-location: print\wcsgetdefaultcolorprofilesize.htm
old-project: print
ms.assetid: d04306e2-3479-4ba4-ac4d-bf3715487fcf
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: WcsGetDefaultColorProfileSize, WcsGetDefaultColorProfileSize function [Print Devices], colorfnc_8259a030-267a-4d53-93fe-73e63f0e5fd7.xml, icm/WcsGetDefaultColorProfileSize, print.wcsgetdefaultcolorprofilesize
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
-   WcsGetDefaultColorProfileSize
product:
- Windows
targetos: Windows
req.typenames: WCS_PROFILE_MANAGEMENT_SCOPE
---

# WcsGetDefaultColorProfileSize function


## -description


The <code>WcsGetDefaultColorProfileSize</code> function returns the size, in bytes, of the default color profile name for a device, including the <b>NULL</b> terminator.


## -parameters




### -param scope




### -param pDeviceName [in, optional]

A pointer to the name of the device for which the default color profile is to be obtained. If <b>NULL</b>, a device-independent default profile will be used.


### -param cptColorProfileType [in]

A <a href="https://msdn.microsoft.com/library/windows/hardware/ff546018">COLORPROFILETYPE</a> value that specifies the color profile type.


### -param cpstColorProfileSubType [in]

A <a href="https://msdn.microsoft.com/library/windows/hardware/ff546012">COLORPROFILESUBTYPE</a> value that specifies the color profile subtype.


### -param dwProfileID [in]

The ID of the color space that the color profile represents.


### -param pcbProfileName [out]

A pointer to a location that receives the size, in bytes, of the path name of the default color profile, including the null terminator.


#### - profileManagementScope [in]


      A <a href="https://msdn.microsoft.com/library/windows/hardware/ff563752">WCS_PROFILE_MANAGEMENT_SCOPE</a> value that specifies the scope of this profile management operation.


## -remarks



Use this function to return the required size of the buffer pointed to by the <i>pProfileName</i> parameter in the <a href="https://msdn.microsoft.com/library/windows/hardware/ff563726">WcsGetDefaultColorProfile</a> function.

This function is executable in Least-Privileged User Account (LUA) context.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff546012">COLORPROFILESUBTYPE</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff546018">COLORPROFILETYPE</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff563752">WCS_PROFILE_MANAGEMENT_SCOPE</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff563726">WcsGetDefaultColorProfile</a>
Â

Â

