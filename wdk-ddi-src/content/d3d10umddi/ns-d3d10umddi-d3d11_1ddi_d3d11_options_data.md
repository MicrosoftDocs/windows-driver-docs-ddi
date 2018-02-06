---
UID: NS:d3d10umddi.D3D11_1DDI_D3D11_OPTIONS_DATA
title: D3D11_1DDI_D3D11_OPTIONS_DATA
author: windows-driver-content
description: Specifies options to provide data to the user-mode display driver.
old-location: display\d3d11_1ddi_d3d11_options_data.htm
old-project: display
ms.assetid: de5fa80e-d3bd-40ef-8e4d-07a0a336f25c
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: D3D11_1DDI_D3D11_OPTIONS_DATA, D3D11_1DDI_D3D11_OPTIONS_DATA structure [Display Devices], display.d3d11_1ddi_d3d11_options_data, d3d10umddi/D3D11_1DDI_D3D11_OPTIONS_DATA
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	D3d10umddi.h
apiname:
-	D3D11_1DDI_D3D11_OPTIONS_DATA
product: Windows
targetos: Windows
req.typenames: D3D11_1DDI_D3D11_OPTIONS_DATA
---

# D3D11_1DDI_D3D11_OPTIONS_DATA structure


## -description


Specifies options to provide data to the user-mode display driver.


## -syntax


````
typedef struct D3D11_1DDI_D3D11_OPTIONS_DATA {
  BOOL OutputMergerLogicOp;
  BOOL AssignDebugBinarySupport;
} D3D11_1DDI_D3D11_OPTIONS_DATA;
````


## -struct-fields




### -field OutputMergerLogicOp

Specifies whether logic operations are available in the blend state. The user-mode display driver sets this member to <b>TRUE</b> if logic operations are available in the blend state and <b>FALSE</b> otherwise. This member is <b>FALSE</b> if the   driver supports Direct3D feature level 9.1, 9.2, and 9.3. This member is optional if the driver supports feature level 10, 10.1, and 11. This member is <b>TRUE</b> if the driver supports feature level 11.1 and later.


### -field AssignDebugBinarySupport

Specifies whether the driver supports the <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d11_1ddi_assigndebugbinary.md">AssignDebugBinary</a> function, which provides the full shader binary that is available after shader creation.


## -see-also

<a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d11_1ddi_assigndebugbinary.md">AssignDebugBinary</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20D3D11_1DDI_D3D11_OPTIONS_DATA structure%20 RELEASE:%20(12/29/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

