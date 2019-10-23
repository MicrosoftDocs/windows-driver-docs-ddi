---
UID: NC:d3dumddi.PFND3DDDI_SETINDICESUM
title: PFND3DDDI_SETINDICESUM (d3dumddi.h)
description: The SetIndicesUM function sets the current index buffer to the given user memory buffer.
old-location: display\setindicesum.htm
tech.root: display
ms.assetid: 9ca38004-8953-4416-8552-c76813192561
ms.date: 05/10/2018
ms.keywords: PFND3DDDI_SETINDICESUM, PFND3DDDI_SETINDICESUM callback, SetIndicesUM, SetIndicesUM callback function [Display Devices], UserModeDisplayDriver_Functions_f692c944-6130-46e3-8e63-f3dbeb051782.xml, d3dumddi/SetIndicesUM, display.setindicesum
ms.topic: callback
req.header: d3dumddi.h
req.include-header: D3dumddi.h
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
targetos: Windows
req.typenames: 
f1_keywords:
 - "d3dumddi/SetIndicesUM"
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - d3dumddi.h
api_name:
 - SetIndicesUM
product:
 - Windows
---

# PFND3DDDI_SETINDICESUM callback function

## -description

The <i>SetIndicesUM</i> function sets the current index buffer to the given user memory buffer.

## -parameters

### -param hDevice

A handle to the display device (graphics context).

### -param Arg2

*IndexSize* [in]

The size, in bytes, of the indices that are contained in the index buffer. The value of this parameter is 2 if the indices are 16-bit quantities or 4 if the indices are 32-bit quantities.

### -param Arg3

*pUMBuffer* [in]

A pointer to the user-memory buffer that supplies the indices for the index buffer.

## -returns

<i>SetIndicesUM</i> returns S_OK or an appropriate error result if the index buffer is not successfully set to the given user memory buffer.

## -see-also

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dumddi/ns-d3dumddi-_d3dddi_devicefuncs">D3DDDI_DEVICEFUNCS</a>

