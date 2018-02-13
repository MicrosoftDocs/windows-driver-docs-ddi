---
UID: NS:d3dkmthk._D3DKMT_DEVICERESET_STATE
title: "_D3DKMT_DEVICERESET_STATE"
author: windows-driver-content
description: The D3DKMT_DEVICERESET_STATE structure identifies reset status.
old-location: display\d3dkmt_devicereset_state.htm
old-project: display
ms.assetid: c2037d77-8745-4307-ac12-54f62f20c2d9
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: D3DKMT_DEVICERESET_STATE, D3DKMT_DEVICERESET_STATE structure [Display Devices], d3dkmthk/D3DKMT_DEVICERESET_STATE, display.d3dkmt_devicereset_state, _D3DKMT_DEVICERESET_STATE, OpenGL_Structs_03e42382-c472-4f0b-9183-a1b6630f64cf.xml
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
-	D3DKMT_DEVICERESET_STATE
product: Windows
targetos: Windows
req.typenames: D3DKMT_DEVICERESET_STATE
---

# _D3DKMT_DEVICERESET_STATE structure


## -description


The D3DKMT_DEVICERESET_STATE structure identifies reset status.


## -syntax


````
typedef struct _D3DKMT_DEVICERESET_STATE {
  union {
    struct {
      UINT DesktopSwitched  :1;
      UINT Reserved  :31;
    };
    UINT   Value;
  };
} D3DKMT_DEVICERESET_STATE;
````


## -struct-fields




### -field DesktopSwitched

A UINT value that specifies whether the desktop that the calling process is created on switched from being visible to being invisible. For example, when the security screen appears because a user pressed CTRL+ALT+DEL, the desktop that the calling process is created on becomes invisible. 

Setting this member is equivalent to setting the first bit of the 32-bit <b>Value</b> member (0x00000001).


### -field Reserved

This member is reserved and should be set to zero. Setting this member to zero is equivalent to setting the remaining 31 bits (0xFFFFFFFE) of the 32-bit <b>Value</b> member to zeros.


### -field Value

A 32-bit value that identifies reset status.


## -see-also

<a href="..\d3dkmthk\ns-d3dkmthk-_d3dkmt_getdevicestate.md">D3DKMT_GETDEVICESTATE</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20D3DKMT_DEVICERESET_STATE structure%20 RELEASE:%20(12/29/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

