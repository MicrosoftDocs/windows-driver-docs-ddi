---
UID: NS:d3dumddi._D3DDDIARG_CREATEEXTENSIONDEVICE
title: _D3DDDIARG_CREATEEXTENSIONDEVICE (d3dumddi.h)
description: The D3DDDIARG_CREATEEXTENSIONDEVICE structure describes a Microsoft DirectX Video Acceleration (DirectX VA) extension device to create.
old-location: display\d3dddiarg_createextensiondevice.htm
tech.root: display
ms.assetid: 33076a24-8856-4533-b4ab-ec1d7bdb083d
ms.date: 05/10/2018
keywords: ["_D3DDDIARG_CREATEEXTENSIONDEVICE structure"]
ms.keywords: D3DDDIARG_CREATEEXTENSIONDEVICE, D3DDDIARG_CREATEEXTENSIONDEVICE structure [Display Devices], UMDisplayDriver_param_Structs_edb27385-af11-4750-aa90-854e21ee11a0.xml, _D3DDDIARG_CREATEEXTENSIONDEVICE, d3dumddi/D3DDDIARG_CREATEEXTENSIONDEVICE, display.d3dddiarg_createextensiondevice
f1_keywords:
 - "d3dumddi/D3DDDIARG_CREATEEXTENSIONDEVICE"
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
- D3DDDIARG_CREATEEXTENSIONDEVICE
product:
- Windows
targetos: Windows
req.typenames: D3DDDIARG_CREATEEXTENSIONDEVICE
---

# _D3DDDIARG_CREATEEXTENSIONDEVICE structure


## -description


The D3DDDIARG_CREATEEXTENSIONDEVICE structure describes a Microsoft DirectX Video Acceleration (DirectX VA) extension device to create. 


## -struct-fields




### -field pGuid

[in] A pointer to the GUID that represents the DirectX VA extension type. The Microsoft Direct3D runtime calls the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dumddi/nc-d3dumddi-pfnd3dddi_getcaps">GetCaps</a> function to query for the supported extension GUIDs.


### -field pPrivate

[in] A pointer to the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dumddi/ns-d3dumddi-_dxvaddi_privatedata">DXVADDI_PRIVATEDATA</a> structure that contains data that the driver requires to create the extension device. 


### -field hExtension

[in/out] A handle to the extension device. The user-mode display driver must set this handle to a value that the Direct3D runtime can use to identify the extension device in subsequent calls.


## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dumddi/nc-d3dumddi-pfnd3dddi_createextensiondevice">CreateExtensionDevice</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dumddi/ns-d3dumddi-_dxvaddi_privatedata">DXVADDI_PRIVATEDATA</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dumddi/nc-d3dumddi-pfnd3dddi_getcaps">GetCaps</a>
 

 

