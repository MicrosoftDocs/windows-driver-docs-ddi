---
UID: NC:d3d10umddi.PFND3D10DDI_SETINPUTLAYOUT
title: PFND3D10DDI_SETINPUTLAYOUT (d3d10umddi.h)
description: The IaSetInputLayout function sets an input layout for the input assembler.
old-location: display\iasetinputlayout.htm
ms.assetid: 905e4e7f-5bc5-487f-8d82-4ebc2db66135
ms.date: 05/10/2018
ms.keywords: IaSetInputLayout, IaSetInputLayout callback function [Display Devices], PFND3D10DDI_SETINPUTLAYOUT, PFND3D10DDI_SETINPUTLAYOUT callback, UserModeDisplayDriverDx10_Functions_fbd365d3-26a5-49a8-b89c-c094d8e873d9.xml, d3d10umddi/IaSetInputLayout, display.iasetinputlayout
f1_keywords:
 - "d3d10umddi/IaSetInputLayout"
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
- APIRef
- kbSyntax
api_type:
- UserDefined
api_location:
- d3d10umddi.h
api_name:
- IaSetInputLayout
product:
- Windows
targetos: Windows
tech.root: display
req.typenames: 
---

# PFND3D10DDI_SETINPUTLAYOUT callback function


## -description


The <i>IaSetInputLayout</i> function sets an input layout for the input assembler. 


## -parameters

### -param Arg1

*hDevice* [in]

A handle to the display device (graphics context).

### -param Arg2

*hInputLayout* [in]

A handle to the input layout object.


## -remarks

The driver can use the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d10ddi_seterror_cb">pfnSetErrorCb</a> callback function to set an error code. 



After the <i>IaSetInputLayout</i> function completes, all subsequent drawing operations use the given layout object until another is selected.

The driver should not encounter any error, except for D3DDDIERR_DEVICEREMOVED. Therefore, if the driver passes any error, except for D3DDDIERR_DEVICEREMOVED, in a call to the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d10ddi_seterror_cb">pfnSetErrorCb</a> function, the Direct3D runtime will determine that the error is critical. Even if the device was removed, the driver is not required to return D3DDDIERR_DEVICEREMOVED; however, if device removal interfered with the operation of <i>IaSetInputLayout</i> (which typically should not happen), the driver can return D3DDDIERR_DEVICEREMOVED.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/ns-d3d10umddi-d3d10ddi_devicefuncs">D3D10DDI_DEVICEFUNCS</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d10ddi_seterror_cb">pfnSetErrorCb</a>
 

 

