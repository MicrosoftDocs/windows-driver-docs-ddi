---
UID: NC:d3dumddi.PFND3DDDI_QUERYDLISTFORAPPLICATION1
title: PFND3DDDI_QUERYDLISTFORAPPLICATION1
author: windows-driver-content
description: Called during Microsoft Direct3D initialization on a hybrid system to determine which GPU an application should run on. A dList is a list of applications that need cross-adapter shared surfaces for high-performance rendering on the discrete GPU.
old-location: display\querydlistforapplication1.htm
old-project: display
ms.assetid: 4F27E884-D21C-483D-9E53-02D405D02F10
ms.author: windowsdriverdev
ms.date: 2/24/2018
ms.keywords: PFND3DDDI_QUERYDLISTFORAPPLICATION1, QueryDListForApplication, QueryDListForApplication callback function [Display Devices], d3dumddi/QueryDListForApplication, display.querydlistforapplication1
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: d3dumddi.h
req.include-header: D3d10umddi.h
req.target-type: Desktop
req.target-min-winverclnt: Windows 8.1,WDDM 1.3 and later
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
-	UserDefined
apilocation:
-	D3dumddi.h
apiname:
-	QueryDListForApplication
product: Windows
targetos: Windows
req.typenames: DXGK_PTE
---

# PFND3DDDI_QUERYDLISTFORAPPLICATION1 callback


## -description


Called during Microsoft Direct3D initialization on a <a href="https://msdn.microsoft.com/ECBB0AA7-50C2-41C8-9DC6-6EEFC5CEEB15">hybrid system</a> to determine which GPU an application should run on. A <i>dList</i> is a list of applications that need cross-adapter shared surfaces for high-performance rendering on the discrete GPU.


## -prototype


````
PFND3DDDI_QUERYDLISTFORAPPLICATION1 QueryDListForApplication;

HRESULT APIENTRY* QueryDListForApplication(
  _Out_ BOOL               *pDefaultToDiscrete,
  _In_  HANDLE             hAdapter,
  _In_  PFND3DDDI_ESCAPECB pfnEscapeCB
)
{ ... }
````


## -parameters




### -param *


### -param HANDLE


### -param PFND3DDDI_ESCAPECB








#### - hAdapter [in]

A handle to the graphics adapter object.


#### - pDefaultToDiscrete [out]

If <b>TRUE</b>, the application should be run on the discrete GPU. Otherwise, the application should run on the integrated GPU.


#### - pfnEscapeCB [in]

A function pointer to a <a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_escapecb.md">pfnEscapeCb</a> callback function that shares info with the display miniport driver.


## -returns



Returns <b>S_OK</b>, or an appropriate error result if the operation is not successful.




## -remarks



For more information on how to call this function and set up the DLL that exports it, see <a href="https://msdn.microsoft.com/8AABE677-2C2D-4CFD-AF22-06D65524A158">Hybrid system DDI</a>.

For more general information on hybrid systems, see <a href="https://msdn.microsoft.com/ECBB0AA7-50C2-41C8-9DC6-6EEFC5CEEB15">Using cross-adapter resources in a hybrid system</a>.




## -see-also

<a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_escapecb.md">pfnEscapeCb</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20PFND3DDDI_QUERYDLISTFORAPPLICATION1 callback function%20 RELEASE:%20(2/24/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

