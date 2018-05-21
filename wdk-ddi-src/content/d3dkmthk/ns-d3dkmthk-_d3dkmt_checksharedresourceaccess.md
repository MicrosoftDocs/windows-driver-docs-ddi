---
UID: NS:d3dkmthk._D3DKMT_CHECKSHAREDRESOURCEACCESS
title: "_D3DKMT_CHECKSHAREDRESOURCEACCESS"
author: windows-driver-content
description: The D3DKMT_CHECKSHAREDRESOURCEACCESS structure describes parameters that the D3DKMTCheckSharedResourceAccess function uses to determine if a process can access a shared resource.
old-location: display\d3dkmt_checksharedresourceaccess.htm
old-project: display
ms.assetid: 1749127f-c5fc-4e69-a2dd-00540e1c4c9a
ms.author: windowsdriverdev
ms.date: 4/16/2018
ms.keywords: D3DKMT_CHECKSHAREDRESOURCEACCESS, D3DKMT_CHECKSHAREDRESOURCEACCESS structure [Display Devices], OpenGL_Structs_5d797cef-2ace-482b-a7b2-82b26a2c7504.xml, _D3DKMT_CHECKSHAREDRESOURCEACCESS, d3dkmthk/D3DKMT_CHECKSHAREDRESOURCEACCESS, display.d3dkmt_checksharedresourceaccess
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: d3dkmthk.h
req.include-header: D3dkmthk.h
req.target-type: Windows
req.target-min-winverclnt: D3DKMT_CHECKSHAREDRESOURCEACCESS is supported beginning with the Windows 7 operating system.
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
-	D3DKMT_CHECKSHAREDRESOURCEACCESS
product:
- Windows
targetos: Windows
req.typenames: D3DKMT_CHECKSHAREDRESOURCEACCESS
---

# _D3DKMT_CHECKSHAREDRESOURCEACCESS structure


## -description


The D3DKMT_CHECKSHAREDRESOURCEACCESS structure describes parameters that the <a href="https://msdn.microsoft.com/library/windows/hardware/ff546769">D3DKMTCheckSharedResourceAccess</a> function uses to determine if a process can access a shared resource. 


## -struct-fields




### -field hResource

[in] A D3DKMT_HANDLE data type that represents a kernel-mode handle to the shared resource to check. 


### -field ClientPid

[in] A UINT value that represents the process identifier (PID) for the client process that requires access to the shared resource that the <b>hProcess</b> member specifies. 


## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff546769">D3DKMTCheckSharedResourceAccess</a>
 

 

