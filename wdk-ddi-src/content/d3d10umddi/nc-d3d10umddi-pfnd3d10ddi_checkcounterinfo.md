---
UID: NC:d3d10umddi.PFND3D10DDI_CHECKCOUNTERINFO
title: PFND3D10DDI_CHECKCOUNTERINFO
author: windows-driver-content
description: The CheckCounterInfo function determines global information that is related to manipulating counters.
old-location: display\checkcounterinfo.htm
ms.assetid: 5dcea47c-aac7-46e5-afd5-c3390c3c5286
ms.author: windowsdriverdev
ms.date: 5/10/2018
ms.keywords: CheckCounterInfo, CheckCounterInfo callback function [Display Devices], PFND3D10DDI_CHECKCOUNTERINFO, PFND3D10DDI_CHECKCOUNTERINFO callback, UserModeDisplayDriverDx10_Functions_7057ce5a-5677-4174-9bee-81c8ab5b18f7.xml, d3d10umddi/CheckCounterInfo, display.checkcounterinfo
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: d3d10umddi.h
req.include-header: D3d10umddi.h
req.target-type: Desktop
req.target-min-winverclnt: Available in Windows Vista and later versions of the Windows operating systems.
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
req.lib: 
req.dll: 
req.irql: 
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	UserDefined
api_location:
-	d3d10umddi.h
api_name:
-	CheckCounterInfo
product:
- Windows
targetos: Windows
tech.root: display
req.typenames: 
---

# PFND3D10DDI_CHECKCOUNTERINFO callback function


## -description


The <b>CheckCounterInfo</b> function determines global information that is related to manipulating counters.


## -parameters




### -param Arg1


### -param *








#### - hDevice [in]

 A handle to the display device (graphics context).


#### - pCounterInfo [out]

A pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/ff541827">D3D10DDI_COUNTER_INFO</a> structure that the driver populates with global information that is related to manipulating counters. 


## -returns



None

The driver can use the <a href="https://msdn.microsoft.com/968b04a7-8869-410c-a6fc-83d57726858f">pfnSetErrorCb</a> callback function to set an error code. For more information about setting error codes, see the following Remarks section.




## -remarks



If the user-mode display driver does not support any of the concepts that are represented in the members of the <a href="https://msdn.microsoft.com/library/windows/hardware/ff541827">D3D10DDI_COUNTER_INFO</a> structure, it can populate the members of D3D10DDI_COUNTER_INFO with zeros. 

The driver's <b>CheckCounterInfo</b> function cannot call the <a href="https://msdn.microsoft.com/968b04a7-8869-410c-a6fc-83d57726858f">pfnSetErrorCb</a> callback function to set the D3DDDIERR_DEVICEREMOVED error code because <b>CheckCounterInfo</b> is a capability-check type of function. The driver must ensure that it has enough information after device creation to respond to a call to <b>CheckCounterInfo</b>, even in the presence of D3DDDIERR_DEVICEREMOVED. <b>CheckCounterInfo</b> should not encounter any errors. However, <b>CheckCounterInfo</b> might call <b>pfnSetErrorCb</b> for critical errors. 




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff541827">D3D10DDI_COUNTER_INFO</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff541833">D3D10DDI_DEVICEFUNCS</a>



<a href="https://msdn.microsoft.com/968b04a7-8869-410c-a6fc-83d57726858f">pfnSetErrorCb</a>
 

 

