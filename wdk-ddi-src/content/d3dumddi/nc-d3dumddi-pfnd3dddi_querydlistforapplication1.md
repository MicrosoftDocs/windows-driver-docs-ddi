---
UID: NC:d3dumddi.PFND3DDDI_QUERYDLISTFORAPPLICATION1
title: PFND3DDDI_QUERYDLISTFORAPPLICATION1
author: windows-driver-content
description: Called during Microsoft Direct3D initialization on a hybrid system to determine which GPU an application should run on. A dList is a list of applications that need cross-adapter shared surfaces for high-performance rendering on the discrete GPU.
old-location: display\querydlistforapplication1.htm
old-project: display
ms.assetid: 4F27E884-D21C-483D-9E53-02D405D02F10
ms.author: windowsdriverdev
ms.date: 4/16/2018
ms.keywords: PFND3DDDI_QUERYDLISTFORAPPLICATION1, PFND3DDDI_QUERYDLISTFORAPPLICATION1 callback, QueryDListForApplication, QueryDListForApplication callback function [Display Devices], d3dumddi/QueryDListForApplication, display.querydlistforapplication1
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: d3dumddi.h
req.include-header: D3d10umddi.h
req.target-type: Desktop
req.target-min-winverclnt: Windows 8.1,WDDM 1.3 and later
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
-	QueryDListForApplication
product:
- Windows
targetos: Windows
req.typenames: 
---

# PFND3DDDI_QUERYDLISTFORAPPLICATION1 callback function


## -description


Called during Microsoft Direct3D initialization on a <a href="https://msdn.microsoft.com/ECBB0AA7-50C2-41C8-9DC6-6EEFC5CEEB15">hybrid system</a> to determine which GPU an application should run on. A <i>dList</i> is a list of applications that need cross-adapter shared surfaces for high-performance rendering on the discrete GPU.


## -parameters




### -param *


### -param Arg1


### -param Arg2








#### - hAdapter [in]

A handle to the graphics adapter object.


#### - pDefaultToDiscrete [out]

If <b>TRUE</b>, the application should be run on the discrete GPU. Otherwise, the application should run on the integrated GPU.


#### - pfnEscapeCB [in]

A function pointer to a <a href="https://msdn.microsoft.com/66c0347f-2cf3-42fc-8641-47c731e958c9">pfnEscapeCb</a> callback function that shares info with the display miniport driver.


## -returns



Returns <b>S_OK</b>, or an appropriate error result if the operation is not successful.




## -remarks



For more information on how to call this function and set up the DLL that exports it, see <a href="https://msdn.microsoft.com/8AABE677-2C2D-4CFD-AF22-06D65524A158">Hybrid system DDI</a>.

For more general information on hybrid systems, see <a href="https://msdn.microsoft.com/ECBB0AA7-50C2-41C8-9DC6-6EEFC5CEEB15">Using cross-adapter resources in a hybrid system</a>.




## -see-also




<a href="https://msdn.microsoft.com/66c0347f-2cf3-42fc-8641-47c731e958c9">pfnEscapeCb</a>
 

 

