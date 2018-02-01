---
UID: NS:d3dumddi._D3DDDIARG_CREATEDECODEDEVICE
title: "_D3DDDIARG_CREATEDECODEDEVICE"
author: windows-driver-content
description: The D3DDDIARG_CREATEDECODEDEVICE structure describes a Microsoft DirectX Video Acceleration (DirectX VA) decode device to create.
old-location: display\d3dddiarg_createdecodedevice.htm
old-project: display
ms.assetid: 15750301-da36-4341-8d5a-ab76a2edb970
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: display.d3dddiarg_createdecodedevice, D3DDDIARG_CREATEDECODEDEVICE, _D3DDDIARG_CREATEDECODEDEVICE, UMDisplayDriver_param_Structs_eb54920e-5904-4a9d-bfac-fe71743b2726.xml, d3dumddi/D3DDDIARG_CREATEDECODEDEVICE, D3DDDIARG_CREATEDECODEDEVICE structure [Display Devices]
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	d3dumddi.h
apiname:
-	D3DDDIARG_CREATEDECODEDEVICE
product: Windows
targetos: Windows
req.typenames: D3DDDIARG_CREATEDECODEDEVICE
---

# _D3DDDIARG_CREATEDECODEDEVICE structure


## -description


The D3DDDIARG_CREATEDECODEDEVICE structure describes a Microsoft DirectX Video Acceleration (DirectX VA) decode device to create. 


## -syntax


````
typedef struct _D3DDDIARG_CREATEDECODEDEVICE {
  const GUID                  *pGuid;
  DXVADDI_VIDEODESC           VideoDesc;
  DXVADDI_CONFIGPICTUREDECODE *pConfig;
  HANDLE                      hDecode;
} D3DDDIARG_CREATEDECODEDEVICE;
````


## -struct-fields




### -field pGuid

[in] A pointer to the GUID that represents the DirectX VA decode type. The Microsoft Direct3D runtime calls the <a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_getcaps.md">GetCaps</a> function to query for the supported GUIDs.


### -field VideoDesc

[in] The <a href="..\d3dumddi\ns-d3dumddi-_dxvaddi_videodesc.md">DXVADDI_VIDEODESC</a> structure for the video stream that the decode device should decode.


### -field pConfig

[in] A pointer to the <a href="..\d3dumddi\ns-d3dumddi-_dxvaddi_configpicturedecode.md">DXVADDI_CONFIGPICTUREDECODE</a> structure that contains the DirectX VA connection configuration data for compressed picture decoding that the decode device requires. The Direct3D runtime calls the <a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_getcaps.md">GetCaps</a> function to query for the supported configurations.


### -field hDecode

[in/out] A handle to the decode device. The user-mode display driver must set this handle to a value that the Direct3D runtime can use to identify the decode device in subsequent calls.


## -see-also

<a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_createdecodedevice.md">CreateDecodeDevice</a>

<a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_getcaps.md">GetCaps</a>

<a href="..\d3dumddi\ns-d3dumddi-_dxvaddi_configpicturedecode.md">DXVADDI_CONFIGPICTUREDECODE</a>

<a href="..\d3dumddi\ns-d3dumddi-_dxvaddi_videodesc.md">DXVADDI_VIDEODESC</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20D3DDDIARG_CREATEDECODEDEVICE structure%20 RELEASE:%20(12/29/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

