---
UID: NS:d3dkmthk._D3DKMT_CHECKSHAREDRESOURCEACCESS
title: "_D3DKMT_CHECKSHAREDRESOURCEACCESS"
author: windows-driver-content
description: The D3DKMT_CHECKSHAREDRESOURCEACCESS structure describes parameters that the D3DKMTCheckSharedResourceAccess function uses to determine if a process can access a shared resource.
old-location: display\d3dkmt_checksharedresourceaccess.htm
old-project: display
ms.assetid: 1749127f-c5fc-4e69-a2dd-00540e1c4c9a
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: "_D3DKMT_CHECKSHAREDRESOURCEACCESS, d3dkmthk/D3DKMT_CHECKSHAREDRESOURCEACCESS, D3DKMT_CHECKSHAREDRESOURCEACCESS, D3DKMT_CHECKSHAREDRESOURCEACCESS structure [Display Devices], OpenGL_Structs_5d797cef-2ace-482b-a7b2-82b26a2c7504.xml, display.d3dkmt_checksharedresourceaccess"
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	d3dkmthk.h
apiname:
-	D3DKMT_CHECKSHAREDRESOURCEACCESS
product: Windows
targetos: Windows
req.typenames: D3DKMT_CHECKSHAREDRESOURCEACCESS
---

# _D3DKMT_CHECKSHAREDRESOURCEACCESS structure


## -description


The D3DKMT_CHECKSHAREDRESOURCEACCESS structure describes parameters that the <a href="..\d3dkmthk\nf-d3dkmthk-d3dkmtchecksharedresourceaccess.md">D3DKMTCheckSharedResourceAccess</a> function uses to determine if a process can access a shared resource. 


## -syntax


````
typedef struct _D3DKMT_CHECKSHAREDRESOURCEACCESS {
  D3DKMT_HANDLE hResource;
  UINT          ClientPid;
} D3DKMT_CHECKSHAREDRESOURCEACCESS;
````


## -struct-fields




### -field hResource

[in] A D3DKMT_HANDLE data type that represents a kernel-mode handle to the shared resource to check. 


### -field ClientPid

[in] A UINT value that represents the process identifier (PID) for the client process that requires access to the shared resource that the <b>hProcess</b> member specifies. 


## -see-also

<a href="..\d3dkmthk\nf-d3dkmthk-d3dkmtchecksharedresourceaccess.md">D3DKMTCheckSharedResourceAccess</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20D3DKMT_CHECKSHAREDRESOURCEACCESS structure%20 RELEASE:%20(12/29/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

