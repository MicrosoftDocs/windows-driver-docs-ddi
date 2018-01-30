---
UID: NS:d3d10umddi.D3D11_1DDI_AUTHENTICATED_CONFIGURE_PROTECTION
title: D3D11_1DDI_AUTHENTICATED_CONFIGURE_PROTECTION
author: windows-driver-content
description: Contains input data for a call to the ConfigureAuthenticatedChannel(D3D11_1) function when D3D11_1DDI_AUTHENTICATED_CONFIGURE_INPUT.ConfigureType has a GUID value of D3D11_AUTHENTICATED_CONFIGURE_PROTECTION.
old-location: display\d3d11_1ddi_authenticated_configure_protection.htm
old-project: display
ms.assetid: 2932fd35-54dc-4054-99e5-9b33aac77413
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: d3d10umddi/D3D11_1DDI_AUTHENTICATED_CONFIGURE_PROTECTION, display.d3d11_1ddi_authenticated_configure_protection, D3D11_1DDI_AUTHENTICATED_CONFIGURE_PROTECTION structure [Display Devices], D3D11_1DDI_AUTHENTICATED_CONFIGURE_PROTECTION
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
-	D3D11_1DDI_AUTHENTICATED_CONFIGURE_PROTECTION
product: Windows
targetos: Windows
req.typenames: D3D11_1DDI_AUTHENTICATED_CONFIGURE_PROTECTION
---

# D3D11_1DDI_AUTHENTICATED_CONFIGURE_PROTECTION structure


## -description


Contains input data for a call to the <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d11_1ddi_configureauthenticatedchannel.md">ConfigureAuthenticatedChannel(D3D11_1)</a> function when <a href="..\d3d10umddi\ns-d3d10umddi-d3d11_1ddi_authenticated_configure_input.md">D3D11_1DDI_AUTHENTICATED_CONFIGURE_INPUT</a>.<b>ConfigureType</b> has a GUID value of <b>D3D11_AUTHENTICATED_CONFIGURE_PROTECTION</b>.


## -syntax


````
typedef struct D3D11_1DDI_AUTHENTICATED_CONFIGURE_PROTECTION {
  D3D11_1DDI_AUTHENTICATED_CONFIGURE_INPUT  Parameters;
  D3D11_1DDI_AUTHENTICATED_PROTECTION_FLAGS Protections;
} D3D11_1DDI_AUTHENTICATED_CONFIGURE_PROTECTION;
````


## -struct-fields




### -field Parameters

A <a href="..\d3d10umddi\ns-d3d10umddi-d3d11_1ddi_authenticated_configure_input.md">D3D11_1DDI_AUTHENTICATED_CONFIGURE_INPUT</a> structure that contains the command GUID and other data. 


### -field Protections

A <a href="..\d3d10umddi\ns-d3d10umddi-d3d11_1ddi_authenticated_protection_flags.md">D3D11_1DDI_AUTHENTICATED_PROTECTION_FLAGS</a> structure that specifies the protection level.




## -see-also

<a href="..\d3d10umddi\ns-d3d10umddi-d3d11_1ddi_authenticated_configure_input.md">D3D11_1DDI_AUTHENTICATED_CONFIGURE_INPUT</a>

<a href="..\d3d10umddi\ns-d3d10umddi-d3d11_1ddi_authenticated_protection_flags.md">D3D11_1DDI_AUTHENTICATED_PROTECTION_FLAGS</a>

<a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d11_1ddi_configureauthenticatedchannel.md">ConfigureAuthenticatedChannel(D3D11_1)</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20D3D11_1DDI_AUTHENTICATED_CONFIGURE_PROTECTION structure%20 RELEASE:%20(12/29/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

