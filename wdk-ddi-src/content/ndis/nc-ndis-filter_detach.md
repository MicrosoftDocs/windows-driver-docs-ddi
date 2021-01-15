---
UID: NC:ndis.FILTER_DETACH
title: FILTER_DETACH (ndis.h)
description: NDIS calls a filter driver's FilterDetach function to release all the resources that are associated with a filter module.Note  You must declare the function by using the FILTER_DETACH type.
old-location: netvista\filterdetach.htm
tech.root: netvista
ms.date: 05/02/2018
keywords: ["FILTER_DETACH callback function"]
ms.keywords: FILTER_DETACH, FILTER_DETACH callback, FilterDetach, FilterDetach callback function [Network Drivers Starting with Windows Vista], filter_functions_ref_dec15a06-93c1-4da8-9dc6-b66be9c6f8eb.xml, ndis/FilterDetach, netvista.filterdetach
req.header: ndis.h
req.include-header: Ndis.h
req.target-type: Windows
req.target-min-winverclnt: Supported in NDIS 6.0 and later.
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
targetos: Windows
req.typenames: 
f1_keywords:
 - FILTER_DETACH
 - ndis/FILTER_DETACH
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - ndis.h
api_name:
 - FILTER_DETACH
---

# FILTER_DETACH callback function


## -description

NDIS calls a filter driver's 
  <i>FilterDetach</i> function to release all the resources that are associated with a filter module.
<div class="alert"><b>Note</b>  You must declare the function by using the <b>FILTER_DETACH</b> type. For more
   information, see the following Examples section.</div><div> </div>

## -parameters

### -param FilterModuleContext 

[in]
A handle to the context area for the filter module that NDIS will remove from the driver stack.
     The filter driver created and initialized this context area in the 
     <a href="/windows-hardware/drivers/ddi/ndis/nc-ndis-filter_attach">FilterAttach</a> function.

## -remarks

<i>FilterDetach</i> is a required function. NDIS calls 
    <i>FilterDetach</i> to remove a filter module from a driver stack. NDIS calls
    <i>FilterDetach</i> when the filter module is in the 
    <i>Paused</i> state.

<i>FilterDetach</i> frees the driver's context areas and other resources (such as buffer pools) for the
    affected filter module.

After the filter driver returns from 
    <i>FilterDetach</i>, the filter module is in the 
    <i>Detached</i> state.

NDIS calls 
    <i>FilterDetach</i> at IRQL = PASSIVE_LEVEL.

<h3><a id="Examples"></a><a id="examples"></a><a id="EXAMPLES"></a>Examples</h3>
To define a <i>FilterDetach</i> function, you must first provide a function declaration that identifies the type of function you're defining. Windows provides a set of function types for drivers. Declaring a function using the function types helps <a href="/windows-hardware/drivers/devtest/code-analysis-for-drivers">Code Analysis for Drivers</a>, <a href="/windows-hardware/drivers/devtest/static-driver-verifier">Static Driver Verifier</a> (SDV), and other verification tools find errors, and it's a requirement for writing drivers for the Windows operating system.

For example, to define a <i>FilterDetach</i> function that is named "MyDetach", use the <b>FILTER_DETACH</b> type as shown in this code example:


```
FILTER_DETACH MyDetach;
```

Then, implement your function as follows:


```
_Use_decl_annotations_
VOID
 MyDetach(
    NDIS_HANDLE  FilterModuleContext
    )
  {...}
```

The <b>FILTER_DETACH</b> function type is defined in the Ndis.h header file. To more accurately identify errors when you run the code analysis tools, be sure to add the _Use_decl_annotations_ annotation to your function definition.  The _Use_decl_annotations_ annotation ensures that the annotations that are applied to the <b>FILTER_DETACH</b> function type in the header file are used.  For more information about the requirements for function declarations, see <a href="/windows-hardware/drivers/devtest/declaring-functions-by-using-function-role-types-for-ndis-drivers">Declaring Functions by Using Function Role Types for NDIS Drivers</a>.

For information about  _Use_decl_annotations_, see <a href="/visualstudio/code-quality/annotating-function-behavior">Annotating Function Behavior</a>.

## -see-also

<a href="/windows-hardware/drivers/ddi/ndis/nc-ndis-filter_attach">FilterAttach</a>

