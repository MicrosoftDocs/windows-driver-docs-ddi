---
UID: NC:d3dumddi.PFND3DDDI_TRIMRESIDENCYSET
title: PFND3DDDI_TRIMRESIDENCYSET
author: windows-driver-content
description: pfnTrimResidencySet is used to trim the residency list for a given device. User mode drivers are required to implement this callback in order to participate in the new memory residency model.
old-location: display\pfntrimresidencyset.htm
tech.root: display
ms.assetid: 192F419C-F38F-4B42-8111-86D58D6781DA
ms.author: windowsdriverdev
ms.date: 5/10/2018
ms.keywords: PFND3DDDI_TRIMRESIDENCYSET, PFND3DDDI_TRIMRESIDENCYSET callback, d3dukmdt/pfnTrimResidencySet, display.pfntrimresidencyset, pfnTrimResidencySet, pfnTrimResidencySet callback function [Display Devices]
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: d3dumddi.h
req.include-header: D3dumddi.h, D3dkmddi.h
req.target-type: Desktop
req.target-min-winverclnt: Windows 10
req.target-min-winversvr: Windows Server 2016
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
-	d3dukmdt.h
api_name:
-	pfnTrimResidencySet
product:
- Windows
targetos: Windows
req.typenames: 
---

# PFND3DDDI_TRIMRESIDENCYSET callback function


## -description


<b>pfnTrimResidencySet</b> is used to trim the residency list for a given device. User mode drivers are required to implement this callback in order to participate in the new memory residency model.


## -parameters




### -param hDevice [in]

A handle to the display device.


### -param *








#### - pData [in]

A pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/dn906759">D3DDDIARG_TRIMRESIDENCYSET</a> structure that provides the details of the requested operation.




## -returns



If this callback function succeeds, it returns <b xmlns:loc="http://microsoft.com/wdcml/l10n">S_OK</b>. Otherwise, it returns an <b xmlns:loc="http://microsoft.com/wdcml/l10n">HRESULT</b> error code.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/dn906759">D3DDDIARG_TRIMRESIDENCYSET</a>
 

 

