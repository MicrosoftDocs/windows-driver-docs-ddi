---
UID: NS:d3d10umddi.D3D11_1DDI_VIDEO_CONTENT_PROTECTION_CAPS
title: D3D11_1DDI_VIDEO_CONTENT_PROTECTION_CAPS
author: windows-driver-content
description: Describes the content-protection capabilities of the user-mode display driver.
old-location: display\d3d11_1ddi_video_content_protection_caps.htm
old-project: display
ms.assetid: 31ff5dfc-72b1-4ce1-af83-cad3816a785c
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: D3D11_1DDI_VIDEO_CONTENT_PROTECTION_CAPS, display.d3d11_1ddi_video_content_protection_caps, D3D11_1DDI_VIDEO_CONTENT_PROTECTION_CAPS structure [Display Devices], d3d10umddi/D3D11_1DDI_VIDEO_CONTENT_PROTECTION_CAPS
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
-	D3D11_1DDI_VIDEO_CONTENT_PROTECTION_CAPS
product: Windows
targetos: Windows
req.typenames: D3D11_1DDI_VIDEO_CONTENT_PROTECTION_CAPS
---

# D3D11_1DDI_VIDEO_CONTENT_PROTECTION_CAPS structure


## -description


Describes the content-protection capabilities of the user-mode display driver.


## -syntax


````
typedef struct D3D11_1DDI_VIDEO_CONTENT_PROTECTION_CAPS {
  UINT      Caps;
  UINT      KeyExchangeTypeCount;
  UINT      BlockAlignmentSize;
  ULONGLONG ProtectedMemorySize;
} D3D11_1DDI_VIDEO_CONTENT_PROTECTION_CAPS;
````


## -struct-fields




### -field Caps

A bitwise <b>OR</b> of zero or more flags from the <a href="..\d3d10umddi\ne-d3d10umddi-d3d11_1ddi_content_protection_caps.md">D3D11_1DDI_CONTENT_PROTECTION_CAPS</a> enumeration.


### -field KeyExchangeTypeCount

The number of cryptographic key-exchange types that are supported by the driver. To get the list of key-exchange types, call the <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d11_1ddi_getcryptokeyexchangetype.md">GetCryptoKeyExchangeType</a> function.


### -field BlockAlignmentSize

The encyrption block size, in bytes. The size of data to be encrypted must be a multiple of this value.


### -field ProtectedMemorySize

The total amount of memory, in bytes, that can be used to hold protected surfaces.


## -see-also

<a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d11_1ddi_getcryptokeyexchangetype.md">GetCryptoKeyExchangeType</a>

<a href="..\d3d10umddi\ne-d3d10umddi-d3d11_1ddi_content_protection_caps.md">D3D11_1DDI_CONTENT_PROTECTION_CAPS</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20D3D11_1DDI_VIDEO_CONTENT_PROTECTION_CAPS structure%20 RELEASE:%20(12/29/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

