---
UID: NS:d3dkmthk._D3DKMT_CONFIGURESHAREDRESOURCE
title: _D3DKMT_CONFIGURESHAREDRESOURCE
author: windows-driver-content
description: The D3DKMT_CONFIGURESHAREDRESOURCE structure describes parameters that the D3DKMTConfigureSharedResource function uses to configure a shared resource.
old-location: display\d3dkmt_configuresharedresource.htm
old-project: display
ms.assetid: ba190f01-428a-4574-8032-c800ce19ba3e
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: _D3DKMT_CONFIGURESHAREDRESOURCE, D3DKMT_CONFIGURESHAREDRESOURCE
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: d3dkmthk.h
req.include-header: D3dkmthk.h
req.target-type: Windows
req.target-min-winverclnt: D3DKMT_CONFIGURESHAREDRESOURCE is supported beginning with the Windows 7 operating system.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: D3DKMT_CONFIGURESHAREDRESOURCE
req.alt-loc: d3dkmthk.h
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
req.typenames: D3DKMT_CONFIGURESHAREDRESOURCE
---

# _D3DKMT_CONFIGURESHAREDRESOURCE structure



## -description
The D3DKMT_CONFIGURESHAREDRESOURCE structure describes parameters that the <a href="..\d3dkmthk\nf-d3dkmthk-d3dkmtconfiguresharedresource.md">D3DKMTConfigureSharedResource</a> function uses to configure a shared resource. 



## -syntax

````
typedef struct _D3DKMT_CONFIGURESHAREDRESOURCE {
  D3DKMT_HANDLE hDevice;
  D3DKMT_HANDLE hResource;
  BOOLEAN       IsDwm;
  HANDLE        hProcess;
  BOOLEAN       AllowAccess;
} D3DKMT_CONFIGURESHAREDRESOURCE;
````


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

[in] A Boolean value that specifies whether the <a href="..\d3dkmthk\nf-d3dkmthk-d3dkmtconfiguresharedresource.md">D3DKMTConfigureSharedResource</a> function should allow the process to access the resource. <b>TRUE</b> indicates to allow access; <b>FALSE</b> indicates to not allow access. 


## -remarks


## -see-also
<dl>
<dt>
<a href="..\d3dkmthk\nf-d3dkmthk-d3dkmtconfiguresharedresource.md">D3DKMTConfigureSharedResource</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20D3DKMT_CONFIGURESHAREDRESOURCE structure%20 RELEASE:%20(12/29/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

