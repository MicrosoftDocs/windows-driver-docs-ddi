---
UID: NE:d3dkmddi._DXGK_RECOMMENDFUNCTIONALVIDPN_REASON
title: "_DXGK_RECOMMENDFUNCTIONALVIDPN_REASON"
author: windows-driver-content
description: The DXGK_RECOMMENDFUNCTIONALVIDPN_REASON enumeration indicates the reason for calling the display miniport driver's DxgkDdiRecommendFunctionalVidPn function.
old-location: display\dxgk_recommendfunctionalvidpn_reason.htm
old-project: display
ms.assetid: 75dda423-8d5a-4b11-a187-d6703601a366
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: DXGK_RECOMMENDFUNCTIONALVIDPN_REASON, DXGK_RECOMMENDFUNCTIONALVIDPN_REASON enumeration [Display Devices], DXGK_RFVR_FIRMWARE, DXGK_RFVR_HOTKEY, DXGK_RFVR_UNINITIALIZED, DXGK_RFVR_USERMODE, DmEnums_bb915c39-0ecd-4b15-8030-6a144173dc90.xml, _DXGK_RECOMMENDFUNCTIONALVIDPN_REASON, d3dkmddi/DXGK_RECOMMENDFUNCTIONALVIDPN_REASON, d3dkmddi/DXGK_RFVR_FIRMWARE, d3dkmddi/DXGK_RFVR_HOTKEY, d3dkmddi/DXGK_RFVR_UNINITIALIZED, d3dkmddi/DXGK_RFVR_USERMODE, display.dxgk_recommendfunctionalvidpn_reason
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	d3dkmddi.h
api_name:
-	DXGK_RECOMMENDFUNCTIONALVIDPN_REASON
product:
- Windows
targetos: Windows
req.typenames: DXGK_RECOMMENDFUNCTIONALVIDPN_REASON
---

# _DXGK_RECOMMENDFUNCTIONALVIDPN_REASON enumeration


## -description


The DXGK_RECOMMENDFUNCTIONALVIDPN_REASON enumeration indicates the reason for calling the display miniport driver's <a href="https://msdn.microsoft.com/320a77a7-d7d4-47b9-8a40-2b6e12819e4b">DxgkDdiRecommendFunctionalVidPn</a> function.


## -enum-fields




### -field DXGK_RFVR_UNINITIALIZED

Indicates that a variable of type DXGK_RECOMMENDFUNCTIONALVIDPN_REASON has not yet been assigned a meaningful value.


### -field DXGK_RFVR_HOTKEY

Indicates that the VidPN manager is calling <i>DxgkDdiRecommendFunctionalVidPn</i> because the user pressed a hot key to request a change in the way the desktop is displayed on a collection of monitors (or other display devices).


### -field DXGK_RFVR_USERMODE

Indicates that a user-mode application initiated a call to <i>DxgkDdiRecommendFunctionalVidPn</i>.


### -field DXGK_RFVR_FIRMWARE

Value indicating that the OS is requesting the driver to describe a functional VidPn which reflects the display topology and timings which are currently set, as inherited from firmware during boot or resume from hibernation.


## -remarks



The <b>RequestReason</b> member of the <a href="https://msdn.microsoft.com/library/windows/hardware/ff557632">DXGKARG_RECOMMENDFUNCTIONALVIDPN</a> structure is a DXGK_RECOMMENDFUNCTIONALVIDPN_REASON value.




## -see-also




<a href="https://msdn.microsoft.com/320a77a7-d7d4-47b9-8a40-2b6e12819e4b">DxgkDdiRecommendFunctionalVidPn</a>
 

 

