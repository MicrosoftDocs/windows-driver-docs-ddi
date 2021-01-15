---
UID: NC:d3dumddi.PFND3DDDI_CLOSEADAPTER
title: PFND3DDDI_CLOSEADAPTER (d3dumddi.h)
description: The CloseAdapter function releases resources for a graphics adapter object.
old-location: display\closeadapter.htm
tech.root: display
ms.date: 05/10/2018
keywords: ["PFND3DDDI_CLOSEADAPTER callback function"]
ms.keywords: CloseAdapter, CloseAdapter callback function [Display Devices], PFND3DDDI_CLOSEADAPTER, PFND3DDDI_CLOSEADAPTER callback, UserModeDisplayDriver_Functions_ccc1793f-15b1-480f-8835-38326b749308.xml, d3dumddi/CloseAdapter, display.closeadapter
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
 - PFND3DDDI_CLOSEADAPTER
 - d3dumddi/PFND3DDDI_CLOSEADAPTER
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - d3dumddi.h
api_name:
 - PFND3DDDI_CLOSEADAPTER
product:
 - Windows
---

# PFND3DDDI_CLOSEADAPTER callback function


## -description

The <b>CloseAdapter</b> function releases resources for a graphics adapter object.

## -parameters

### -param hAdapter

A handle to the graphics adapter object that was created with the <a href="/windows-hardware/drivers/ddi/d3dumddi/nc-d3dumddi-pfnd3dddi_openadapter">OpenAdapter</a> function.

## -returns

<b>CloseAdapter</b> returns S_OK if the operation succeeds. Otherwise, this function returns an appropriate error result.

## -remarks

The user-mode display driver's <b>CloseAdapter</b> function should free all of the resources that it allocated for the graphics adapter object.

Before <b>CloseAdapter</b> closes the graphics adapter object, all of the display devices that were created by using the graphics adapter object in calls to the user-mode display driver's <a href="/windows-hardware/drivers/ddi/d3dumddi/nc-d3dumddi-pfnd3dddi_createdevice">CreateDevice</a> function must be destroyed in calls to the driver's <a href="/windows-hardware/drivers/ddi/d3dumddi/nc-d3dumddi-pfnd3dddi_destroydevice">DestroyDevice</a> function.

## -see-also

<a href="/windows-hardware/drivers/ddi/d3dumddi/nc-d3dumddi-pfnd3dddi_createdevice">CreateDevice</a>



<a href="/windows-hardware/drivers/ddi/d3dumddi/ns-d3dumddi-_d3dddi_adapterfuncs">D3DDDI_ADAPTERFUNCS</a>



<a href="/windows-hardware/drivers/ddi/d3dumddi/nc-d3dumddi-pfnd3dddi_destroydevice">DestroyDevice</a>



<a href="/windows-hardware/drivers/ddi/d3dumddi/nc-d3dumddi-pfnd3dddi_openadapter">OpenAdapter</a>

