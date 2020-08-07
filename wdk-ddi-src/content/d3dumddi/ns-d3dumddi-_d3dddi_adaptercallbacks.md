---
UID: NS:d3dumddi._D3DDDI_ADAPTERCALLBACKS
title: _D3DDDI_ADAPTERCALLBACKS (d3dumddi.h)
description: The D3DDDI_ADAPTERCALLBACKS structure contains Microsoft Direct3D runtime callback functions that the user-mode display driver can use.
old-location: display\d3dddi_adaptercallbacks.htm
tech.root: display
ms.assetid: b912449b-45d1-473d-aa14-b3f3ffbfefff
ms.date: 05/10/2018
keywords: ["D3DDDI_ADAPTERCALLBACKS structure"]
ms.keywords: D3DDDI_ADAPTERCALLBACKS, D3DDDI_ADAPTERCALLBACKS structure [Display Devices], D3D_other_Structs_6919397d-68ab-4ada-9f39-bf08bc0ac9ae.xml, _D3DDDI_ADAPTERCALLBACKS, d3dumddi/D3DDDI_ADAPTERCALLBACKS, display.d3dddi_adaptercallbacks
f1_keywords:
 - "d3dumddi/D3DDDI_ADAPTERCALLBACKS"
 - "D3DDDI_ADAPTERCALLBACKS"
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
- D3DDDI_ADAPTERCALLBACKS
targetos: Windows
req.typenames: D3DDDI_ADAPTERCALLBACKS
---

# _D3DDDI_ADAPTERCALLBACKS structure


## -description


The D3DDDI_ADAPTERCALLBACKS structure contains Microsoft Direct3D runtime callback functions that the user-mode display driver can use.


## -struct-fields




### -field pfnQueryAdapterInfoCb

A pointer to the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dumddi/nc-d3dumddi-pfnd3dddi_queryadapterinfocb">pfnQueryAdapterInfoCb</a> function, which the user-mode display driver uses to query the display miniport driver for adapter configuration information.


### -field pfnGetMultisampleMethodListCb

A pointer to the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dumddi/nc-d3dumddi-pfnd3dddi_getmultisamplemethodlistcb">pfnGetMultisampleMethodListCb</a> function, which the user-mode display driver uses to retrieve the list of multiple-sampling methods that are used for an allocation.

### -field pfnQueryAdapterInfoCb2

## -remarks



The following code example demonstrates the function declarations for the functions that the members of D3DDDI_ADAPTERCALLBACKS point to.

```cpp
typedef HRESULT (APIENTRY CALLBACK *PFND3DDDI_QUERYADAPTERINFOCB)(HANDLE hAdapter, CONST D3DDDICB_QUERYADAPTERINFO*);
typedef HRESULT (APIENTRY CALLBACK *PFND3DDDI_GETMULTISAMPLEMETHODLISTCB)(HANDLE hAdapter, D3DDDICB_GETMULTISAMPLEMETHODLIST*);
```


## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dumddi/ns-d3dumddi-_d3dddiarg_openadapter">D3DDDIARG_OPENADAPTER</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dumddi/nc-d3dumddi-pfnd3dddi_openadapter">OpenAdapter</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dumddi/nc-d3dumddi-pfnd3dddi_getmultisamplemethodlistcb">pfnGetMultisampleMethodListCb</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dumddi/nc-d3dumddi-pfnd3dddi_queryadapterinfocb">pfnQueryAdapterInfoCb</a>
 

 

