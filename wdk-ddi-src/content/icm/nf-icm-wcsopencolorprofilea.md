---
UID: NF:icm.WcsOpenColorProfileA
title: WcsOpenColorProfileA function
author: windows-driver-content
description: The WcsOpenColorProfile function creates a handle to a specified color profile.
old-location: print\wcsopencolorprofile.htm
tech.root: print
ms.assetid: ecc573e6-c83c-4cf2-9dad-c3c75d9578eb
ms.date: 4/20/2018
ms.keywords: WcsOpenColorProfile, WcsOpenColorProfile function [Print Devices], WcsOpenColorProfileA, WcsOpenColorProfileW, colorfnc_d9a9eca5-5559-4579-a892-c75499627912.xml, icm/WcsOpenColorProfile, print.wcsopencolorprofile
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
req.dll:
req.irql:
topic_type:
-   APIRef
-   kbSyntax
api_type:
-   LibDef
api_location:
-   Mscms.lib
-   Mscms.dll
api_name:
-   WcsOpenColorProfile
product:
- Windows
targetos: Windows
req.typenames: 
---

# WcsOpenColorProfileA function


## -description


The <code>WcsOpenColorProfile</code> function creates a handle to a specified color profile.


## -parameters




### -param pCDMPProfile




### -param pCAMPProfile [in, optional]

A pointer to a profile structure that specifies a  WCS color appearance model profile (CAMP). The <i>pCAMPProfile</i> pointer can be freed as soon as the handle is created. If <b>NULL</b>, the standard default CAMP is used, and the current user setting, WCS_PROFILE_MANAGEMENT_SCOPE_CURRENT_USER, is used while querying the default CAMP.


### -param pGMMPProfile [in, optional]

A pointer to a profile structure that specifies a WCS gamut map model profile (GMMP). The <i>pGMMPProfile</i> pointer can be freed as soon as the handle is created. If <b>NULL</b>, the default GMMP for the default rendering intent is used, and the current user setting, WCS_PROFILE_MANAGEMENT_SCOPE_CURRENT_USER, is used while querying the default GMMP. For a description of rendering intents, see <a href="http://go.microsoft.com/fwlink/p/?linkid=52269">Rendering Intents</a> in the Microsoft Windows SDK documentation.


### -param dwDesireAccess




### -param dwShareMode [in]

A flag value that specifies actions to take while opening a color profile if it is contained in a file. This parameter must take one of the following values, which are defined in winnt.h:





#### FILE_SHARE_READ

Specifies that other open operations can be performed on the profile for read access.



#### FILE_SHARE_WRITE

Specifies that other open operations can be performed on the profile for write access. This flag value is ignored when a WCS profile is opened.


### -param dwCreationMode [in]

A flag value that specifies actions to take while opening a color profile if it is contained in a file. This parameter must take one of the following values, which are defined in winbase.h:





#### CREATE_NEW

Specifies that a new profile is to be created. The function fails if the profile already exists.



#### CREATE_ALWAYS

Specifies that a new profile is to be created. If a profile already exists, it is overwritten.



#### OPEN_EXISTING

Specifies that the profile is to be opened. The function fails if the profile does not exist.



#### OPEN_ALWAYS

Specifies that the profile is to be opened if an International Color Consortium (ICC) file exists. If an ICC profile does not exist, WCS creates a new ICC profile. The function will fail for WCS profiles if this flag is set and a WCS profile does not exist.



#### TRUNCATE_EXISTING

Specifies that the profile is to be opened and truncated to zero bytes. The function fails if the profile does not exist.


### -param dwFlags [in]

A flag value that specifies whether to use the embedded WCS profile. This parameter has no effect unless <i>pCDMProfile</i> specifies an ICC profile that contains an embedded WCS profile.This parameter takes one of the following values:

<table>
<tr>
<td>0</td>
<td>Specifies that the embedded WCS profile will be used and the ICC profile specfied by pCDMPProfile will be ignored.</td>
</tr>
<tr>
<td>DONT_USE_EMBEDDED_WCS_PROFILES</td>
<td>Specifies that the ICC profile specified by pCDMPProfile will be used and the embedded WCS profile will be ignored.</td>
</tr>
</table>



#### - dwDesiredAccess [in]

A flag value that specifies how to access the given color profile. This parameter must take one of the following values:





#### PROFILE_READ

Specifies that the color profile will be opened for read-only access.



#### PROFILE_READWRITE

Specifies that the color profile will be opened for both read and write access.  This flag value is ignored when a WCS profile is opened.


#### - pDMPProfile [in]

A pointer to a profile structure that specifies a WCS device model profile (DMP). The <i>pDMPProfile</i> pointer can be freed as soon as the handle is created.


## -remarks



The handle returned by this function can be used in other color profile management functions.

The compiler setting also determinDeclared in Icm.hes the function version. If Unicode is defined, the function call resolves to <b>WcsOpenColorProfileW</b>. Otherwise, the function call resolves to <b>WcsOpenColorProfileA</b> because ANSI strings are being used.

If the color profile data is not specified using a file name, the <i>dwShareMode</i> and <i>dwCreationMode</i> values are ignored.

This function initially attempts to open the profile as an ICC profile. Even if a WCS profile is provided, the PROFILE_READWRITE and FILE_SHARE_WRITE flags are not ignored. However, if the provided profile is not an ICC profile (and a new ICC profile is not being created), these flag values are ignored.

The <i>dwCreationMode</i> flags CREATE_NEW, CREATE_ALWAYS, and TRUNCATE_EXISTING will always return an empty handle to the ICC color profile.

Once the handle to the color profile is created, any information used to create that handle can be deleted.

Use the <a href="http://go.microsoft.com/fwlink/p/?linkid=52323">CloseColorProfile </a> function to close an object handle returned by <code>WcsOpenColorProfile</code>.




## -see-also




<a href="http://go.microsoft.com/fwlink/p/?linkid=52323">CloseColorProfile</a>




