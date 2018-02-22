---
UID: NS:d3d10umddi.D3D11DDI_HANDLESIZE
title: D3D11DDI_HANDLESIZE
author: windows-driver-content
description: The D3D11DDI_HANDLESIZE structure describes a handle.
old-location: display\d3d11ddi_handlesize.htm
old-project: display
ms.assetid: 9b785bee-289f-4f91-8183-c1dc2fa1fa6d
ms.author: windowsdriverdev
ms.date: 2/20/2018
ms.keywords: UMDisplayDriver_Dx11param_Structs_4eedfbd5-b87d-42bb-9ec9-2efc75ad3464.xml, display.d3d11ddi_handlesize, d3d10umddi/D3D11DDI_HANDLESIZE, D3D11DDI_HANDLESIZE, D3D11DDI_HANDLESIZE structure [Display Devices]
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: d3d10umddi.h
req.include-header: D3d10umddi.h
req.target-type: Windows
req.target-min-winverclnt: D3D11DDI_HANDLESIZE is supported beginning with the Windows 7 operating system.
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
-	d3d10umddi.h
apiname:
-	D3D11DDI_HANDLESIZE
product: Windows
targetos: Windows
req.typenames: D3D11DDI_HANDLESIZE
---

# D3D11DDI_HANDLESIZE structure


## -description


The D3D11DDI_HANDLESIZE structure describes a handle.


## -syntax


````
typedef struct D3D11DDI_HANDLESIZE {
  D3D11DDI_HANDLETYPE HandleType;
  SIZE_T              DriverPrivateSize;
} D3D11DDI_HANDLESIZE;
````


## -struct-fields




### -field HandleType

[in] A <a href="..\d3d10umddi\ne-d3d10umddi-d3d11ddi_handletype.md">D3D11DDI_HANDLETYPE</a>-typed value that identifies the handle type. 


### -field DriverPrivateSize

[in] The size, in bytes, of the driver-private memory space that holds the handle data. 


## -remarks



The driver's <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d11ddi_checkdeferredcontexthandlesizes.md">CheckDeferredContextHandleSizes</a> function verifies the size of the driver-private memory space that holds the handle data of a deferred context handle and returns the size in the <b>DriverPrivateSize</b> member of the D3D11DDI_HANDLESIZE structure that the <i>pHandleSize</i> parameter points to. 




## -see-also

<a href="..\d3d10umddi\ne-d3d10umddi-d3d11ddi_handletype.md">D3D11DDI_HANDLETYPE</a>



<a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d11ddi_checkdeferredcontexthandlesizes.md">CheckDeferredContextHandleSizes</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20D3D11DDI_HANDLESIZE structure%20 RELEASE:%20(2/20/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

