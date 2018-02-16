---
UID: NS:dxgiddi.DXGI_DDI_ARG_ROTATE_RESOURCE_IDENTITIES
title: DXGI_DDI_ARG_ROTATE_RESOURCE_IDENTITIES
author: windows-driver-content
description: Describes a list of resources to rotate.
old-location: display\dxgi_ddi_arg_rotate_resource_identities.htm
old-project: display
ms.assetid: 904b16d1-44dc-4d7a-96cb-3fd82d378b24
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: DXGI_DDI_ARG_ROTATE_RESOURCE_IDENTITIES, display.dxgi_ddi_arg_rotate_resource_identities, dxgiddi/DXGI_DDI_ARG_ROTATE_RESOURCE_IDENTITIES, UMDisplayDriver_Dx10param_Structs_f52f40ab-97f1-4c3f-839f-9da2dc8e7798.xml, DXGI_DDI_ARG_ROTATE_RESOURCE_IDENTITIES structure [Display Devices]
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	dxgiddi.h
apiname:
-	DXGI_DDI_ARG_ROTATE_RESOURCE_IDENTITIES
product: Windows
targetos: Windows
req.typenames: DXGI_DDI_ARG_ROTATE_RESOURCE_IDENTITIES
---

# DXGI_DDI_ARG_ROTATE_RESOURCE_IDENTITIES structure


## -description


Describes a list of resources to rotate. 


## -syntax


````
typedef struct DXGI_DDI_ARG_ROTATE_RESOURCE_IDENTITIES {
  DXGI_DDI_HDEVICE         hDevice;
  const DXGI_DDI_HRESOURCE *pResources;
  UINT                     Resources;
} DXGI_DDI_ARG_ROTATE_RESOURCE_IDENTITIES;
````


## -struct-fields




### -field hDevice

[in] A handle to the display device (graphics context) on which the driver rotates resources. The Direct3D runtime passes this handle to the driver in the <b>hDrvDevice</b> member of the <a href="..\d3d10umddi\ns-d3d10umddi-d3d10ddiarg_createdevice.md">D3D10DDIARG_CREATEDEVICE</a> structure when the runtime calls the driver's <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi_createdevice.md">CreateDevice(D3D10)</a> function to create the display device. 


### -field pResources

[in] A pointer to an array of handles to the resources to rotate.

Beginning in Windows 8, the driver must support rotation of stereo back buffers.


### -field Resources

[in] The number of elements in the <i>pResources</i> array.  


## -see-also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff569514">RotateResourceIdentitiesDXGI</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20DXGI_DDI_ARG_ROTATE_RESOURCE_IDENTITIES structure%20 RELEASE:%20(12/29/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

