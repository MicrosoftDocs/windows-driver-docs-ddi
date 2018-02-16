---
UID: NS:d3dumddi._D3DDDIARG_DXVAHD_CREATEVIDEOPROCESSOR
title: "_D3DDDIARG_DXVAHD_CREATEVIDEOPROCESSOR"
author: windows-driver-content
description: The D3DDDIARG_DXVAHD_CREATEVIDEOPROCESSOR structure describes a Microsoft DirectX Video Acceleration (DirectX VA) video processor to create.
old-location: display\d3dddiarg_dxvahd_createvideoprocessor.htm
old-project: display
ms.assetid: fafb1b1f-409d-4eab-a5dd-22fd1ab830d2
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: d3dumddi/D3DDDIARG_DXVAHD_CREATEVIDEOPROCESSOR, D3DDDIARG_DXVAHD_CREATEVIDEOPROCESSOR, _D3DDDIARG_DXVAHD_CREATEVIDEOPROCESSOR, D3DDDIARG_DXVAHD_CREATEVIDEOPROCESSOR structure [Display Devices], display.d3dddiarg_dxvahd_createvideoprocessor, UMDisplayDriver_param_Structs_c2d925e2-646c-46dc-9795-1a885aa64a02.xml
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: d3dumddi.h
req.include-header: D3dumddi.h
req.target-type: Windows
req.target-min-winverclnt: D3DDDIARG_DXVAHD_CREATEVIDEOPROCESSOR is supported beginning with the Windows 7 operating system.
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
-	d3dumddi.h
apiname:
-	D3DDDIARG_DXVAHD_CREATEVIDEOPROCESSOR
product: Windows
targetos: Windows
req.typenames: D3DDDIARG_DXVAHD_CREATEVIDEOPROCESSOR
---

# _D3DDDIARG_DXVAHD_CREATEVIDEOPROCESSOR structure


## -description


The D3DDDIARG_DXVAHD_CREATEVIDEOPROCESSOR structure describes a Microsoft DirectX Video Acceleration (DirectX VA) video processor to create. 


## -syntax


````
typedef struct _D3DDDIARG_DXVAHD_CREATEVIDEOPROCESSOR {
  const GUID *pVPGuid;
  HANDLE     hVideoProcessor;
} D3DDDIARG_DXVAHD_CREATEVIDEOPROCESSOR;
````


## -struct-fields




### -field pVPGuid

[in] A pointer to the GUID that represents a DirectX VA video processor to create. The Microsoft Direct3D runtime can call the user-mode display driver's <a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_getcaps.md">GetCaps</a> function to query (D3DDDICAPS_DXVAHD_GETVPCAPS) for the capabilities of the video processors that the driver supports. Each <b>VPGuid</b> member of the <a href="..\d3dumddi\ns-d3dumddi-_dxvahdddi_vpcaps.md">DXVAHDDDI_VPCAPS</a> structure in the array that the driver's <b>GetCaps</b> returns specifies a video processor that the driver supports.  


### -field hVideoProcessor

[out] A handle to the video processor. The user-mode display driver must set this handle to a value that the Microsoft Direct3D runtime can use to identify the video processor in subsequent calls. 


## -see-also

<a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_dxvahd_createvideoprocessor.md">CreateVideoProcessor</a>



<a href="..\d3dumddi\ns-d3dumddi-_dxvahdddi_vpcaps.md">DXVAHDDDI_VPCAPS</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20D3DDDIARG_DXVAHD_CREATEVIDEOPROCESSOR structure%20 RELEASE:%20(12/29/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

