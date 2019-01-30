---
UID: NC:fwpsk.FWPS_VSWITCH_FILTER_ENGINE_REORDER_CALLBACK0
title: FWPS_VSWITCH_FILTER_ENGINE_REORDER_CALLBACK0 (fwpsk.h)
description: The filter engine calls the vSwitchFilterEngineReorderNotifyRn (FWPS_VSWITCH_FILTER_ENGINE_REORDER_CALLBACK0) callout function to notify the callout driver about events that are associated the virtual switch filter engine reordering.Note  FWPS_VSWITCH_FILTER_ENGINE_REORDER_CALLBACK0 is a specific version of FWPS_VSWITCH_FILTER_ENGINE_REORDER_CALLBACK. See WFP Version-Independent Names and Targeting Specific Versions of Windows for more information.
old-location: netvista\fwps_vswitch_filter_engine_reorder_callback0.htm
tech.root: netvista
ms.assetid: 2526E8BD-316F-4B8D-9CC4-66F4E3B7D708
ms.date: 05/02/2018
ms.keywords: FWPS_VSWITCH_FILTER_ENGINE_REORDER_CALLBACK0, FWPS_VSWITCH_FILTER_ENGINE_REORDER_CALLBACK0 callback, fwpsk/vSwitchFilterEngineReorderNotifyRn, netvista.fwps_vswitch_filter_engine_reorder_callback0, vSwitchFilterEngineReorderNotifyRn, vSwitchFilterEngineReorderNotifyRn callback function [Network Drivers Starting with Windows Vista]
ms.topic: callback
req.header: fwpsk.h
req.include-header: Fwpsk.h
req.target-type: Windows
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
req.irql: "<= DISPATCH_LEVEL"
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	UserDefined
api_location:
-	fwpsk.h
api_name:
-	vSwitchFilterEngineReorderNotifyRn
product:
- Windows
targetos: Windows
req.typenames: 
---

# FWPS_VSWITCH_FILTER_ENGINE_REORDER_CALLBACK0 callback function


## -description


The filter engine calls the  <i>vSwitchFilterEngineReorderNotifyRn</i> (<i>FWPS_VSWITCH_FILTER_ENGINE_REORDER_CALLBACK0</i>) callout function to notify the callout driver about events that are associated the virtual switch  filter engine reordering.

<div class="alert"><b>Note</b>  <i>FWPS_VSWITCH_FILTER_ENGINE_REORDER_CALLBACK0</i> is a specific version of <i>FWPS_VSWITCH_FILTER_ENGINE_REORDER_CALLBACK</i>. See <a href="https://msdn.microsoft.com/FBDF53E5-F7DE-4DEB-AC18-6D2BB59FE670">WFP Version-Independent Names and Targeting Specific Versions of Windows</a> for more information.</div>

## -parameters




### -param *notifyContext [in, optional]

A pointer to a context provided by the callout driver. The driver passed this pointer to the <i>notifyContext</i> parameter of the <a href="https://msdn.microsoft.com/library/windows/hardware/hh439687">FwpsvSwitchEventsSubscribe0</a>
 function. This parameter is optional and can be NULL.


### -param *completionContext [in]

A pointer to a completion context provided by the callout driver. This parameter is optional and can be NULL.




### -param isInRequiredPosition [in]

A BOOLEAN value that is set to TRUE if the filter is in the required position in the filter stack or FALSE if it is not.


### -param *vSwitchExtensionLwfList [in]

An <a href="https://msdn.microsoft.com/library/windows/hardware/ff565457">NDIS_ENUM_FILTERS</a> structure that specifies a list of the virtual switch extension NDIS filter drivers.


## -returns



A callout's 
  
  <i>FWPS_VSWITCH_FILTER_ENGINE_REORDER_CALLBACK0</i> function returns one of the following NTSTATUS codes.

<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_SUCCESS</b></dt>
</dl>
</td>
<td width="60%">
The callout driver accepts the notification from the filter engine.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>Other status codes</b></dt>
</dl>
</td>
<td width="60%">
An error occurred. 

</td>
</tr>
</table>
 




## -remarks



A callout driver registers a 
  
  <i>vSwitchFilterEngineReorderNotifyRn</i> function  by calling      
    the <a href="https://msdn.microsoft.com/library/windows/hardware/hh439687">FwpsvSwitchEventsSubscribe0</a>
 function.

By default, the WFP virtual switch extension is positioned as the first filtering extension at virtual switch ingress. (Therefore, it is also the last extension at virtual switch egress). This is usually the best position, because the WFP extension can intercept packets before any other extensions can modify them at ingress. Also, the WFP extension can intercept packets after all packet modifications are done at egress.



However, because an administrator can reorder any virtual switch extensions of the same class, the WFP extension can be reordered out of the default position. After a reorder occurs, a WFP client’s filters could be bypassed and might need to be adjusted.

If the <i>vSwitchFilterEngineReorderNotifyRn</i> callback is registered, the callout driver is notified when a virtual switch reorder is occurring. The callout driver receives an <a href="https://msdn.microsoft.com/library/windows/hardware/ff565457">NDIS_ENUM_FILTERS</a> structure with an ordered list of current virtual switch extensions in the <i>vSwitchExtensionLwfList</i> parameter.

If the virtual switch extensions are reordered, the WFP extension is  paused (see <a href="https://msdn.microsoft.com/a239889e-ec39-48fc-9e82-c8bc3d7ca51a">FilterPause</a>) and restarted (see <a href="https://msdn.microsoft.com/4a917824-eef1-4945-b45e-1c940bc8a50d">FilterRestart</a>). From the WFP filter <i>FilterRestart</i> call, the WFP filter driver calls the <a href="https://msdn.microsoft.com/library/windows/hardware/ff561758">NdisEnumerateFilterModules</a> function to obtain an ordered list of virtual switch extension filters.  If the WFP extension is not in the default position, then the filter driver notifies the callout drivers.

A callout driver cannot return STATUS_PENDING from <i>vSwitchFilterEngineReorderNotifyRn</i>.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff543875">Callout Driver Callout Functions</a>



<a href="https://msdn.microsoft.com/a239889e-ec39-48fc-9e82-c8bc3d7ca51a">FilterPause</a>



<a href="https://msdn.microsoft.com/4a917824-eef1-4945-b45e-1c940bc8a50d">FilterRestart</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh439687">FwpsvSwitchEventsSubscribe0</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh439695">FwpsvSwitchNotifyComplete0</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff565457">NDIS_ENUM_FILTERS</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff561758">NdisEnumerateFilterModules</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff562610">NdisFRestartComplete</a>
 

 

