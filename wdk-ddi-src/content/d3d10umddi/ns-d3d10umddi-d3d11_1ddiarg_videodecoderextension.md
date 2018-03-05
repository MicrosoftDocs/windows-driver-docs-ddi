---
UID: NS:d3d10umddi.D3D11_1DDIARG_VIDEODECODEREXTENSION
title: D3D11_1DDIARG_VIDEODECODEREXTENSION
author: windows-driver-content
description: Specifies driver-specific data for the extended Microsoft DirectX Video Acceleration (DXVA) decoding function that is provided by a call to the VideoDecoderExtension function.
old-location: display\d3d11_1ddiarg_videodecoderextension.htm
old-project: display
ms.assetid: d11a6be1-f723-47eb-b131-e1b02451e18a
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: D3D11_1DDIARG_VIDEODECODEREXTENSION, D3D11_1DDIARG_VIDEODECODEREXTENSION structure [Display Devices], d3d10umddi/D3D11_1DDIARG_VIDEODECODEREXTENSION, display.d3d11_1ddiarg_videodecoderextension
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: d3d10umddi.h
req.include-header: D3d10umddi.h
req.target-type: Windows
req.target-min-winverclnt: Windows 8
req.target-min-winversvr: Windows Server 2012
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
-	D3d10umddi.h
api_name:
-	D3D11_1DDIARG_VIDEODECODEREXTENSION
product: Windows
targetos: Windows
req.typenames: D3D11_1DDIARG_VIDEODECODEREXTENSION
---

# D3D11_1DDIARG_VIDEODECODEREXTENSION structure


## -description


Specifies driver-specific data for the extended Microsoft DirectX Video Acceleration (DXVA) decoding function that is provided by a call to the <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d11_1ddi_videodecoderextension.md">VideoDecoderExtension</a> function.


## -syntax


````
typedef struct D3D11_1DDIARG_VIDEODECODEREXTENSION {
  UINT               Function;
  void               *pPrivateInputData;
  UINT               PrivateInputDataSize;
  void               *pPrivateOutputData;
  UINT               PrivateOutputDataSize;
  UINT               ResourceCount;
  D3D10DDI_HRESOURCE *pResourceList;
} D3D11_1DDIARG_VIDEODECODEREXTENSION;
````


## -struct-fields




### -field Function

The function number. This number identifies the operation to perform. Currently no function numbers are defined.


### -field pPrivateInputData

A pointer to a buffer that contains input data for the driver.


### -field PrivateInputDataSize

The size of the buffer pointed to by <b>pPrivateInputData</b>, in bytes.


### -field pPrivateOutputData

A pointer to a buffer that the driver can use to write output data.


### -field PrivateOutputDataSize

The size of the buffer pointed to by <b>pPrivateOutputData</b>, in bytes.


### -field ResourceCount

The number of elements in the <b>pResourceList</b> array. If <b>pResourceList</b> is <b>NULL</b>, set <b>ResourceCount</b> to zero.


### -field pResourceList

A pointer to an array of resource handles. Use this member to pass Direct3D resources to the driver.


## -remarks



The exact meaning of each structure member depends on the value of <b>Function</b>.




## -see-also

<a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d11_1ddi_videodecoderextension.md">VideoDecoderExtension</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20D3D11_1DDIARG_VIDEODECODEREXTENSION structure%20 RELEASE:%20(2/26/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

