---
UID: NS:d3dkmthk._D3DKMT_SETDISPLAYMODE_FLAGS
title: _D3DKMT_SETDISPLAYMODE_FLAGS
author: windows-driver-content
description: The D3DKMT_SETDISPLAYMODE_FLAGS structure identifies attributes for setting the display mode.
old-location: display\d3dkmt_setdisplaymode_flags.htm
old-project: display
ms.assetid: 245586cb-d277-4cef-aeb9-b576a4ae6d43
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: _D3DKMT_SETDISPLAYMODE_FLAGS, D3DKMT_SETDISPLAYMODE_FLAGS
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: d3dkmthk.h
req.include-header: D3dkmthk.h
req.target-type: Windows
req.target-min-winverclnt: D3DKMT_SETDISPLAYMODE_FLAGS is supported beginning with the Windows 7 operating system.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: D3DKMT_SETDISPLAYMODE_FLAGS
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
req.typenames: D3DKMT_SETDISPLAYMODE_FLAGS
---

# _D3DKMT_SETDISPLAYMODE_FLAGS structure



## -description
The D3DKMT_SETDISPLAYMODE_FLAGS structure identifies attributes for setting the display mode.



## -syntax

````
typedef struct _D3DKMT_SETDISPLAYMODE_FLAGS {
  BOOLEAN PreserveVidPn  :1;
  UINT    Reserved  :31;
} D3DKMT_SETDISPLAYMODE_FLAGS;
````


## -struct-fields

### -field PreserveVidPn

[in] A Boolean value that specifies whether the video present network (VidPN) for a monitor is preserved. 


### -field Reserved

[in] This member is reserved and should be set to zero. 


## -remarks
To set attributes of the display mode, you specify bitfields of the D3DKMT_SETDISPLAYMODE_FLAGS structure in the <b>Flags</b> member of the <a href="..\d3dkmthk\ns-d3dkmthk-_d3dkmt_setdisplaymode.md">D3DKMT_SETDISPLAYMODE</a> structure. 


## -see-also
<dl>
<dt>
<a href="..\d3dkmthk\ns-d3dkmthk-_d3dkmt_setdisplaymode.md">D3DKMT_SETDISPLAYMODE</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20D3DKMT_SETDISPLAYMODE_FLAGS structure%20 RELEASE:%20(12/29/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

