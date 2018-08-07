---
UID: NS:d3d10umddi.D3D11_1DDI_AUTHENTICATED_CONFIGURE_PROTECTION
title: D3D11_1DDI_AUTHENTICATED_CONFIGURE_PROTECTION
author: windows-driver-content
description: Contains input data for a call to the ConfigureAuthenticatedChannel(D3D11_1) function when D3D11_1DDI_AUTHENTICATED_CONFIGURE_INPUT.ConfigureType has a GUID value of D3D11_AUTHENTICATED_CONFIGURE_PROTECTION.
old-location: display\d3d11_1ddi_authenticated_configure_protection.htm
tech.root: display
ms.assetid: 2932fd35-54dc-4054-99e5-9b33aac77413
ms.author: windowsdriverdev
ms.date: 5/10/2018
ms.keywords: D3D11_1DDI_AUTHENTICATED_CONFIGURE_PROTECTION, D3D11_1DDI_AUTHENTICATED_CONFIGURE_PROTECTION structure [Display Devices], d3d10umddi/D3D11_1DDI_AUTHENTICATED_CONFIGURE_PROTECTION, display.d3d11_1ddi_authenticated_configure_protection
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
-	D3D11_1DDI_AUTHENTICATED_CONFIGURE_PROTECTION
product:
- Windows
targetos: Windows
req.typenames: D3D11_1DDI_AUTHENTICATED_CONFIGURE_PROTECTION
---

# D3D11_1DDI_AUTHENTICATED_CONFIGURE_PROTECTION structure


## -description


Contains input data for a call to the <a href="https://msdn.microsoft.com/28d32813-15f5-4b9c-9bdb-5ad9b47bbe3b">ConfigureAuthenticatedChannel(D3D11_1)</a> function when <a href="https://msdn.microsoft.com/library/windows/hardware/hh406358">D3D11_1DDI_AUTHENTICATED_CONFIGURE_INPUT</a>.<b>ConfigureType</b> has a GUID value of <b>D3D11_AUTHENTICATED_CONFIGURE_PROTECTION</b>.


## -struct-fields




### -field Parameters

A <a href="https://msdn.microsoft.com/library/windows/hardware/hh406358">D3D11_1DDI_AUTHENTICATED_CONFIGURE_INPUT</a> structure that contains the command GUID and other data. 


### -field Protections

A <a href="https://msdn.microsoft.com/library/windows/hardware/hh406375">D3D11_1DDI_AUTHENTICATED_PROTECTION_FLAGS</a> structure that specifies the protection level.




## -see-also




<a href="https://msdn.microsoft.com/28d32813-15f5-4b9c-9bdb-5ad9b47bbe3b">ConfigureAuthenticatedChannel(D3D11_1)</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh406358">D3D11_1DDI_AUTHENTICATED_CONFIGURE_INPUT</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh406375">D3D11_1DDI_AUTHENTICATED_PROTECTION_FLAGS</a>
 

 

