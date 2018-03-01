---
UID: NS:d3dkmthk._D3DKMT_FREEGPUVIRTUALADDRESS
title: "_D3DKMT_FREEGPUVIRTUALADDRESS"
author: windows-driver-content
description: D3DKMT_FREEGPUVIRTUALADDRESS is used with FreeGpuVirtualAddress to release a range of graphics processing unit (GPU) virtual addresses that were previously reserved or mapped.
old-location: display\d3dkmt_freegpuvirtualaddress.htm
old-project: display
ms.assetid: BB3DD49B-7DAB-48AC-BC63-595A184374AB
ms.author: windowsdriverdev
ms.date: 2/24/2018
ms.keywords: D3DKMT_FREEGPUVIRTUALADDRESS, D3DKMT_FREEGPUVIRTUALADDRESS structure [Display Devices], _D3DKMT_FREEGPUVIRTUALADDRESS, d3dkmthk/D3DKMT_FREEGPUVIRTUALADDRESS, display.d3dkmt_freegpuvirtualaddress
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: d3dkmthk.h
req.include-header: D3dkmthk.h
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
req.irql: 
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	d3dkmthk.h
api_name:
-	D3DKMT_FREEGPUVIRTUALADDRESS
product: Windows
targetos: Windows
req.typenames: D3DKMT_FREEGPUVIRTUALADDRESS
---

# _D3DKMT_FREEGPUVIRTUALADDRESS structure


## -description


<b>D3DKMT_FREEGPUVIRTUALADDRESS</b> is used with <a href="..\d3dkmthk\nf-d3dkmthk-d3dkmtfreegpuvirtualaddress.md">FreeGpuVirtualAddress</a> to release a range of graphics processing unit (GPU) virtual addresses that were previously reserved or mapped.


## -syntax


````
typedef struct _D3DKMT_FREEGPUVIRTUALADDRESS {
  D3DKMT_HANDLE          hAdapter;
  D3DGPU_VIRTUAL_ADDRESS BaseAddress;
  D3DGPU_SIZE_T          Size;
} D3DKMT_FREEGPUVIRTUALADDRESS;
````


## -struct-fields




### -field hAdapter

Specifies the handle to the adapter.


### -field BaseAddress

Specifies the base virtual address, in bytes, of the range to free. Must be aligned to 4 KB.


### -field Size

Specifies the size, in bytes, of the range to free. Must be aligned to 4 KB.


## -see-also

<a href="..\d3dkmthk\nf-d3dkmthk-d3dkmtfreegpuvirtualaddress.md">FreeGpuVirtualAddress</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20D3DKMT_FREEGPUVIRTUALADDRESS structure%20 RELEASE:%20(2/24/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

