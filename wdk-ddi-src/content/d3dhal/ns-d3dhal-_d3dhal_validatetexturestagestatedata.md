---
UID: NS:d3dhal._D3DHAL_VALIDATETEXTURESTAGESTATEDATA
title: "_D3DHAL_VALIDATETEXTURESTAGESTATEDATA"
author: windows-driver-content
description: The D3DHAL_VALIDATETEXTURESTAGESTATEDATA structure contains the information required for the driver to determine and return its ability to support multitexturing using the current state.
old-location: display\d3dhal_validatetexturestagestatedata.htm
old-project: display
ms.assetid: 25534f3b-5da8-47e0-a956-6d1849c40a3d
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: D3DHAL_VALIDATETEXTURESTAGESTATEDATA structure [Display Devices], _D3DHAL_VALIDATETEXTURESTAGESTATEDATA, display.d3dhal_validatetexturestagestatedata, d3dhal/D3DHAL_VALIDATETEXTURESTAGESTATEDATA, d3dhal/LPD3DHAL_VALIDATETEXTURESTAGESTATEDATA, LPD3DHAL_VALIDATETEXTURESTAGESTATEDATA, *LPD3DHAL_VALIDATETEXTURESTAGESTATEDATA, d3dstrct_1f23a380-4c92-44c1-a2ae-7e0558fad221.xml, D3DHAL_VALIDATETEXTURESTAGESTATEDATA, LPD3DHAL_VALIDATETEXTURESTAGESTATEDATA structure pointer [Display Devices]
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: d3dhal.h
req.include-header: D3dhal.h
req.target-type: Windows
req.target-min-winverclnt: 
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
-	d3dhal.h
apiname:
-	D3DHAL_VALIDATETEXTURESTAGESTATEDATA
product: Windows
targetos: Windows
req.typenames: D3DHAL_VALIDATETEXTURESTAGESTATEDATA
---

# _D3DHAL_VALIDATETEXTURESTAGESTATEDATA structure


## -description


The D3DHAL_VALIDATETEXTURESTAGESTATEDATA structure contains the information required for the driver to determine and return its ability to support multitexturing using the current state.


## -syntax


````
typedef struct _D3DHAL_VALIDATETEXTURESTAGESTATEDATA {
  ULONG_PTR dwhContext;
  DWORD     dwFlags;
  ULONG_PTR dwReserved;
  DWORD     dwNumPasses;
  HRESULT   ddrval;
} D3DHAL_VALIDATETEXTURESTAGESTATEDATA, *LPD3DHAL_VALIDATETEXTURESTAGESTATEDATA;
````


## -struct-fields




### -field dwhContext

Specifies the context ID of the Direct3D device.


### -field dwFlags

Currently set to zero and should be ignored by the driver.


### -field dwReserved

Reserved for system use and should be ignored by the driver.


### -field dwNumPasses

Specifies the location where the driver should write the number of passes required by the hardware to perform the blending operations.


### -field ddrval

Specifies the location where the driver writes the return value of the <a href="https://msdn.microsoft.com/library/windows/hardware/ff549064">D3dValidateTextureStageState</a> function. A return code of D3D_OK indicates success. For more information, see <a href="https://msdn.microsoft.com/033beb6e-5872-4cb3-8f39-459e2fff82cd">Return Codes for Direct3D Driver Callbacks</a>.


## -see-also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff549064">D3dValidateTextureStageState</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20D3DHAL_VALIDATETEXTURESTAGESTATEDATA structure%20 RELEASE:%20(12/29/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

