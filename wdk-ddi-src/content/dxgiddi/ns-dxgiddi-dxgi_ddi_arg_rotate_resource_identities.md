---
UID: NS:dxgiddi.DXGI_DDI_ARG_ROTATE_RESOURCE_IDENTITIES
title: DXGI_DDI_ARG_ROTATE_RESOURCE_IDENTITIES
author: windows-driver-content
description: Describes a list of resources to rotate.
old-location: display\dxgi_ddi_arg_rotate_resource_identities.htm
old-project: display
ms.assetid: 904b16d1-44dc-4d7a-96cb-3fd82d378b24
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: DXGI_DDI_ARG_ROTATE_RESOURCE_IDENTITIES, DXGI_DDI_ARG_ROTATE_RESOURCE_IDENTITIES structure [Display Devices], UMDisplayDriver_Dx10param_Structs_f52f40ab-97f1-4c3f-839f-9da2dc8e7798.xml, display.dxgi_ddi_arg_rotate_resource_identities, dxgiddi/DXGI_DDI_ARG_ROTATE_RESOURCE_IDENTITIES
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: dxgiddi.h
req.include-header: D3d10umddi.h
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
-	dxgiddi.h
api_name:
-	DXGI_DDI_ARG_ROTATE_RESOURCE_IDENTITIES
product: Windows
targetos: Windows
req.typenames: DXGI_DDI_ARG_ROTATE_RESOURCE_IDENTITIES
---

# DXGI_DDI_ARG_ROTATE_RESOURCE_IDENTITIES structure


## -description


Describes a list of resources to rotate. 


## -struct-fields




### -field hDevice

[in] A handle to the display device (graphics context) on which the driver rotates resources. The Direct3D runtime passes this handle to the driver in the <b>hDrvDevice</b> member of the <a href="https://msdn.microsoft.com/library/windows/hardware/ff541664">D3D10DDIARG_CREATEDEVICE</a> structure when the runtime calls the driver's <a href="https://msdn.microsoft.com/c69eedb1-c975-412c-aa9f-cf64a702f937">CreateDevice(D3D10)</a> function to create the display device. 


### -field pResources

[in] A pointer to an array of handles to the resources to rotate.

Beginning in Windows 8, the driver must support rotation of stereo back buffers.


### -field Resources

[in] The number of elements in the <i>pResources</i> array.  


## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff569514">RotateResourceIdentitiesDXGI</a>
 

 

