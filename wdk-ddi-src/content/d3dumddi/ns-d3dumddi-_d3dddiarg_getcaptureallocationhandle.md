---
UID: NS:d3dumddi._D3DDDIARG_GETCAPTUREALLOCATIONHANDLE
title: "_D3DDDIARG_GETCAPTUREALLOCATIONHANDLE"
author: windows-driver-content
description: The D3DDDIARG_GETCAPTUREALLOCATIONHANDLE structure describes the parameters for retrieving an allocation handle from a capture resource handle.
old-location: display\d3dddiarg_getcaptureallocationhandle.htm
old-project: display
ms.assetid: 588ebf7a-db83-4eb8-8403-04b215bed12b
ms.author: windowsdriverdev
ms.date: 2/24/2018
ms.keywords: ",  , ,, 3, A, C, D, D3DDDIARG_GETCAPTUREALLOCATIONHANDLE, D3DDDIARG_GETCAPTUREALLOCATIONHANDLE structure [Display Devices], E, G, H, I, L, N, O, P, R, T, U, UMDisplayDriver_param_Structs_8fece49c-e3e6-4683-b4af-517da6f73cc7.xml, _, _D3DDDIARG_GETCAPTUREALLOCATIONHANDLE, d3dumddi/D3DDDIARG_GETCAPTUREALLOCATIONHANDLE, display.d3dddiarg_getcaptureallocationhandle"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: d3dumddi.h
req.include-header: D3dumddi.h
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
req.irql: 
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	d3dumddi.h
apiname:
-	D3DDDIARG_GETCAPTUREALLOCATIONHANDLE
product: Windows
targetos: Windows
req.typenames: D3DDDIARG_GETCAPTUREALLOCATIONHANDLE
---

# _D3DDDIARG_GETCAPTUREALLOCATIONHANDLE structure


## -description


The D3DDDIARG_GETCAPTUREALLOCATIONHANDLE structure describes the parameters for retrieving an allocation handle from a capture resource handle. 


## -syntax


````
typedef struct _D3DDDIARG_GETCAPTUREALLOCATIONHANDLE {
  HANDLE        hResource;
  D3DKMT_HANDLE hAllocation;
} D3DDDIARG_GETCAPTUREALLOCATIONHANDLE;
````


## -struct-fields




### -field hResource

[in] A handle to the capture resource that <a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_getcaptureallocationhandle.md">GetCaptureAllocationHandle</a> retrieves the allocation handle for.


### -field hAllocation

[out] A D3DKMT_HANDLE data type that represents a kernel-mode handle to the allocation that is associated with the resource that <b>hResource</b> specifies.


## -see-also

<a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_getcaptureallocationhandle.md">GetCaptureAllocationHandle</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20D3DDDIARG_GETCAPTUREALLOCATIONHANDLE structure%20 RELEASE:%20(2/24/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

