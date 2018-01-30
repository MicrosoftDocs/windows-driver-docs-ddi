---
UID: NS:d3dumddi.D3DDDICAPS_SIMPLE_INSTANCING_SUPPORT
title: D3DDDICAPS_SIMPLE_INSTANCING_SUPPORT
author: windows-driver-content
description: Describes whether simple instancing is supported.
old-location: display\d3dddicaps_simple_instancing_support.htm
old-project: display
ms.assetid: CF75EBC8-D756-49B5-BC1F-1DBE8DC04137
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: display.d3dddicaps_simple_instancing_support, d3dumddi/D3DDDICAPS_SIMPLE_INSTANCING_SUPPORT, D3DDDICAPS_SIMPLE_INSTANCING_SUPPORT, D3DDDICAPS_SIMPLE_INSTANCING_SUPPORT structure [Display Devices]
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: d3dumddi.h
req.include-header: D3d10umddi.h
req.target-type: Windows
req.target-min-winverclnt: Windows 8.1
req.target-min-winversvr: Windows Server 2012 R2
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
-	D3dumddi.h
apiname:
-	D3DDDICAPS_SIMPLE_INSTANCING_SUPPORT
product: Windows
targetos: Windows
req.typenames: D3DDDICAPS_SIMPLE_INSTANCING_SUPPORT
---

# D3DDDICAPS_SIMPLE_INSTANCING_SUPPORT structure


## -description


Describes whether simple instancing is supported.


## -syntax


````
typedef struct D3DDDICAPS_SIMPLE_INSTANCING_SUPPORT {
  BOOL SimpleInstancingSupported;
} D3DDDICAPS_SIMPLE_INSTANCING_SUPPORT;
````


## -struct-fields




### -field SimpleInstancingSupported

Specifies whether the hardware and the user-mode driver support simple instancing. The Direct3D runtime sets this member to <b>TRUE</b> if the hardware and driver support simple instancing and the driver is a Direct3D Level 9 driver and supports Windows Display Driver Model (WDDM) 1.3 and later. Otherwise this member is <b>FALSE</b>.

Used only by Direct3D Level 9 drivers that support WDDM 1.3 and later.

Supported starting with Windows 8.1.


## -remarks


Instancing capabilities are exposed through the <b>D3DDDICAPS_GET_SIMPLE_INSTANCING_SUPPORT</b> constant value of the <a href="..\d3dumddi\ne-d3dumddi-_d3dddicaps_type.md">D3DDDICAPS_TYPE</a> enumeration.

For more info on simple instancing, see The Microsoft Direct3D 11 topic, <a href="https://msdn.microsoft.com/940381BB-E8F6-416D-8F36-CC3591E70703">D3D11_FEATURE_DATA_D3D9_SIMPLE_INSTANCING_SUPPORT</a>.



## -see-also

<a href="https://msdn.microsoft.com/940381BB-E8F6-416D-8F36-CC3591E70703">D3D11_FEATURE_DATA_D3D9_SIMPLE_INSTANCING_SUPPORT</a>

<a href="..\d3dumddi\ne-d3dumddi-_d3dddicaps_type.md">D3DDDICAPS_TYPE</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20D3DDDICAPS_SIMPLE_INSTANCING_SUPPORT structure%20 RELEASE:%20(12/29/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

