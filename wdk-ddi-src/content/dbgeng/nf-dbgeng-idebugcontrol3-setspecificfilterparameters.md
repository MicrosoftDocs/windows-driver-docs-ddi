---
UID: NF:dbgeng.IDebugControl3.SetSpecificFilterParameters
title: IDebugControl3::SetSpecificFilterParameters method
author: windows-driver-content
description: The SetSpecificFilterParameters method changes the break status and handling status for some specific event filters.
old-location: debugger\setspecificfilterparameters.htm
old-project: debugger
ms.assetid: 97eb6db8-3c0a-44b4-8fb4-9e42ee9f9856
ms.author: windowsdriverdev
ms.date: 1/10/2018
ms.keywords: IDebugControl3, IDebugControl3::SetSpecificFilterParameters, SetSpecificFilterParameters
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: method
req.header: dbgeng.h
req.include-header: Dbgeng.h
req.target-type: Desktop
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: IDebugControl.SetSpecificFilterParameters,IDebugControl2.SetSpecificFilterParameters,IDebugControl3.SetSpecificFilterParameters
req.alt-loc: dbgeng.h
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
req.typenames: *PDOT4_ACTIVITY, DOT4_ACTIVITY
---

# IDebugControl3::SetSpecificFilterParameters method



## -description
The <b>SetSpecificFilterParameters</b> method changes the <a href="debugger.debug_filter_xxx#break_status#break_status">break status</a> and <a href="debugger.debug_filter_xxx#handling_status#handling_status">handling status</a> for some specific event filters.



## -syntax

````
HRESULT SetSpecificFilterParameters(
  [in] ULONG                             Start,
  [in] ULONG                             Count,
  [in] PDEBUG_SPECIFIC_FILTER_PARAMETERS Params
);
````


## -parameters

### -param Start [in]

Specifies the index of the first specific event filter whose parameters will be changed.


### -param Count [in]

Specifies the number of specific event filters whose parameters will be changed.


### -param Params [in]

Specifies an array of specific event filter parameters of type <a href="..\dbgeng\ns-dbgeng-_debug_specific_filter_parameters.md">DEBUG_SPECIFIC_FILTER_PARAMETERS</a>.  Only the <b>ExecutionOption</b> and <b>ContinueOption</b> members are used.  <b>ExceptionOption</b> specifies the new break status and <b>ContinueOption</b> specifies the new handling status.


## -returns
This method may also return error values.  See <a href="https://msdn.microsoft.com/713f3ee2-2f5b-415e-9908-90f5ae428b43">Return Values</a> for more details.
<dl>
<dt><b>S_OK</b></dt>
</dl>The method was successful.

 


## -remarks
For more information about <a href="debugger.events#event_filters#event_filters">event filters</a>, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff543071">Event Filters</a>.


## -see-also
<dl>
<dt>
<a href="..\dbgeng\nn-dbgeng-idebugcontrol.md">IDebugControl</a>
</dt>
<dt>
<a href="..\dbgeng\nn-dbgeng-idebugcontrol2.md">IDebugControl2</a>
</dt>
<dt>
<a href="..\dbgeng\nn-dbgeng-idebugcontrol3.md">IDebugControl3</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/fdb5059f-e7d9-4e14-aa3d-030e72c30732">sx, sxd, sxe, sxi, sxn (Set Exceptions)</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff548398">GetSpecificFilterParameters</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff556683">SetExceptionFilterParameters</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [debugger\debugger]:%20IDebugControl::SetSpecificFilterParameters method%20 RELEASE:%20(1/10/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

