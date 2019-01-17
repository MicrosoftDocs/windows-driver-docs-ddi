---
UID: NF:icm.WcsSetUsePerUserProfiles
title: WcsSetUsePerUserProfiles function
description: The WcsSetUsePerUserProfiles function allows the user to specify whether or not to use a per-user profile association list for the specified device.
old-location: print\wcssetuseperuserprofiles.htm
tech.root: print
ms.assetid: e14f944f-67fe-4eb8-85b2-9ba262e2e549
ms.date: 04/20/2018
ms.keywords: WcsSetUsePerUserProfiles, WcsSetUsePerUserProfiles function [Print Devices], colorfnc_e56a2693-0dec-4b5a-96be-2934ec336d2b.xml, icm/WcsSetUsePerUserProfiles, print.wcssetuseperuserprofiles
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
-	WcsSetUsePerUserProfiles
product:
- Windows
targetos: Windows
req.typenames: 
---

# WcsSetUsePerUserProfiles function


## -description


The <code>WcsSetUsePerUserProfiles</code> function allows the user to specify whether or not to use a per-user profile association list for the specified device.


## -parameters




### -param pDeviceName [in]

A pointer to a string that contains the friendly name of the device.


### -param dwDeviceClass [in]

A flag value that specifies the class of the device. This parameter must take one of the following values:





#### CLASS_MONITOR

Specifies a display device.



#### CLASS_PRINTER

Specifies a printer.



#### CLASS_SCANNER

Specifies an image capture device.


### -param usePerUserProfiles [in]

A Boolean value that is <b>TRUE</b> if the user wants to use a per-user profile association list for the specified device; otherwise <b>FALSE</b>.


## -remarks



This function will fail if the device pointed to by <i>pDeviceName</i> is not of the class specified by <i>dwDeviceClass</i>.

This function is executable in Least-Privileged User Account (LUA) context.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff563734">WcsGetUsePerUserProfiles</a>
 

 

