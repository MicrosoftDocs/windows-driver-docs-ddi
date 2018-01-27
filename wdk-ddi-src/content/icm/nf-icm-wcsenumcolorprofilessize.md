---
UID: NF:icm.WcsEnumColorProfilesSize
title: WcsEnumColorProfilesSize function
author: windows-driver-content
description: The WcsEnumColorProfilesSize function returns the size, in bytes, of the buffer required by the WcsEnumColorProfiles function to enumerate color profiles.
old-location: print\wcsenumcolorprofilessize.htm
old-project: print
ms.assetid: bcd9c781-aa44-4e90-9290-c9f13b192cae
ms.author: windowsdriverdev
ms.date: 1/18/2018
ms.keywords: icm/WcsEnumColorProfilesSize, colorfnc_dec9b73e-e492-4fed-841f-bbc0c8a5f225.xml, WcsEnumColorProfilesSize, WcsEnumColorProfilesSize function [Print Devices], print.wcsenumcolorprofilessize
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
-	WcsEnumColorProfilesSize
product: Windows
targetos: Windows
req.typenames: WCS_PROFILE_MANAGEMENT_SCOPE
---

# WcsEnumColorProfilesSize function


## -description


The <code>WcsEnumColorProfilesSize</code> function returns the size, in bytes, of the buffer required by the <a href="..\icm\nf-icm-wcsenumcolorprofiles.md">WcsEnumColorProfiles</a> function to enumerate color profiles.


## -syntax


````
BOOL WcsEnumColorProfilesSize(
  _In_  WCS_PROFILE_MANAGEMENT_SCOPE profileManagementScope,
  _In_  PENUMTYPEW                   pEnumRecord,
  _Out_ PDWORD                       pdwSize
);
````


## -parameters




### -param scope

TBD


### -param pEnumRecord [in]

A pointer to a structure that specifies the enumeration criteria.


### -param pdwSize [out]

A pointer to a variable that receives the size of the buffer that is required to receive all enumerated profile names. This value is used by the <i>dwSize</i> parameter of the <a href="..\icm\nf-icm-wcsenumcolorprofiles.md">WcsEnumColorProfiles</a> function.


#### - profileManagementScope [in]

A <a href="..\icm\ne-icm-wcs_profile_management_scope.md">WCS_PROFILE_MANAGEMENT_SCOPE</a> value that specifies the scope of the profile management operation performed by this function.


## -remarks


This function is executable in Least-Privileged User Account (LUA) context.



## -see-also

<a href="..\icm\nf-icm-wcsenumcolorprofiles.md">WcsEnumColorProfiles</a>

<a href="..\icm\ne-icm-wcs_profile_management_scope.md">WCS_PROFILE_MANAGEMENT_SCOPE</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [print\print]:%20WcsEnumColorProfilesSize function%20 RELEASE:%20(1/18/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

