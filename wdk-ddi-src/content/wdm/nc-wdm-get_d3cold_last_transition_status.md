---
UID: NC:wdm.GET_D3COLD_LAST_TRANSITION_STATUS
title: GET_D3COLD_LAST_TRANSITION_STATUS
author: windows-driver-content
description: The GetLastTransitionStatus routine enables the driver for a device to query whether the most recent transition to the D3hot substate was followed by a transition to the D3cold substate.
old-location: kernel\getlasttransitionstatus.htm
old-project: kernel
ms.assetid: 2ED5A28B-8668-411D-9462-8D6ED2F08B35
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: kernel.getlasttransitionstatus, GetLastTransitionStatus routine [Kernel-Mode Driver Architecture], GetLastTransitionStatus, GET_D3COLD_LAST_TRANSITION_STATUS, GET_D3COLD_LAST_TRANSITION_STATUS, wdm/GetLastTransitionStatus
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	UserDefined
apilocation:
-	Wdm.h
apiname:
-	GetLastTransitionStatus
product: Windows
targetos: Windows
req.typenames: WDI_TYPE_PMK_NAME, *PWDI_TYPE_PMK_NAME
req.product: Windows 10 or later.
---

# GET_D3COLD_LAST_TRANSITION_STATUS callback


## -description


The <i>GetLastTransitionStatus</i> routine enables the driver for a device to query whether the most recent transition to the D3hot substate was followed by a transition to the D3cold substate.


## -prototype


````
GET_D3COLD_LAST_TRANSITION_STATUS GetLastTransitionStatus;

VOID GetLastTransitionStatus(
  _In_opt_ PVOID                          Context,
  _Out_    PD3COLD_LAST_TRANSITION_STATUS LastTransitionStatus
)
{ ... }
````


## -parameters




### -param Context [in, optional]

A pointer to interface-specific context information. The caller sets this parameter to the value of the <b>Context</b> member of the <a href="..\wdm\ns-wdm-_d3cold_support_interface.md">D3COLD_SUPPORT_INTERFACE</a> structure for the interface.


### -param LastTransitionStatus [out]

A pointer to a variable into which the routine writes one of the following <a href="..\wdm\ne-wdm-_d3cold_last_transition_status.md">D3COLD_LAST_TRANSITION_STATUS</a> enumeration values:

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

For more information, see <a href="..\wdm\ne-wdm-_d3cold_last_transition_status.md">D3COLD_LAST_TRANSITION_STATUS</a>.




## -see-also

<a href="..\wdm\ns-wdm-_d3cold_support_interface.md">D3COLD_SUPPORT_INTERFACE</a>



<a href="..\wdm\ne-wdm-_d3cold_last_transition_status.md">D3COLD_LAST_TRANSITION_STATUS</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20GET_D3COLD_LAST_TRANSITION_STATUS routine%20 RELEASE:%20(2/16/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

