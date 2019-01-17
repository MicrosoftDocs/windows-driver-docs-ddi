---
UID: NC:d3dumddi.PFND3DDDI_CHECKCOUNTERINFO
title: PFND3DDDI_CHECKCOUNTERINFO
description: Called by the Microsoft Direct3D runtime to determine global information that's related to manipulating counters. Must be implemented by Windows Display Driver Model (WDDM) 1.3 and later user-mode display drivers.
old-location: display\pfncheckcounterinfo.htm
tech.root: display
ms.assetid: 98B8EE79-18D2-4C57-964B-74DB550C1330
ms.date: 05/10/2018
ms.keywords: PFND3DDDI_CHECKCOUNTERINFO, PFND3DDDI_CHECKCOUNTERINFO callback, d3dumddi/pfnCheckCounterInfo, display.pfncheckcounterinfo, pfnCheckCounterInfo, pfnCheckCounterInfo callback function [Display Devices]
ms.topic: callback
req.header: d3dumddi.h
req.include-header: D3d10umddi.h
req.target-type: Desktop
req.target-min-winverclnt: Windows 8.1
req.target-min-winversvr: Windows Server 2012 R2
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: 
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	UserDefined
api_location:
-	D3dumddi.h
api_name:
-	pfnCheckCounterInfo
product:
- Windows
targetos: Windows
req.typenames: 
---

# PFND3DDDI_CHECKCOUNTERINFO callback function


## -description


Called by the Microsoft Direct3D runtime to determine global information that's related to manipulating counters. Must be implemented by Windows Display Driver Model (WDDM) 1.3 and later user-mode display drivers.


## -parameters




### -param hDevice [in]

A handle to the display device (graphics context).




### -param *

*pCounterInfo* [out]

A pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/dn449152">D3DDDIARG_COUNTER_INFO</a> structure that the driver populates with global information that's related to manipulating counters.


## -returns



None

The driver can use the <a href="https://msdn.microsoft.com/968b04a7-8869-410c-a6fc-83d57726858f">pfnSetErrorCb</a> callback function to set an error code. For more information about setting error codes, see the following Remarks section.




## -remarks



This function should behave similarly to the <a href="https://msdn.microsoft.com/5dcea47c-aac7-46e5-afd5-c3390c3c5286">CheckCounterInfo</a> function that supports Microsoft Direct3D 10 and later.

If the user-mode display driver does not support any of the concepts that are represented in the members of the <a href="https://msdn.microsoft.com/library/windows/hardware/dn449152">D3DDDIARG_COUNTER_INFO</a> structure, it can populate the members of <b>D3DDDIARG_COUNTER_INFO</b> with zeros.

The driver's <i>pfnCheckCounterInfo</i> function cannot call the <a href="https://msdn.microsoft.com/968b04a7-8869-410c-a6fc-83d57726858f">pfnSetErrorCb</a> callback function to set the <b>D3DDDIERR_DEVICEREMOVED</b> error code because <i>pfnCheckCounterInfo</i> is a capability-check type of function. The driver must ensure that it has enough information after device creation to respond to a call to <i>pfnCheckCounterInfo</i>, even in the presence of <b>D3DDDIERR_DEVICEREMOVED</b>. <i>pfnCheckCounterInfo</i> should not encounter any errors. However, <i>pfnCheckCounterInfo</i> might call <b>pfnSetErrorCb</b> for critical errors.




## -see-also




<a href="https://msdn.microsoft.com/5dcea47c-aac7-46e5-afd5-c3390c3c5286">CheckCounterInfo</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/dn449152">D3DDDIARG_COUNTER_INFO</a>



<a href="https://msdn.microsoft.com/968b04a7-8869-410c-a6fc-83d57726858f">pfnSetErrorCb</a>
 

 

