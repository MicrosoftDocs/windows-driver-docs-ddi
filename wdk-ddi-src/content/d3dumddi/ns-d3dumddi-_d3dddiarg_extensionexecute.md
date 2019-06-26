---
UID: NS:d3dumddi._D3DDDIARG_EXTENSIONEXECUTE
title: _D3DDDIARG_EXTENSIONEXECUTE (d3dumddi.h)
description: The D3DDDIARG_EXTENSIONEXECUTE structure describes a Microsoft DirectX Video Acceleration (VA) extension operation to perform.
old-location: display\d3dddiarg_extensionexecute.htm
tech.root: display
ms.assetid: adc3e8a0-b261-47dc-ada2-bd21cb3ca954
ms.date: 05/10/2018
ms.keywords: D3DDDIARG_EXTENSIONEXECUTE, D3DDDIARG_EXTENSIONEXECUTE structure [Display Devices], UMDisplayDriver_param_Structs_99780923-fb21-4c84-bced-973ebfe44b1a.xml, _D3DDDIARG_EXTENSIONEXECUTE, d3dumddi/D3DDDIARG_EXTENSIONEXECUTE, display.d3dddiarg_extensionexecute
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
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- d3dumddi.h
api_name:
- D3DDDIARG_EXTENSIONEXECUTE
product:
- Windows
targetos: Windows
req.typenames: D3DDDIARG_EXTENSIONEXECUTE
---

# _D3DDDIARG_EXTENSIONEXECUTE structure


## -description


The D3DDDIARG_EXTENSIONEXECUTE structure describes a Microsoft DirectX Video Acceleration (VA) extension operation to perform.


## -struct-fields




### -field hExtension

[in] A handle to the DirectX VA extension device. The user-mode display driver returns this handle in a call to its <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3dumddi/nc-d3dumddi-pfnd3dddi_createextensiondevice">CreateExtensionDevice</a> function.


### -field Function

[in] A specific operation to perform. The possible values for this member are defined by the extension device.


### -field pPrivateInput

[in] A pointer to a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3dumddi/ns-d3dumddi-_dxvaddi_privatedata">DXVADDI_PRIVATEDATA</a> structure that contains data that the driver requires to perform the extension operation.


### -field pPrivateOutput

[in] A pointer to a DXVADDI_PRIVATEDATA structure that contains data about the extension operation that the driver returns.


### -field NumBuffers

[in] The number of buffers in the list that is pointed to by <b>pBuffers</b>.


### -field pBuffers


      [in] A pointer to a list of <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3dumddi/ns-d3dumddi-_dxvaddi_privatebuffer">DXVADDI_PRIVATEBUFFER</a> structures that describe private buffers that an extension device uses to perform an extended operation.
     


## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3dumddi/nc-d3dumddi-pfnd3dddi_createextensiondevice">CreateExtensionDevice</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3dumddi/ns-d3dumddi-_dxvaddi_privatebuffer">DXVADDI_PRIVATEBUFFER</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3dumddi/ns-d3dumddi-_dxvaddi_privatedata">DXVADDI_PRIVATEDATA</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3dumddi/nc-d3dumddi-pfnd3dddi_extensionexecute">ExtensionExecute</a>
 

 

