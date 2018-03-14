---
UID: NC:d3dumddi.PFND3DDDI_CHECKCOUNTERINFO
title: PFND3DDDI_CHECKCOUNTERINFO
author: windows-driver-content
description: Called by the Microsoft Direct3D runtime to determine global information that's related to manipulating counters. Must be implemented by Windows Display Driver Model (WDDM) 1.3 and later user-mode display drivers.
old-location: display\pfncheckcounterinfo.htm
old-project: display
ms.assetid: 98B8EE79-18D2-4C57-964B-74DB550C1330
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: PFND3DDDI_CHECKCOUNTERINFO, d3dumddi/pfnCheckCounterInfo, display.pfncheckcounterinfo, pfnCheckCounterInfo, pfnCheckCounterInfo callback function [Display Devices]
ms.prod: windows-hardware
ms.technology: windows-devices
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
product: Windows
targetos: Windows
req.typenames: DXGK_PTE
---

# PFND3DDDI_CHECKCOUNTERINFO callback


## -description


Called by the Microsoft Direct3D runtime to determine global information that's related to manipulating counters. Must be implemented by Windows Display Driver Model (WDDM) 1.3 and later user-mode display drivers.


## -prototype


````
PFND3DDDI_CHECKCOUNTERINFO pfnCheckCounterInfo;

VOID APIENTRY* pfnCheckCounterInfo(
  _In_  HANDLE                 hDevice,
  _Out_ D3DDDIARG_COUNTER_INFO *pCounterInfo
)
{ ... }
````


## -parameters




### -param hDevice [in]

A handle to the display device (graphics context).




### -param *








#### - pCounterInfo [out]

A pointer to a <a href="..\d3dumddi\ns-d3dumddi-d3dddiarg_counter_info.md">D3DDDIARG_COUNTER_INFO</a> structure that the driver populates with global information that's related to manipulating counters.


## -returns



None

The driver can use the <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi_seterror_cb.md">pfnSetErrorCb</a> callback function to set an error code. For more information about setting error codes, see the following Remarks section.




## -remarks



This function should behave similarly to the <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi_checkcounterinfo.md">CheckCounterInfo</a> function that supports Microsoft Direct3D 10 and later.

If the user-mode display driver does not support any of the concepts that are represented in the members of the <a href="..\d3dumddi\ns-d3dumddi-d3dddiarg_counter_info.md">D3DDDIARG_COUNTER_INFO</a> structure, it can populate the members of <b>D3DDDIARG_COUNTER_INFO</b> with zeros.

The driver's <i>pfnCheckCounterInfo</i> function cannot call the <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi_seterror_cb.md">pfnSetErrorCb</a> callback function to set the <b>D3DDDIERR_DEVICEREMOVED</b> error code because <i>pfnCheckCounterInfo</i> is a capability-check type of function. The driver must ensure that it has enough information after device creation to respond to a call to <i>pfnCheckCounterInfo</i>, even in the presence of <b>D3DDDIERR_DEVICEREMOVED</b>. <i>pfnCheckCounterInfo</i> should not encounter any errors. However, <i>pfnCheckCounterInfo</i> might call <b>pfnSetErrorCb</b> for critical errors.




## -see-also

<a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi_seterror_cb.md">pfnSetErrorCb</a>



<a href="..\d3dumddi\ns-d3dumddi-d3dddiarg_counter_info.md">D3DDDIARG_COUNTER_INFO</a>



<a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi_checkcounterinfo.md">CheckCounterInfo</a>



 

 


