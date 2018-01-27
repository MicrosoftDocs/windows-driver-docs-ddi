---
UID: NS:d3dkmddi._DXGKARG_CREATEPROCESS
title: _DXGKARG_CREATEPROCESS
author: windows-driver-content
description: DXGKARG_CREATEPROCESS is used with DxgkDdiCreateProcess to create a kernel mode driver object for a Microsoft DirectX graphics kernel process object.
old-location: display\dxgkarg_createprocess.htm
old-project: display
ms.assetid: F4FDF254-1C36-43DC-B1FD-376AD7658E61
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: *INOUT_PDXGKARG_CREATEPROCESS, d3dkmddi/DXGKARG_CREATEPROCESS, _DXGKARG_CREATEPROCESS, DXGKARG_CREATEPROCESS structure [Display Devices], DXGKARG_CREATEPROCESS, display.dxgkarg_createprocess
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: d3dkmddi.h
req.include-header: D3dkmddi.h
req.target-type: Windows
req.target-min-winverclnt: Windows 10
req.target-min-winversvr: Windows Server 2016
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
req.irql: PASSIVE_LEVEL
topictype: 
-	APIRef
-	kbSyntax
apitype: 
-	HeaderDef
apilocation: 
-	d3dkmddi.h
apiname: 
-	DXGKARG_CREATEPROCESS
product: Windows
targetos: Windows
req.typenames: DXGKARG_CREATEPROCESS
---

# _DXGKARG_CREATEPROCESS structure


## -description


<b>DXGKARG_CREATEPROCESS</b> is used with <a href="..\d3dkmddi\nc-d3dkmddi-dxgkddi_createprocess.md">DxgkDdiCreateProcess</a> to create a kernel mode driver object for a Microsoft DirectX graphics kernel process object.


## -syntax


````
typedef struct _DXGKARG_CREATEPROCESS {
  HANDLE                  hDxgkProcess;
  HANDLE                  hKmdProcess;
  DXGK_CREATEPROCESSFLAGS Flags;
  UINT                    NumPasid;
  ULONG*                  pPasid;
} DXGKARG_CREATEPROCESS;
````


## -struct-fields




### -field hDxgkProcess

[in] The handle to the DirectX graphics kernel process.


### -field hKmdProcess

[out] The handle to the kernel mode driver process.


### -field Flags

[in] A <a href="..\d3dkmddi\ns-d3dkmddi-_dxgk_createprocessflags.md">DXGK_CREATEPROCESSFLAGS</a> structure describing the operation.


### -field NumPasid

[in] The number of elements in the process address space identifier array located in the <b>pPasid</b>  member. 


### -field pPasid

[in] A pointer to an array of process address identifiers. There will be one for each physical GPUs.


## -see-also

<a href="..\d3dkmddi\nc-d3dkmddi-dxgkddi_createprocess.md">DxgkDdiCreateProcess</a>

<a href="..\d3dkmddi\ns-d3dkmddi-_dxgk_createprocessflags.md">DXGK_CREATEPROCESSFLAGS</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20DXGKARG_CREATEPROCESS structure%20 RELEASE:%20(12/29/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

