---
UID: NC:d3dumddi.PFND3DDDI_ESCAPECB
title: PFND3DDDI_ESCAPECB
description: The pfnEscapeCb callback function shares information with the display miniport driver.
old-location: display\pfnescapecb.htm
tech.root: display
ms.assetid: 66c0347f-2cf3-42fc-8641-47c731e958c9
ms.date: 05/10/2018
ms.keywords: D3Druntime_Functions_8c7e48ef-f8e8-45d2-a424-9065e97f725f.xml, PFND3DDDI_ESCAPECB, PFND3DDDI_ESCAPECB callback, d3dumddi/pfnEscapeCb, display.pfnescapecb, pfnEscapeCb, pfnEscapeCb callback function [Display Devices]
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	UserDefined
api_location:
-	d3dumddi.h
api_name:
-	pfnEscapeCb
product:
- Windows
targetos: Windows
req.typenames: 
---

# PFND3DDDI_ESCAPECB callback function


## -description


The <b>pfnEscapeCb</b> callback function shares information with the display miniport driver.


## -parameters




### -param hAdapter [in]

A handle to the graphics adapter object.


### -param *








*pData* [in, out]

A pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/ff544190">D3DDDICB_ESCAPE</a> structure that describes the shared information.


## -returns



<b>pfnEscapeCb</b> returns one of the following values:

| **Return code** | **Description** | 
|:--|:--|
| **S_OK** | Information was successfully shared. | 
| **E_OUTOFMEMORY** | pfnEscapeCb could not complete because of insufficient memory. | 
| **E_INVALIDARG** |     Parameters were validated and determined to be incorrect.| 
| **D3DDDIERR_DEVICEREMOVED** | pfnEscapeCb could not initiate a call to the display miniport driver's [DxgkDdiEscape](https://msdn.microsoft.com/79a524cd-dec1-4ea8-a660-d9d9c644e162) function because a Plug and Play (PnP) stop or a Timeout Detection and Recovery (TDR) event occurred. The user-mode display driver function that called pfnEscapeCb must return this error code back to the Direct3D runtime.<br/>**Direct3D Version 9** Note:  For more information about returning error codes, see [Returning Error Codes Received from Runtime Functions](https://msdn.microsoft.com/4a2384e8-407f-4248-8b31-7c4e836b15dc).<br/>**Direct3D Versions 10 and 11** Note:  If the driver function does not return a value (that is, has VOID for a return parameter type), the driver function calls the [pfnSetErrorCb](https://msdn.microsoft.com/968b04a7-8869-410c-a6fc-83d57726858f) function to send an error code back to the runtime. For more information about handling error codes, see [Handling Errors](https://msdn.microsoft.com/ac4e056e-3304-4934-887a-5cc2b87989bd). |

 

This function might also return other HRESULT values.




## -remarks



A user-mode display driver calls <b>pfnEscapeCb</b> to share miscellaneous information with the display miniport driver in a way that is not supported by any other driver communication. The user-mode display driver can send miscellaneous information to the display miniport driver or can retrieve information from the display miniport driver. 

<b>Direct3D Version 11 Note:  </b>For more information about how the driver calls <b>pfnEscapeCb</b>, see <a href="https://msdn.microsoft.com/014a5e44-f8c4-45c0-96e8-d82f37b8b28d">Changes from Direct3D 10</a>.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff544190">D3DDDICB_ESCAPE</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff544512">D3DDDI_DEVICECALLBACKS</a>



<a href="https://msdn.microsoft.com/79a524cd-dec1-4ea8-a660-d9d9c644e162">DxgkDdiEscape</a>
 

 

