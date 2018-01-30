---
UID: NS:dxgitype.DXGI_GAMMA_CONTROL_CAPABILITIES
title: DXGI_GAMMA_CONTROL_CAPABILITIES
author: windows-driver-content
description: The DXGI_GAMMA_CONTROL_CAPABILIITES structure describes gamma capabilities.
old-location: display\dxgi_gamma_control_capabiliites.htm
old-project: display
ms.assetid: 7a91311e-c8b9-4f28-b72e-9f93d459aac2
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: DXGI_GAMMA_CONTROL_CAPABILITIES, DXGI_GAMMA_CONTROL_CAPABILIITES structure [Display Devices], display.dxgi_gamma_control_capabiliites, DXGI_GAMMA_CONTROL_CAPABILIITES, UMDisplayDriver_Dx10param_Structs_002eb4f0-081a-43df-a307-e979017daf6f.xml, DXGI_GAMMA_CONTROL_CAPABILITIES structure [Display Devices], dxgitype/DXGI_GAMMA_CONTROL_CAPABILIITES
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: dxgitype.h
req.include-header: D3d10umddi.h
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
-	Dxgitype.h
apiname:
-	DXGI_GAMMA_CONTROL_CAPABILITIES
product: Windows
targetos: Windows
req.typenames: DXGI_GAMMA_CONTROL_CAPABILITIES
---

# DXGI_GAMMA_CONTROL_CAPABILITIES structure


## -description


The DXGI_GAMMA_CONTROL_CAPABILIITES structure describes gamma capabilities. 


## -syntax


````
typedef struct DXGI_GAMMA_CONTROL_CAPABILIITES {
  BOOL  ScaleAndOffsetSupported;
  float MaxConvertedValue;
  float MinConvertedValue;
  UINT  NumGammaControlPoints;
  float ControlPointPositions[1025];
} DXGI_GAMMA_CONTROL_CAPABILITIES;
````


## -struct-fields




### -field ScaleAndOffsetSupported

[out] A BOOL value that indicates whether the device supports scale and offset. <b>TRUE</b> indicates that the device supports scale and offset; <b>FALSE</b> indicates that the device does not support scale and offset. 


### -field MaxConvertedValue

[out] A single-precision float vector for the maximum converted value for the gamma control. 


### -field MinConvertedValue

[out] A single-precision float vector for the minimum converted value for the gamma control. 


### -field NumGammaControlPoints

[out] The number of elements in the array that the <b>ControlPointPositions</b> member specifies. 


### -field ControlPointPositions

[out] An array of single-precision float vectors that describe the gamma control point positions. 


## -see-also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff566790">GetGammaCapsDXGI</a>

<a href="..\dxgiddi\ns-dxgiddi-dxgi_ddi_arg_get_gamma_control_caps.md">DXGI_DDI_ARG_GET_GAMMA_CONTROL_CAPS</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20DXGI_GAMMA_CONTROL_CAPABILIITES structure%20 RELEASE:%20(12/29/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

