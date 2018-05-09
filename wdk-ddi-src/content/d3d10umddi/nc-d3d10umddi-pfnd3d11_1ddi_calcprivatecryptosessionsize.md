---
UID: NC:d3d10umddi.PFND3D11_1DDI_CALCPRIVATECRYPTOSESSIONSIZE
title: PFND3D11_1DDI_CALCPRIVATECRYPTOSESSIONSIZE
author: windows-driver-content
description: Returns the number of bytes that the driver requires to store private data for the cryptographic session state.
old-location: display\calcprivatecryptosessionsize.htm
old-project: display
ms.assetid: 9ca0fdd5-a724-4d5d-81b2-8885b2aed1ca
ms.author: windowsdriverdev
ms.date: 4/16/2018
ms.keywords: CalcPrivateCryptoSessionSize, CalcPrivateCryptoSessionSize callback function [Display Devices], PFND3D11_1DDI_CALCPRIVATECRYPTOSESSIONSIZE, PFND3D11_1DDI_CALCPRIVATECRYPTOSESSIONSIZE callback, d3d10umddi/CalcPrivateCryptoSessionSize, display.calcprivatecryptosessionsize
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
product:
- Windows
targetos: Windows
req.typenames: 
---

# PFND3D11_1DDI_CALCPRIVATECRYPTOSESSIONSIZE callback function


## -description


Returns the number of bytes that the driver requires to store private data for the cryptographic session state.


## -parameters




### -param hDevice [in]

A handle to the display device (graphics context).




### -param *pCreateData [in]

A pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/hh406308">D3D11_1DDIARG_CREATECRYPTOSESSION</a> structure that describes the cryptographic session.


## -returns



The required number of bytes for the cryptographic session state.




## -remarks



The runtime will validate the members of the <a href="https://msdn.microsoft.com/library/windows/hardware/hh406308">D3D11_1DDIARG_CREATECRYPTOSESSION</a> structure before it calls this function.

This function is not expected to fail.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/hh406308">D3D11_1DDIARG_CREATECRYPTOSESSION</a>
 

 

