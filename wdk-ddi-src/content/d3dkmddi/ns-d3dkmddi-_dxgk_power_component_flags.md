---
UID: NS:d3dkmddi._DXGK_POWER_COMPONENT_FLAGS
title: "_DXGK_POWER_COMPONENT_FLAGS"
author: windows-driver-content
description: Describes state transition information about a power component.
old-location: display\dxgk_power_component_flags.htm
old-project: display
ms.assetid: aa8cce5b-d582-4c5b-99e2-fad1f0e80128
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: display.dxgk_power_component_flags, _DXGK_POWER_COMPONENT_FLAGS, DXGK_POWER_COMPONENT_FLAGS structure [Display Devices], DXGK_POWER_COMPONENT_FLAGS, d3dkmddi/DXGK_POWER_COMPONENT_FLAGS
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: d3dkmddi.h
req.include-header: D3dkmddi.h
req.target-type: Windows
req.target-min-winverclnt: Windows 8
req.target-min-winversvr: Windows Server 2012
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
-	D3dkmddi.h
apiname:
-	DXGK_POWER_COMPONENT_FLAGS
product: Windows
targetos: Windows
req.typenames: DXGK_POWER_COMPONENT_FLAGS
---

# _DXGK_POWER_COMPONENT_FLAGS structure


## -description


Describes state transition information about a power component.


## -syntax


````
typedef struct _DXGK_POWER_COMPONENT_FLAGS {
  union {
    struct {
      UINT Reserved0  :1;
      UINT DriverCompletesFStateTransition  :1;
      UINT TransitionTo_F0_OnDx  :1;
      UINT Reserved  :29;
    };
    UINT Value;
  };
} DXGK_POWER_COMPONENT_FLAGS;
````


## -struct-fields




### -field Reserved0

Reserved for system use and should be set to zero.


### -field DriverCompletesFStateTransition

If set, indicates that the display miniport driver will call the  <a href="..\d3dkmddi\nc-d3dkmddi-dxgkcb_completefstatetransition.md">DxgkCbCompleteFStateTransition</a> function for a registered power component when the component completes an F-state transition.

For more information, see Remarks section of the <a href="..\d3dkmddi\nc-d3dkmddi-dxgkcb_completefstatetransition.md">DxgkCbCompleteFStateTransition</a> function.


### -field TransitionTo_F0_OnDx

If set, indicates that the Windows power management framework will place a registered power component into the F0 power state during device power state (Dx) transitions.

If set, during a Dx transition the power manager places the component into the F0 state before it dispatches a Dx IRP to the device stack. The power manager keeps the component in the F0 state until the D0 IRP is completed.


### -field NoDebounce

 


### -field ActiveInD3

 


### -field Reserved

This member is reserved and should be set to zero. Setting this member to zero is equivalent to setting the remaining 29 bits (0xFFFFFFF8) of the 32-bit <b>Value</b> member to zeros.


### -field Value

A member in the union that <b>DXGK_POWER_COMPONENT_FLAGS</b> contains that can hold a 32-bit value that identifies information about the power component.


## -see-also

<a href="..\d3dkmddi\nc-d3dkmddi-dxgkcb_completefstatetransition.md">DxgkCbCompleteFStateTransition</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20DXGK_POWER_COMPONENT_FLAGS structure%20 RELEASE:%20(12/29/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

