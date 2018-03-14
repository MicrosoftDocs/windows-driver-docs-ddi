---
UID: NA:d3dumddi
ms.assetid: 64c7511b-6379-3c2f-bd00-f08eab970dc2
ms.author: windowsdriverdev
ms.date: 03/13/18
ms.keywords: 
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: portal
---

# D3Dumddi.h header



This header is used by Display. For more information, see
- [Display](../_display/index.md)

The reference pages in this section describe the functions that the user-mode display driver DLL supplies to the Microsoft Direct3D version 9 runtime. 

The user-mode display driver DLL exports the OpenAdapter function and supplies pointers to adapter-specific functions through members of the D3DDDI_ADAPTERFUNCS structure when the runtime calls OpenAdapter. 

The Direct3D runtime calls the CreateDevice function from the pfnCreateDevice member of D3DDDI_ADAPTERFUNCS to create a display device that is used to handle a collection of rendering state. The user-mode display driver DLL supplies pointers to all of its display device-specific functions through members of the D3DDDI_DEVICEFUNCS structure when the runtime calls the CreateDevice function.

Send comments about this topic to Microsoft

