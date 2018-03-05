---
UID: NC:d3d10umddi.PFND3D11_1DDI_CALCPRIVATECRYPTOSESSIONSIZE
title: PFND3D11_1DDI_CALCPRIVATECRYPTOSESSIONSIZE
author: windows-driver-content
description: Returns the number of bytes that the driver requires to store private data for the cryptographic session state.
old-location: display\calcprivatecryptosessionsize.htm
old-project: display
ms.assetid: 9ca0fdd5-a724-4d5d-81b2-8885b2aed1ca
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: CalcPrivateCryptoSessionSize, CalcPrivateCryptoSessionSize callback function [Display Devices], PFND3D11_1DDI_CALCPRIVATECRYPTOSESSIONSIZE, d3d10umddi/CalcPrivateCryptoSessionSize, display.calcprivatecryptosessionsize
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: d3d10umddi.h
req.include-header: D3d10umddi.h
req.target-type: Desktop
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
-	UserDefined
api_location:
-	D3d10umddi.h
api_name:
-	CalcPrivateCryptoSessionSize
product: Windows
targetos: Windows
req.typenames: SETRESULT_INFO, *PSETRESULT_INFO
---

# PFND3D11_1DDI_CALCPRIVATECRYPTOSESSIONSIZE callback


## -description


Returns the number of bytes that the driver requires to store private data for the cryptographic session state.


## -prototype


````
PFND3D11_1DDI_CALCPRIVATECRYPTOSESSIONSIZE CalcPrivateCryptoSessionSize;

SIZE_T APIENTRY* CalcPrivateCryptoSessionSize(
  _In_       D3D10DDI_HDEVICE                  hDevice,
  _In_ const D3D11_1DDIARG_CREATECRYPTOSESSION *pCreateData
)
{ ... }
````


## -parameters




### -param hDevice [in]

A handle to the display device (graphics context).




### -param *pCreateData [in]

A pointer to a <a href="..\d3d10umddi\ns-d3d10umddi-d3d11_1ddiarg_createcryptosession.md">D3D11_1DDIARG_CREATECRYPTOSESSION</a> structure that describes the cryptographic session.


## -returns



The required number of bytes for the cryptographic session state.




## -remarks



The runtime will validate the members of the <a href="..\d3d10umddi\ns-d3d10umddi-d3d11_1ddiarg_createcryptosession.md">D3D11_1DDIARG_CREATECRYPTOSESSION</a> structure before it calls this function.

This function is not expected to fail.




## -see-also

<a href="..\d3d10umddi\ns-d3d10umddi-d3d11_1ddiarg_createcryptosession.md">D3D11_1DDIARG_CREATECRYPTOSESSION</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20PFND3D11_1DDI_CALCPRIVATECRYPTOSESSIONSIZE callback function%20 RELEASE:%20(2/26/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

