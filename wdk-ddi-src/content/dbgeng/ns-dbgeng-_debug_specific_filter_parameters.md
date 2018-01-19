---
UID: NS:dbgeng._DEBUG_SPECIFIC_FILTER_PARAMETERS
title: _DEBUG_SPECIFIC_FILTER_PARAMETERS
author: windows-driver-content
description: The DEBUG_SPECIFIC_FILTER_PARAMETERS structure contains the parameters for a specific event filter.
old-location: debugger\debug_specific_filter_parameters.htm
old-project: debugger
ms.assetid: 06926380-aae5-4d9f-94e0-43098f8a0423
ms.author: windowsdriverdev
ms.date: 1/10/2018
ms.keywords: _DEBUG_SPECIFIC_FILTER_PARAMETERS, DEBUG_SPECIFIC_FILTER_PARAMETERS, *PDEBUG_SPECIFIC_FILTER_PARAMETERS
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: dbgeng.h
req.include-header: DbgEng.h
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: DEBUG_SPECIFIC_FILTER_PARAMETERS
req.alt-loc: DbgEng.h
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
req.typenames: DEBUG_SPECIFIC_FILTER_PARAMETERS, *PDEBUG_SPECIFIC_FILTER_PARAMETERS
---

# _DEBUG_SPECIFIC_FILTER_PARAMETERS structure



## -description
The DEBUG_SPECIFIC_FILTER_PARAMETERS structure contains the parameters for a <a href="debugger.debug_filter_xxx#specific_event_filter#specific_event_filter">specific event filter</a>.



## -syntax

````
typedef struct _DEBUG_SPECIFIC_FILTER_PARAMETERS {
  ULONG ExecutionOption;
  ULONG ContinueOption;
  ULONG TextSize;
  ULONG CommandSize;
  ULONG ArgumentSize;
} DEBUG_SPECIFIC_FILTER_PARAMETERS, *PDEBUG_SPECIFIC_FILTER_PARAMETERS;
````


## -struct-fields

### -field ExecutionOption

The <a href="debugger.debug_filter_xxx#break_status#break_status">break status</a> of the specific event filter.  For possible values, see <b>DEBUG_FILTER_XXX</b>.


### -field ContinueOption

The <a href="debugger.debug_filter_xxx#handling_status#handling_status">handling status</a> of the specific event filter.  For possible values, see <b>DEBUG_FILTER_XXX</b>.


### -field TextSize

The size, in characters (including the terminator), of the name of the specific event filter.


### -field CommandSize

The size, in characters, of the command (including the terminator), to execute when the event occurs.


### -field ArgumentSize

Specifies the size, in characters, of the specific event filter argument.  This size includes the NULL terminator.  If the specific event filter does not take an argument, <b>ArgumentSize</b> is zero.

<div class="alert"><b>Note</b>  If the filter does take an argument, but the argument is empty, <b>ArgumentSize</b> will be one, reflecting the NULL terminator.</div>
<div> </div>

## -remarks


## -see-also
<dl>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff548398">GetSpecificFilterParameters</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff556795">SetSpecificFilterParameters</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [debugger\debugger]:%20DEBUG_SPECIFIC_FILTER_PARAMETERS structure%20 RELEASE:%20(1/10/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

