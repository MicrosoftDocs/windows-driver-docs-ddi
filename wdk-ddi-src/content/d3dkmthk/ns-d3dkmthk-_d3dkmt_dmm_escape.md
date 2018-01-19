---
UID: NS:d3dkmthk._D3DKMT_DMM_ESCAPE
title: _D3DKMT_DMM_ESCAPE
author: windows-driver-content
description: Do not use the D3DKMT_DMM_ESCAPE structure; it is for testing purposes only. The D3DKMT_DMM_ESCAPE structure describes how to control the display mode manager (DMM) in a call to the D3DKMTEscape function.
old-location: display\d3dkmt_dmm_escape.htm
old-project: display
ms.assetid: 9d4a317d-bb0c-47d4-b9f2-e668adc4d0d4
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: _D3DKMT_DMM_ESCAPE, D3DKMT_DMM_ESCAPE
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: d3dkmthk.h
req.include-header: D3dkmthk.h
req.target-type: Windows
req.target-min-winverclnt: Available in Windows Vista and later versions of the Windows operating systems.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: D3DKMT_DMM_ESCAPE
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
req.typenames: D3DKMT_DMM_ESCAPE
---

# _D3DKMT_DMM_ESCAPE structure



## -description

   Do not use the D3DKMT_DMM_ESCAPE structure; it is for testing purposes only.
   

The D3DKMT_DMM_ESCAPE structure describes how to control the display mode manager (DMM) in a call to the <a href="..\d3dkmthk\nf-d3dkmthk-d3dkmtescape.md">D3DKMTEscape</a> function.



## -syntax

````
typedef struct _D3DKMT_DMM_ESCAPE {
  D3DKMT_DMMESCAPETYPE Type;
  SIZE_T               ProvidedBufferSize;
  SIZE_T               MinRequiredBufferSize;
  UCHAR                Data[1];
} D3DKMT_DMM_ESCAPE;
````


## -struct-fields

### -field Type


### -field ProvidedBufferSize

actual size of Data[] array, in bytes.


### -field MinRequiredBufferSize

minimum required size of Data[] array to contain requested data.


### -field Data


## -remarks


## -see-also
<dl>
<dt>
<a href="..\d3dkmthk\ns-d3dkmthk-_d3dkmt_escape.md">D3DKMT_ESCAPE</a>
</dt>
<dt>
<a href="..\d3dkmthk\nf-d3dkmthk-d3dkmtescape.md">D3DKMTEscape</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20D3DKMT_DMM_ESCAPE structure%20 RELEASE:%20(12/29/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

