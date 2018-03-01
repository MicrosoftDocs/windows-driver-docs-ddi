---
UID: NS:d3dumddi._D3DDDIARG_EXTENSIONEXECUTE
title: "_D3DDDIARG_EXTENSIONEXECUTE"
author: windows-driver-content
description: The D3DDDIARG_EXTENSIONEXECUTE structure describes a Microsoft DirectX Video Acceleration (VA) extension operation to perform.
old-location: display\d3dddiarg_extensionexecute.htm
old-project: display
ms.assetid: adc3e8a0-b261-47dc-ada2-bd21cb3ca954
ms.author: windowsdriverdev
ms.date: 2/24/2018
ms.keywords: D3DDDIARG_EXTENSIONEXECUTE, D3DDDIARG_EXTENSIONEXECUTE structure [Display Devices], UMDisplayDriver_param_Structs_99780923-fb21-4c84-bced-973ebfe44b1a.xml, _D3DDDIARG_EXTENSIONEXECUTE, d3dumddi/D3DDDIARG_EXTENSIONEXECUTE, display.d3dddiarg_extensionexecute
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
-	D3DDDIARG_EXTENSIONEXECUTE
product: Windows
targetos: Windows
req.typenames: D3DDDIARG_EXTENSIONEXECUTE
---

# _D3DDDIARG_EXTENSIONEXECUTE structure


## -description


The D3DDDIARG_EXTENSIONEXECUTE structure describes a Microsoft DirectX Video Acceleration (VA) extension operation to perform.


## -syntax


````
typedef struct _D3DDDIARG_EXTENSIONEXECUTE {
  HANDLE                hExtension;
  UINT                  Function;
  DXVADDI_PRIVATEDATA   *pPrivateInput;
  DXVADDI_PRIVATEDATA   *pPrivateOutput;
  UINT                  NumBuffers;
  DXVADDI_PRIVATEBUFFER *pBuffers;
} D3DDDIARG_EXTENSIONEXECUTE;
````


## -struct-fields




### -field hExtension

[in] A handle to the DirectX VA extension device. The user-mode display driver returns this handle in a call to its <a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_createextensiondevice.md">CreateExtensionDevice</a> function.


### -field Function

[in] A specific operation to perform. The possible values for this member are defined by the extension device.


### -field pPrivateInput

[in] A pointer to a <a href="..\d3dumddi\ns-d3dumddi-_dxvaddi_privatedata.md">DXVADDI_PRIVATEDATA</a> structure that contains data that the driver requires to perform the extension operation.


### -field pPrivateOutput

[in] A pointer to a DXVADDI_PRIVATEDATA structure that contains data about the extension operation that the driver returns.


### -field NumBuffers

[in] The number of buffers in the list that is pointed to by <b>pBuffers</b>.


### -field pBuffers


      [in] A pointer to a list of <a href="..\d3dumddi\ns-d3dumddi-_dxvaddi_privatebuffer.md">DXVADDI_PRIVATEBUFFER</a> structures that describe private buffers that an extension device uses to perform an extended operation.
     


## -see-also

<a href="..\d3dumddi\ns-d3dumddi-_dxvaddi_privatedata.md">DXVADDI_PRIVATEDATA</a>



<a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_extensionexecute.md">ExtensionExecute</a>



<a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_createextensiondevice.md">CreateExtensionDevice</a>



<a href="..\d3dumddi\ns-d3dumddi-_dxvaddi_privatebuffer.md">DXVADDI_PRIVATEBUFFER</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20D3DDDIARG_EXTENSIONEXECUTE structure%20 RELEASE:%20(2/24/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

