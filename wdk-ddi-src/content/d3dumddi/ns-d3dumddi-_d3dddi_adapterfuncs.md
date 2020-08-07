---
UID: NS:d3dumddi._D3DDDI_ADAPTERFUNCS
title: _D3DDDI_ADAPTERFUNCS (d3dumddi.h)
description: The D3DDDI_ADAPTERFUNCS structure contains functions that the user-mode display driver can implement to communicate with a graphics adapter object.
old-location: display\d3dddi_adapterfuncs.htm
tech.root: display
ms.assetid: bbf4852c-0fa5-47c0-a77e-7114b2a77549
ms.date: 05/10/2018
keywords: ["D3DDDI_ADAPTERFUNCS structure"]
ms.keywords: D3DDDI_ADAPTERFUNCS, D3DDDI_ADAPTERFUNCS structure [Display Devices], D3D_other_Structs_2397321f-704c-4c93-bbd1-b7591134294c.xml, _D3DDDI_ADAPTERFUNCS, d3dumddi/D3DDDI_ADAPTERFUNCS, display.d3dddi_adapterfuncs
f1_keywords:
 - "d3dumddi/D3DDDI_ADAPTERFUNCS"
 - "D3DDDI_ADAPTERFUNCS"
req.header: d3dumddi.h
req.include-header: D3dumddi.h
req.target-type: Windows
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
- HeaderDef
api_location:
- d3dumddi.h
api_name:
- D3DDDI_ADAPTERFUNCS
targetos: Windows
req.typenames: D3DDDI_ADAPTERFUNCS
---

# _D3DDDI_ADAPTERFUNCS structure


## -description


The D3DDDI_ADAPTERFUNCS structure contains functions that the user-mode display driver can implement to communicate with a graphics adapter object. 


## -struct-fields




### -field pfnGetCaps

A pointer to the driver's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dumddi/nc-d3dumddi-pfnd3dddi_getcaps">GetCaps</a> function that queries for capabilities of the graphics hardware.


### -field pfnCreateDevice

A pointer to the driver's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dumddi/nc-d3dumddi-pfnd3dddi_createdevice">CreateDevice</a> function that creates a representation of a display device that handles a collection of rendering state.


### -field pfnCloseAdapter

A pointer to the driver's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dumddi/nc-d3dumddi-pfnd3dddi_closeadapter">CloseAdapter</a> function that releases resources for a graphics adapter object.


## -remarks



Multiple graphics adapter objects can be created for a single physical graphics adapter.

The following code example demonstrates the function declarations for the functions that the members of D3DDDI_ADAPTERFUNCS point to.

```cpp
typedef HRESULT (APIENTRY *PFND3DDDI_GETCAPS)(HANDLE hAdapter, CONST D3DDDIARG_GETCAPS*);
typedef HRESULT (APIENTRY *PFND3DDDI_CREATEDEVICE)(IN HANDLE hAdapter, IN D3DDDIARG_CREATEDEVICE*);
typedef HRESULT (APIENTRY *PFND3DDDI_CLOSEADAPTER)(IN HANDLE hAdapter);
```


## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dumddi/nc-d3dumddi-pfnd3dddi_closeadapter">CloseAdapter</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dumddi/nc-d3dumddi-pfnd3dddi_createdevice">CreateDevice</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dumddi/ns-d3dumddi-_d3dddiarg_openadapter">D3DDDIARG_OPENADAPTER</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dumddi/nc-d3dumddi-pfnd3dddi_getcaps">GetCaps</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dumddi/nc-d3dumddi-pfnd3dddi_openadapter">OpenAdapter</a>
 

 

