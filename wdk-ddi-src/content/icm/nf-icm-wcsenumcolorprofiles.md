---
UID: NF:icm.WcsEnumColorProfiles
title: WcsEnumColorProfiles function (icm.h)
description: The WcsEnumColorProfiles function enumerates all color profiles that satisfy the enumeration criteria in the specified profile management scope.
old-location: print\wcsenumcolorprofiles.htm
tech.root: print
ms.assetid: 54cb2647-5685-4856-9b70-97733758aac2
ms.date: 08/14/2020
keywords: ["WcsEnumColorProfiles function"]
ms.keywords: WcsEnumColorProfiles, WcsEnumColorProfiles function [Print Devices], colorfnc_06eda9f3-b5d8-4d57-b9e4-1a939bc0ea70.xml, icm/WcsEnumColorProfiles, print.wcsenumcolorprofiles
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
-   WcsEnumColorProfiles
targetos: Windows
req.typenames: 
---

# WcsEnumColorProfiles function

## -description

The **WcsEnumColorProfiles** function enumerates all color profiles that satisfy the enumeration criteria in the specified profile management scope.

## -parameters

### -param scope

### -param pEnumRecord [in]

A pointer to a structure that specifies the enumeration criteria.

### -param pBuffer [out]

A pointer to a buffer in which the profile names are to be enumerated. A MULTI_SZ string that consists of profile names that satisfy the criteria specified in **pEnumRecord* will be placed in this buffer.

### -param dwSize [in]

A variable that contains the size, in bytes, of the buffer pointed to by *pBuffer*. See Remarks.

### -param pnProfiles [out, optional]

An optional pointer to a variable that receives the number of profile names actually copied to the buffer pointed to by *pBuffer*. Can be **NULL** if this information is not needed.

#### - profileManagementScope [in]

A [WCS_PROFILE_MANAGEMENT_SCOPE](https://docs.microsoft.com/previous-versions/ff563752(v=vs.85)) value that specifies the scope of this profile management operation.

## -remarks

Use the [WcsEnumColorProfilesSize](https://docs.microsoft.com/previous-versions/ff563722(v=vs.85)) function to obtain the value for the *dwSize* parameter, which is the size, in bytes, of the buffer pointed to by the *pBuffer* parameter.

If the *profileManagementScope* parameter is WCS_PROFILE_MANAGEMENT_SCOPE_SYSTEM_WIDE, only system-wide associations of profiles to the device are considered. If *profileManagementScope* is WCS_PROFILE_MANAGEMENT_SCOPE_CURRENT_USER, only per-user associations for the current user are considered. If either [WcsSetUsePerUserProfiles](https://docs.microsoft.com/previous-versions/ff563741(v=vs.85)) has never been called for this user, or **WcsSetUsePerUserProfiles** was most recently called for this user with its *usePerUserProfiles* parameter set to **FALSE**, then **WCSEnumColorProfiles** returns an empty list.

If WCS_PROFILE_MANAGEMENT_SCOPE_CURRENT_USER, the current user setting, is present, it overrides the system-wide default for the *profileManagementScope* parameter.

This function is executable in Least-Privileged User Account (LUA) context.

## -see-also

[WCS_PROFILE_MANAGEMENT_SCOPE](https://docs.microsoft.com/previous-versions/ff563752(v=vs.85))

[WcsEnumColorProfilesSize](https://docs.microsoft.com/previous-versions/ff563722(v=vs.85))
