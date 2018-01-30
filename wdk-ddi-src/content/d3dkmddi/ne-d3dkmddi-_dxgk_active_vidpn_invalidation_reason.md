---
UID: NE:d3dkmddi._DXGK_ACTIVE_VIDPN_INVALIDATION_REASON
title: "_DXGK_ACTIVE_VIDPN_INVALIDATION_REASON"
author: windows-driver-content
description: The DXGK_ACTIVE_VIDPN_INVALIDATION_REASON enumeration is used to indicate the reason why an active VidPN is invalidated and a new VidPN is requested.
old-location: display\dxgk_active_vidpn_invalidation_reason.htm
old-project: display
ms.assetid: e1f33307-1bb0-4cdd-aa47-954f6e551582
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: d3dkmddi/DXGK_AVIR_HOTKEY, d3dkmddi/DXGK_AVIR_UNINITIALIZED, DmEnums_9a263431-3cae-4e33-a2f0-310ec88c1343.xml, DXGK_ACTIVE_VIDPN_INVALIDATION_REASON enumeration [Display Devices], d3dkmddi/DXGK_AVIR_USERMODE, DXGK_AVIR_HOTKEY, d3dkmddi/DXGK_ACTIVE_VIDPN_INVALIDATION_REASON, DXGK_ACTIVE_VIDPN_INVALIDATION_REASON, DXGK_AVIR_UNINITIALIZED, display.dxgk_active_vidpn_invalidation_reason, DXGK_AVIR_USERMODE, _DXGK_ACTIVE_VIDPN_INVALIDATION_REASON
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
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
-	DXGK_ACTIVE_VIDPN_INVALIDATION_REASON
product: Windows
targetos: Windows
req.typenames: DXGK_ACTIVE_VIDPN_INVALIDATION_REASON
---

# _DXGK_ACTIVE_VIDPN_INVALIDATION_REASON enumeration


## -description


The DXGK_ACTIVE_VIDPN_INVALIDATION_REASON enumeration is used to indicate the reason why an active VidPN is invalidated and a new VidPN is requested.


## -syntax


````
typedef enum _DXGK_ACTIVE_VIDPN_INVALIDATION_REASON { 
  DXGK_AVIR_UNINITIALIZED  = DXGK_RFVR_UNINITIALIZED,
  DXGK_AVIR_HOTKEY         = DXGK_RFVR_HOTKEY,
  DXGK_AVIR_USERMODE       = DXGK_RFVR_USERMODE
} DXGK_ACTIVE_VIDPN_INVALIDATION_REASON;
````


## -enum-fields




### -field DXGK_AVIR_UNINITIALIZED

Indicates that a variable of type DXGK_ACTIVE_VIDPN_INVALIDATION_REASON has not yet been assigned a meaningful value. 


### -field DXGK_AVIR_HOTKEY

Indicates that the user pressed a keyboard shortcut to change the set of monitors (or other display devices) being used to display the desktop. 


### -field DXGK_AVIR_USERMODE

Indicates that a call to the <a href="..\d3dkmthk\nf-d3dkmthk-d3dkmtinvalidateactivevidpn.md">D3DKMTInvalidateActiveVidPn</a> function has been made in user mode.


## -see-also

<a href="..\d3dkmthk\nf-d3dkmthk-d3dkmtinvalidateactivevidpn.md">D3DKMTInvalidateActiveVidPN</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20DXGK_ACTIVE_VIDPN_INVALIDATION_REASON enumeration%20 RELEASE:%20(12/29/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

