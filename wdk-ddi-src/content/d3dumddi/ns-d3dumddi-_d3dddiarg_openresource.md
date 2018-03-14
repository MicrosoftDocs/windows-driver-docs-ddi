---
UID: NS:d3dumddi._D3DDDIARG_OPENRESOURCE
title: "_D3DDDIARG_OPENRESOURCE"
author: windows-driver-content
description: The D3DDDIARG_OPENRESOURCE structure contains information for opening a shared resource.
old-location: display\d3dddiarg_openresource.htm
old-project: display
ms.assetid: eb1b7317-2e54-4e61-a3e5-b5ac0c09064e
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: D3DDDIARG_OPENRESOURCE, D3DDDIARG_OPENRESOURCE structure [Display Devices], UMDisplayDriver_param_Structs_d0d23672-9994-4fad-b104-4eef57b3b03e.xml, _D3DDDIARG_OPENRESOURCE, d3dumddi/D3DDDIARG_OPENRESOURCE, display.d3dddiarg_openresource
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
-	D3DDDIARG_OPENRESOURCE
product: Windows
targetos: Windows
req.typenames: D3DDDIARG_OPENRESOURCE
---

# _D3DDDIARG_OPENRESOURCE structure


## -description


The D3DDDIARG_OPENRESOURCE structure contains information for opening a shared resource.


## -syntax


````
typedef struct _D3DDDIARG_OPENRESOURCE {
  UINT                      NumAllocations;
#if (D3D_UMD_INTERFACE_VERSION >= D3D_UMD_INTERFACE_VERSION_WIN7)
  union {
    D3DDDI_OPENALLOCATIONINFO  *pOpenAllocationInfo;
    D3DDDI_OPENALLOCATIONINFO2 *pOpenAllocationInfo2;
  };
#else 
  D3DDDI_OPENALLOCATIONINFO *pOpenAllocationInfo;
#endif 
  D3DKMT_HANDLE             hKMResource;
  VOID                      *pPrivateDriverData;
  UINT                      PrivateDriverDataSize;
  HANDLE                    hResource;
  D3DDDI_ROTATION           Rotation;
  D3DDDI_OPENRESOURCEFLAGS  Flags;
} D3DDDIARG_OPENRESOURCE;
````


## -struct-fields




### -field NumAllocations

[in] The number of elements in the array that is specified by <b>pOpenAllocationInfo</b>. <b>NumAllocations</b> represents the number of allocations to open.


### -field pOpenAllocationInfo

[in] An array of <a href="..\d3dukmdt\ns-d3dukmdt-_d3dddi_openallocationinfo.md">D3DDDI_OPENALLOCATIONINFO</a> structures that describe the allocations in the resource to open.

[in] An array of <a href="..\d3dukmdt\ns-d3dukmdt-_d3dddi_openallocationinfo.md">D3DDDI_OPENALLOCATIONINFO</a> structures that describe the allocations in the resource to open.


### -field hKMResource

[in] A D3DKMT_HANDLE data type that represents a kernel-mode handle to the resource that is associated with the allocations. 

This kernel-mode handle represents an existing shared resource that was previously created through a call to the user-mode display driver's <a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_createresource.md">CreateResource</a> function. 


### -field pPrivateDriverData

[in] A pointer to private data that was passed to the display miniport driver when the resource was created. This data is per resource and not per allocation like the private data in each allocation's <a href="..\d3dukmdt\ns-d3dukmdt-_d3dddi_openallocationinfo.md">D3DDDI_OPENALLOCATIONINFO</a> structure. 


### -field PrivateDriverDataSize

[in] The size, in bytes, of the private data that is pointed to by <b>pPrivateDriverData</b>.


### -field hResource

[in/out] A handle to the resource that is associated with the allocations. 

The user-mode display driver should save this handle and use it to identify the resource anytime that the driver calls back into the Microsoft Direct3D runtime. The user-mode display driver should generate a unique handle and pass it back to the Direct3D runtime. The Direct3D runtime uses this handle in driver calls to identify the resource.


### -field Rotation

[in] A <a href="..\d3dukmdt\ne-d3dukmdt-_d3dddi_rotation.md">D3DDDI_ROTATION</a>-typed value that identifies the orientation of the shared primary resource. 

When the primary resource is used with a full-screen device and is rotated, the driver might be required to create interim allocations to handle the full-screen device. The <b>Fullscreen</b> bitfield flag is set in the <b>Flags</b> member to indicate that the primary resource is used with a full-screen device.


### -field Flags

[in] A <a href="..\d3dumddi\ns-d3dumddi-_d3dddi_openresourceflags.md">D3DDDI_OPENRESOURCEFLAGS</a> structure that identifies the type of resource to open. 


#### - pOpenAllocationInfo2

This member is reserved and should be set to zero.

This member is available beginning with Windows 7.


## -remarks



The <b>Primary</b> and <b>SharedResource</b> bit-field flags are set in the <b>Flags</b> member of the <a href="..\d3dukmdt\ns-d3dukmdt-_d3dddiarg_createresource.md">D3DDDIARG_CREATERESOURCE</a> structure in a call to the <a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_createresource.md">CreateResource</a> function to create a shared primary resource.




## -see-also

<a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_openresource.md">OpenResource</a>



<a href="..\d3dumddi\ns-d3dumddi-_d3dddi_openresourceflags.md">D3DDDI_OPENRESOURCEFLAGS</a>



<a href="..\d3dukmdt\ns-d3dukmdt-_d3dddiarg_createresource.md">D3DDDIARG_CREATERESOURCE</a>



<a href="..\d3dukmdt\ns-d3dukmdt-_d3dddi_openallocationinfo.md">D3DDDI_OPENALLOCATIONINFO</a>



<a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_createresource.md">CreateResource</a>



<a href="..\d3dukmdt\ne-d3dukmdt-_d3dddi_rotation.md">D3DDDI_ROTATION</a>



 

 


