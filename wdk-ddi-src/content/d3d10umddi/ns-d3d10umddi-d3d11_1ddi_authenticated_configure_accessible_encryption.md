---
UID: NS:d3d10umddi.D3D11_1DDI_AUTHENTICATED_CONFIGURE_ACCESSIBLE_ENCRYPTION
title: D3D11_1DDI_AUTHENTICATED_CONFIGURE_ACCESSIBLE_ENCRYPTION
author: windows-driver-content
description: Contains input data for a call to the ConfigureAuthenticatedChannel(D3D11_1) function when D3D11_1DDI_AUTHENTICATED_CONFIGURE_INPUT.ConfigureType has a GUID value of D3D11_1DDI_AUTHENTICATED_CONFIGURE_SHARED_RESOURCE.
old-location: display\d3d11_1ddi_authenticated_configure_accessible_encryption.htm
old-project: display
ms.assetid: 07a2508e-fa0e-489c-8f27-7f5d09919fb4
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: D3D11_1DDI_AUTHENTICATED_CONFIGURE_ACCESSIBLE_ENCRYPTION, D3D11_1DDI_AUTHENTICATED_CONFIGURE_ACCESSIBLE_ENCRYPTION structure [Display Devices], d3d10umddi/D3D11_1DDI_AUTHENTICATED_CONFIGURE_ACCESSIBLE_ENCRYPTION, display.d3d11_1ddi_authenticated_configure_accessible_encryption
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
-	D3D11_1DDI_AUTHENTICATED_CONFIGURE_ACCESSIBLE_ENCRYPTION
product: Windows
targetos: Windows
req.typenames: D3D11_1DDI_AUTHENTICATED_CONFIGURE_ACCESSIBLE_ENCRYPTION
---

# D3D11_1DDI_AUTHENTICATED_CONFIGURE_ACCESSIBLE_ENCRYPTION structure


## -description


Contains input data for a call to the <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d11_1ddi_configureauthenticatedchannel.md">ConfigureAuthenticatedChannel(D3D11_1)</a> function when <a href="..\d3d10umddi\ns-d3d10umddi-d3d11_1ddi_authenticated_configure_input.md">D3D11_1DDI_AUTHENTICATED_CONFIGURE_INPUT</a>.<b>ConfigureType</b> has a GUID value of <b>D3D11_1DDI_AUTHENTICATED_CONFIGURE_SHARED_RESOURCE</b>.


## -syntax


````
typedef struct D3D11_1DDI_AUTHENTICATED_CONFIGURE_ACCESSIBLE_ENCRYPTION {
  D3D11_1DDI_AUTHENTICATED_CONFIGURE_INPUT Parameters;
  GUID                                     EncryptionGuid;
} D3D11_1DDI_AUTHENTICATED_CONFIGURE_ACCESSIBLE_ENCRYPTION;
````


## -struct-fields




### -field Parameters

A <a href="..\d3d10umddi\ns-d3d10umddi-d3d11_1ddi_authenticated_configure_input.md">D3D11_1DDI_AUTHENTICATED_CONFIGURE_INPUT</a> structure that contains the command GUID and other data.


### -field EncryptionGuid

A GUID that specifies the type of encryption to apply.


## -see-also

<a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d11_1ddi_configureauthenticatedchannel.md">ConfigureAuthenticatedChannel(D3D11_1)</a>



<a href="..\d3d10umddi\ns-d3d10umddi-d3d11_1ddi_authenticated_configure_input.md">D3D11_1DDI_AUTHENTICATED_CONFIGURE_INPUT</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20D3D11_1DDI_AUTHENTICATED_CONFIGURE_ACCESSIBLE_ENCRYPTION structure%20 RELEASE:%20(2/26/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

