---
UID: NS:d3dkmthk._D3DKMT_CONFIGURESHAREDRESOURCE
title: "_D3DKMT_CONFIGURESHAREDRESOURCE"
author: windows-driver-content
description: The D3DKMT_CONFIGURESHAREDRESOURCE structure describes parameters that the D3DKMTConfigureSharedResource function uses to configure a shared resource.
old-location: display\d3dkmt_configuresharedresource.htm
ms.assetid: ba190f01-428a-4574-8032-c800ce19ba3e
ms.date: 05/10/2018
ms.keywords: D3DKMT_CONFIGURESHAREDRESOURCE, D3DKMT_CONFIGURESHAREDRESOURCE structure [Display Devices], OpenGL_Structs_ae687fae-f425-4a9b-8426-ee3cc02c8170.xml, _D3DKMT_CONFIGURESHAREDRESOURCE, d3dkmthk/D3DKMT_CONFIGURESHAREDRESOURCE, display.d3dkmt_configuresharedresource
ms.topic: struct
req.header: d3dkmthk.h
req.include-header: D3dkmthk.h
req.target-type: Windows
req.target-min-winverclnt: D3DKMT_CONFIGURESHAREDRESOURCE is supported beginning with the Windows 7 operating system.
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	d3dkmthk.h
api_name:
-	D3DKMT_CONFIGURESHAREDRESOURCE
product:
- Windows
targetos: Windows
tech.root: display
req.typenames: D3DKMT_CONFIGURESHAREDRESOURCE
---

# _D3DKMT_CONFIGURESHAREDRESOURCE structure


## -description


The D3DKMT_CONFIGURESHAREDRESOURCE structure describes parameters that the <a href="https://msdn.microsoft.com/library/windows/hardware/ff546798">D3DKMTConfigureSharedResource</a> function uses to configure a shared resource. 


## -struct-fields




### -field hDevice

[in] A handle to the device that the resource is associated with. 


### -field hResource

[in] A D3DKMT_HANDLE data type that represents a kernel-mode handle to the shared resource to configure. 


### -field IsDwm

[in] A Boolean value that specifies whether the current process is the Desktop Windows Manager (DWM). <b>TRUE</b> indicates DWM; <b>FALSE</b> indicates that the current process is non-DWM and is specified by the <b>hProcess</b> member. 


### -field hProcess

[in] A handle to the process for the non-DWM situation. 


### -field AllowAccess

[in] A Boolean value that specifies whether the <a href="https://msdn.microsoft.com/library/windows/hardware/ff546798">D3DKMTConfigureSharedResource</a> function should allow the process to access the resource. <b>TRUE</b> indicates to allow access; <b>FALSE</b> indicates to not allow access. 


## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff546798">D3DKMTConfigureSharedResource</a>
 

 

