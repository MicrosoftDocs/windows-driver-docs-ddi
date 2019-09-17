---
UID: NC:d3dumddi.PFND3DDDI_TRIMRESIDENCYSET
title: PFND3DDDI_TRIMRESIDENCYSET (d3dumddi.h)
description: pfnTrimResidencySet is used to trim the residency list for a given device. User mode drivers are required to implement this callback in order to participate in the new memory residency model.
old-location: display\pfntrimresidencyset.htm
tech.root: display
ms.assetid: 192F419C-F38F-4B42-8111-86D58D6781DA
ms.date: 05/10/2018
ms.keywords: PFND3DDDI_TRIMRESIDENCYSET, PFND3DDDI_TRIMRESIDENCYSET callback, d3dukmdt/pfnTrimResidencySet, display.pfntrimresidencyset, pfnTrimResidencySet, pfnTrimResidencySet callback function [Display Devices]
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
targetos: Windows
req.typenames: 
f1_keywords:
 - "d3dumddi/pfnTrimResidencySet"
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - d3dukmdt.h
api_name:
 - pfnTrimResidencySet
product:
 - Windows
---

# PFND3DDDI_TRIMRESIDENCYSET callback function

## -description

<b>pfnTrimResidencySet</b> is used to trim the residency list for a given device. User mode drivers are required to implement this callback in order to participate in the new memory residency model.

## -parameters

### -param hDevice

A handle to the display device.

### -param Arg2

*pData* [in]

A pointer to a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3dumddi/ns-d3dumddi-d3dddiarg_trimresidencyset">D3DDDIARG_TRIMRESIDENCYSET</a> structure that provides the details of the requested operation.

## -returns

If this callback function succeeds, it returns <b xmlns:loc="http://microsoft.com/wdcml/l10n">S_OK</b>. Otherwise, it returns an <b xmlns:loc="http://microsoft.com/wdcml/l10n">HRESULT</b> error code.

## -see-also

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3dumddi/ns-d3dumddi-d3dddiarg_trimresidencyset">D3DDDIARG_TRIMRESIDENCYSET</a>

