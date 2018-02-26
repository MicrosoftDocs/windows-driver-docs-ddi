---
UID: NE:wdm._D3COLD_LAST_TRANSITION_STATUS
title: "_D3COLD_LAST_TRANSITION_STATUS"
author: windows-driver-content
description: The D3COLD_LAST_TRANSITION_STATUS enumeration indicates whether the most recent transition to the D3hot device power state was followed by a transition to the D3cold device power state.
old-location: kernel\d3cold_last_transition_status.htm
old-project: kernel
ms.assetid: 21E89D92-9902-4785-B022-8D17268FE75F
ms.author: windowsdriverdev
ms.date: 2/24/2018
ms.keywords: ",  , *, *PD3COLD_LAST_TRANSITION_STATUS, ,, 3, A, C, D, D3COLD_LAST_TRANSITION_STATUS, D3COLD_LAST_TRANSITION_STATUS enumeration [Kernel-Mode Driver Architecture], I, L, LastDStateTransitionD3cold, LastDStateTransitionD3hot, LastDStateTransitionStatusUnknown, N, O, P, R, S, T, U, _, _D3COLD_LAST_TRANSITION_STATUS, kernel.d3cold_last_transition_status, wdm/D3COLD_LAST_TRANSITION_STATUS, wdm/LastDStateTransitionD3cold, wdm/LastDStateTransitionD3hot, wdm/LastDStateTransitionStatusUnknown"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
req.header: wdm.h
req.include-header: Wdm.h
req.target-type: Windows
req.target-min-winverclnt: 
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
-	Wdm.h
apiname:
-	D3COLD_LAST_TRANSITION_STATUS
product: Windows
targetos: Windows
req.typenames: D3COLD_LAST_TRANSITION_STATUS, *PD3COLD_LAST_TRANSITION_STATUS
req.product: Windows 10 or later.
---

# _D3COLD_LAST_TRANSITION_STATUS enumeration


## -description


The <b>D3COLD_LAST_TRANSITION_STATUS</b> enumeration indicates whether the most recent transition to the D3hot device power state was followed by a transition to the D3cold device power state.


## -syntax


````
typedef enum _D3COLD_LAST_TRANSITION_STATUS { 
  LastDStateTransitionStatusUnknown  = 0,
  LastDStateTransitionD3hot,
  LastDStateTransitionD3cold
} D3COLD_LAST_TRANSITION_STATUS;
````


## -enum-fields




### -field LastDStateTransitionStatusUnknown

Information is not available from the bus driver or platform firmware about whether the most recent transition to D3hot was followed by a transition to D3cold.


### -field LastDStateTransitionD3hot

The most recent transition to the D3hot device power state was not followed by a transition to the D3cold device power state.


### -field LastDStateTransitionD3cold

The most recent transition to the D3hot device power state was followed by a transition to the D3cold device power state.


## -remarks



The <i>LastTransitionStatus</i> parameter of the <a href="..\wdm\nc-wdm-get_d3cold_last_transition_status.md">GetLastTransitionStatus</a> routine is a pointer to a variable of type <b>D3COLD_LAST_TRANSITION_STATUS</b>.




## -see-also

<a href="..\wdm\nc-wdm-get_d3cold_last_transition_status.md">GetLastTransitionStatus</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20D3COLD_LAST_TRANSITION_STATUS enumeration%20 RELEASE:%20(2/24/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

