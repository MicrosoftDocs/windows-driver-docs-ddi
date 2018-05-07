---
UID: NC:wdm.GET_D3COLD_LAST_TRANSITION_STATUS
title: GET_D3COLD_LAST_TRANSITION_STATUS
author: windows-driver-content
description: The GetLastTransitionStatus routine enables the driver for a device to query whether the most recent transition to the D3hot substate was followed by a transition to the D3cold substate.
old-location: kernel\getlasttransitionstatus.htm
old-project: kernel
ms.assetid: 2ED5A28B-8668-411D-9462-8D6ED2F08B35
ms.author: windowsdriverdev
ms.date: 4/30/2018
ms.keywords: GET_D3COLD_LAST_TRANSITION_STATUS, GetLastTransitionStatus, GetLastTransitionStatus routine [Kernel-Mode Driver Architecture], kernel.getlasttransitionstatus, wdm/GetLastTransitionStatus
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: wdm.h
req.include-header: Wdm.h
req.target-type: Desktop
req.target-min-winverclnt: Available starting with Windows 8.
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
-	UserDefined
api_location:
-	Wdm.h
api_name:
-	GetLastTransitionStatus
product:
- Windows
targetos: Windows
req.typenames: 
---

# GET_D3COLD_LAST_TRANSITION_STATUS callback function


## -description


The <i>GetLastTransitionStatus</i> routine enables the driver for a device to query whether the most recent transition to the D3hot substate was followed by a transition to the D3cold substate.


## -parameters




### -param Context [in, optional]

A pointer to interface-specific context information. The caller sets this parameter to the value of the <b>Context</b> member of the <a href="https://msdn.microsoft.com/library/windows/hardware/hh967706">D3COLD_SUPPORT_INTERFACE</a> structure for the interface.


### -param LastTransitionStatus [out]

A pointer to a variable into which the routine writes one of the following <a href="https://msdn.microsoft.com/library/windows/hardware/hh967705">D3COLD_LAST_TRANSITION_STATUS</a> enumeration values:

<ul>
<li><b>LastDStateTransitionStatusUnknown</b></li>
<li><b>LastDStateTransitionD3hot</b></li>
<li><b>LastDStateTransitionD3cold</b></li>
</ul>
 The <b>LastDStateTransitionD3cold</b> value indicates that the most recent transition to D3hot was followed by a transition to D3cold. For more information, see Remarks.


## -returns



None.




## -remarks



This routine tries to get the information needed to answer the caller's query from the parent bus driver and platform firmware. If this information is not available, the routine writes the value <b>LastDStateTransitionStatusUnknown</b> to the location pointed to by <i>the LastTransitionStatus</i> parameter.

For more information, see <a href="https://msdn.microsoft.com/library/windows/hardware/hh967705">D3COLD_LAST_TRANSITION_STATUS</a>.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/hh967705">D3COLD_LAST_TRANSITION_STATUS</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh967706">D3COLD_SUPPORT_INTERFACE</a>
 

 

