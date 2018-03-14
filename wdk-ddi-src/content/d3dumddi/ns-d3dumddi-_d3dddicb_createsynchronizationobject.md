---
UID: NS:d3dumddi._D3DDDICB_CREATESYNCHRONIZATIONOBJECT
title: "_D3DDDICB_CREATESYNCHRONIZATIONOBJECT"
author: windows-driver-content
description: The D3DDDICB_CREATESYNCHRONIZATIONOBJECT structure describes a synchronization object that the pfnCreateSynchronizationObjectCb function creates.
old-location: display\d3dddicb_createsynchronizationobject.htm
old-project: display
ms.assetid: e799a11c-eab7-4d85-9ed8-063e87aa351f
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: D3DDDICB_CREATESYNCHRONIZATIONOBJECT, D3DDDICB_CREATESYNCHRONIZATIONOBJECT structure [Display Devices], D3D_param_Structs_b52426c9-988d-4676-b906-cfa13cc9ffc5.xml, _D3DDDICB_CREATESYNCHRONIZATIONOBJECT, d3dumddi/D3DDDICB_CREATESYNCHRONIZATIONOBJECT, display.d3dddicb_createsynchronizationobject
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
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
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	d3dumddi.h
api_name:
-	D3DDDICB_CREATESYNCHRONIZATIONOBJECT
product: Windows
targetos: Windows
req.typenames: D3DDDICB_CREATESYNCHRONIZATIONOBJECT
---

# _D3DDDICB_CREATESYNCHRONIZATIONOBJECT structure


## -description


The D3DDDICB_CREATESYNCHRONIZATIONOBJECT structure describes a synchronization object that the <a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_createsynchronizationobjectcb.md">pfnCreateSynchronizationObjectCb</a> function creates.


## -syntax


````
typedef struct _D3DDDICB_CREATESYNCHRONIZATIONOBJECT {
  D3DDDI_SYNCHRONIZATIONOBJECTINFO Info;
  D3DKMT_HANDLE                    hSyncObject;
} D3DDDICB_CREATESYNCHRONIZATIONOBJECT;
````


## -struct-fields




### -field Info

[in] A <a href="..\d3dukmdt\ns-d3dukmdt-_d3dddi_synchronizationobjectinfo.md">D3DDDI_SYNCHRONIZATIONOBJECTINFO</a> structure that contains information about the kernel-mode synchronization object.


### -field hSyncObject

[out] A <b>D3DKMT_HANDLE</b> value that represents a kernel-mode handle to the kernel-mode synchronization object. 


## -see-also

<a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_createsynchronizationobjectcb.md">pfnCreateSynchronizationObjectCb</a>



<a href="..\d3dukmdt\ns-d3dukmdt-_d3dddi_synchronizationobjectinfo.md">D3DDDI_SYNCHRONIZATIONOBJECTINFO</a>



 

 


