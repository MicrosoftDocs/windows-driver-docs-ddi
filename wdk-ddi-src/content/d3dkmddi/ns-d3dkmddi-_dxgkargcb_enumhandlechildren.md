---
UID: NS:d3dkmddi._DXGKARGCB_ENUMHANDLECHILDREN
title: "_DXGKARGCB_ENUMHANDLECHILDREN"
author: windows-driver-content
description: The DXGKARGCB_ENUMHANDLECHILDREN structure describes a parent resource and the index of one of its child allocations.
old-location: display\dxgkargcb_enumhandlechildren.htm
old-project: display
ms.assetid: da97b175-a24c-406d-9747-c84122781f79
ms.author: windowsdriverdev
ms.date: 2/24/2018
ms.keywords: DXGKARGCB_ENUMHANDLECHILDREN, DXGKARGCB_ENUMHANDLECHILDREN structure [Display Devices], DmStructs_b02ec187-32ca-41ff-bfc3-03d058872b5d.xml, _DXGKARGCB_ENUMHANDLECHILDREN, d3dkmddi/DXGKARGCB_ENUMHANDLECHILDREN, display.dxgkargcb_enumhandlechildren
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: d3dkmddi.h
req.include-header: D3dkmddi.h
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
req.irql: PASSIVE_LEVEL
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	d3dkmddi.h
apiname:
-	DXGKARGCB_ENUMHANDLECHILDREN
product: Windows
targetos: Windows
req.typenames: DXGKARGCB_ENUMHANDLECHILDREN
---

# _DXGKARGCB_ENUMHANDLECHILDREN structure


## -description


The DXGKARGCB_ENUMHANDLECHILDREN structure describes a parent resource and the index of one of its child allocations. 


## -syntax


````
typedef struct _DXGKARGCB_ENUMHANDLECHILDREN {
  D3DKMT_HANDLE hObject;
  UINT          Index;
} DXGKARGCB_ENUMHANDLECHILDREN;
````


## -struct-fields




### -field hObject

[in] A handle to the parent resource of a group of child allocations. This handle is the kernel-mode handle that the Microsoft DirectX graphics kernel subsystem (which is part of <i>Dxgkrnl.sys</i>) assigned for the parent resource.


### -field Index

[in] The index into the array of allocations that belongs to the resource that <b>hObject</b> specifies.


## -see-also

<a href="..\d3dkmddi\nc-d3dkmddi-dxgkcb_enumhandlechildren.md">DxgkCbEnumHandleChildren</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20DXGKARGCB_ENUMHANDLECHILDREN structure%20 RELEASE:%20(2/24/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

