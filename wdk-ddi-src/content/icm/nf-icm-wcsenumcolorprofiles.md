---
UID: NF:icm.WcsEnumColorProfiles
title: WcsEnumColorProfiles function
author: windows-driver-content
description: The WcsEnumColorProfiles function enumerates all color profiles that satisfy the enumeration criteria in the specified profile management scope.
old-location: print\wcsenumcolorprofiles.htm
old-project: print
ms.assetid: 54cb2647-5685-4856-9b70-97733758aac2
ms.author: windowsdriverdev
ms.date: 4/20/2018
ms.keywords: WcsEnumColorProfiles, WcsEnumColorProfiles function [Print Devices], colorfnc_06eda9f3-b5d8-4d57-b9e4-1a939bc0ea70.xml, icm/WcsEnumColorProfiles, print.wcsenumcolorprofiles
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
-	WcsEnumColorProfiles
product: Windows
targetos: Windows
req.typenames: 
---

# WcsEnumColorProfiles function


## -description


The <code>WcsEnumColorProfiles</code> function enumerates all color profiles that satisfy the enumeration criteria in the specified profile management scope.


## -parameters




### -param scope

TBD


### -param pEnumRecord [in]

A pointer to a structure that specifies the enumeration criteria.


### -param pBuffer [out]

A pointer to a buffer in which the profile names are to be enumerated. A MULTI_SZ string that consists of profile names that satisfy the criteria specified in <i>*pEnumRecord</i> will be placed in this buffer.


### -param dwSize [in]

A variable that contains the size, in bytes, of the buffer pointed to by <i>pBuffer</i>. See Remarks.


### -param pnProfiles [out, optional]

An optional pointer to a variable that receives the number of profile names actually copied to the buffer pointed to by <i>pBuffer</i>. Can be <b>NULL</b> if this information is not needed.


#### - profileManagementScope [in]

A <a href="https://msdn.microsoft.com/library/windows/hardware/ff563752">WCS_PROFILE_MANAGEMENT_SCOPE</a> value that specifies the scope of this profile management operation.


## -remarks



Use the <a href="https://msdn.microsoft.com/library/windows/hardware/ff563722">WcsEnumColorProfilesSize</a> function to obtain the value for the <i>dwSize</i> parameter, which is the size, in bytes, of the buffer pointed to by the <i>pBuffer</i> parameter.

If the <i>profileManagementScope</i> parameter is WCS_PROFILE_MANAGEMENT_SCOPE_SYSTEM_WIDE, only system-wide associations of profiles to the device are considered. If <i>profileManagementScope</i> is WCS_PROFILE_MANAGEMENT_SCOPE_CURRENT_USER, only per-user associations for the current user are considered. If either <a href="https://msdn.microsoft.com/library/windows/hardware/ff563741">WcsSetUsePerUserProfiles</a> has never been called for this user, or <b>WcsSetUsePerUserProfiles</b> was most recently called for this user with its <i>usePerUserProfiles</i> parameter set to <b>FALSE</b>, then <code>WCSEnumColorProfiles</code> returns an empty list.

If WCS_PROFILE_MANAGEMENT_SCOPE_CURRENT_USER, the current user setting, is present, it overrides the system-wide default for the <i>profileManagementScope</i> parameter.

This function is executable in Least-Privileged User Account (LUA) context.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff563752">WCS_PROFILE_MANAGEMENT_SCOPE</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff563722">WcsEnumColorProfilesSize</a>
 

 

