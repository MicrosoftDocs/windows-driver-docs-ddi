---
UID: NF:icm.WcsGetDefaultColorProfileSize
title: WcsGetDefaultColorProfileSize function
author: windows-driver-content
description: The WcsGetDefaultColorProfileSize function returns the size, in bytes, of the default color profile name for a device, including the NULL terminator.
old-location: print\wcsgetdefaultcolorprofilesize.htm
old-project: print
ms.assetid: d04306e2-3479-4ba4-ac4d-bf3715487fcf
ms.author: windowsdriverdev
ms.date: 1/18/2018
ms.keywords: icm/WcsGetDefaultColorProfileSize, WcsGetDefaultColorProfileSize function [Print Devices], colorfnc_8259a030-267a-4d53-93fe-73e63f0e5fd7.xml, print.wcsgetdefaultcolorprofilesize, WcsGetDefaultColorProfileSize
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
-	WcsGetDefaultColorProfileSize
product: Windows
targetos: Windows
req.typenames: WCS_PROFILE_MANAGEMENT_SCOPE
---

# WcsGetDefaultColorProfileSize function


## -description


The <code>WcsGetDefaultColorProfileSize</code> function returns the size, in bytes, of the default color profile name for a device, including the <b>NULL</b> terminator.


## -syntax


````
BOOL WcsGetDefaultColorProfileSize(
  _In_     WCS_PROFILE_MANAGEMENT_SCOPE profileManagementScope,
  _In_opt_ PCWSTR                       pDeviceName,
  _In_     COLORPROFILETYPE             cptColorProfileType,
  _In_     COLORPROFILESUBTYPE          cpstColorProfileSubType,
  _In_     DWORD                        dwProfileID,
  _Out_    PDWORD                       pcbProfileName
);
````


## -parameters




### -param scope

TBD


### -param pDeviceName [in, optional]

A pointer to the name of the device for which the default color profile is to be obtained. If <b>NULL</b>, a device-independent default profile will be used.


### -param cptColorProfileType [in]

A <a href="..\icm\ne-icm-colorprofiletype.md">COLORPROFILETYPE</a> value that specifies the color profile type.


### -param cpstColorProfileSubType [in]

A <a href="..\icm\ne-icm-colorprofilesubtype.md">COLORPROFILESUBTYPE</a> value that specifies the color profile subtype.


### -param dwProfileID [in]

The ID of the color space that the color profile represents.


### -param pcbProfileName [out]

A pointer to a location that receives the size, in bytes, of the path name of the default color profile, including the null terminator.


#### - profileManagementScope [in]


      A <a href="..\icm\ne-icm-wcs_profile_management_scope.md">WCS_PROFILE_MANAGEMENT_SCOPE</a> value that specifies the scope of this profile management operation.


## -remarks


Use this function to return the required size of the buffer pointed to by the <i>pProfileName</i> parameter in the <a href="..\icm\nf-icm-wcsgetdefaultcolorprofile.md">WcsGetDefaultColorProfile</a> function.

This function is executable in Least-Privileged User Account (LUA) context.



## -see-also

<a href="..\icm\nf-icm-wcsgetdefaultcolorprofile.md">WcsGetDefaultColorProfile</a>

<a href="..\icm\ne-icm-wcs_profile_management_scope.md">WCS_PROFILE_MANAGEMENT_SCOPE</a>

<a href="..\icm\ne-icm-colorprofilesubtype.md">COLORPROFILESUBTYPE</a>

<a href="..\icm\ne-icm-colorprofiletype.md">COLORPROFILETYPE</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [print\print]:%20WcsGetDefaultColorProfileSize function%20 RELEASE:%20(1/18/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

