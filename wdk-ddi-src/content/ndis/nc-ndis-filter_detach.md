---
UID: NC:ndis.FILTER_DETACH
title: FILTER_DETACH
author: windows-driver-content
description: NDIS calls a filter driver's FilterDetach function to release all the resources that are associated with a filter module.Note  You must declare the function by using the FILTER_DETACH type.
old-location: netvista\filterdetach.htm
old-project: netvista
ms.assetid: 49dfbbb3-74e7-4904-8370-36d589276653
ms.author: windowsdriverdev
ms.date: 4/25/2018
ms.keywords: FILTER_DETACH, FILTER_DETACH callback, FilterDetach, FilterDetach callback function [Network Drivers Starting with Windows Vista], filter_functions_ref_dec15a06-93c1-4da8-9dc6-b66be9c6f8eb.xml, ndis/FilterDetach, netvista.filterdetach
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	UserDefined
api_location:
-	ndis.h
api_name:
-	FilterDetach
product:
- Windows
targetos: Windows
req.typenames: 
---

# FILTER_DETACH callback function


## -description


NDIS calls a filter driver's 
  <i>FilterDetach</i> function to release all the resources that are associated with a filter module.
<div class="alert"><b>Note</b>  You must declare the function by using the <b>FILTER_DETACH</b> type. For more
   information, see the following Examples section.</div><div> </div>

## -parameters




### -param FilterModuleContext [in]

A handle to the context area for the filter module that NDIS will remove from the driver stack.
     The filter driver created and initialized this context area in the 
     <a href="https://msdn.microsoft.com/library/windows/hardware/ff540442">FilterAttach</a> function.


## -returns



None




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
To define a <i>FilterDetach</i> function, you must first provide a function declaration that identifies the type of function you're defining. Windows provides a set of function types for drivers. Declaring a function using the function types helps <a href="https://msdn.microsoft.com/2F3549EF-B50F-455A-BDC7-1F67782B8DCA">Code Analysis for Drivers</a>, <a href="https://msdn.microsoft.com/74feeb16-387c-4796-987a-aff3fb79b556">Static Driver Verifier</a> (SDV), and other verification tools find errors, and it's a requirement for writing drivers for the Windows operating system.

For example, to define a <i>FilterDetach</i> function that is named "MyDetach", use the <b>FILTER_DETACH</b> type as shown in this code example:

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>FILTER_DETACH MyDetach;</pre>
</td>
</tr>
</table></span></div>
Then, implement your function as follows:

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>_Use_decl_annotations_
VOID
 MyDetach(
    NDIS_HANDLE  FilterModuleContext
    )
  {...}</pre>
</td>
</tr>
</table></span></div>
The <b>FILTER_DETACH</b> function type is defined in the Ndis.h header file. To more accurately identify errors when you run the code analysis tools, be sure to add the _Use_decl_annotations_ annotation to your function definition.  The _Use_decl_annotations_ annotation ensures that the annotations that are applied to the <b>FILTER_DETACH</b> function type in the header file are used.  For more information about the requirements for function declarations, see <a href="https://msdn.microsoft.com/232c4272-0bf0-4a4e-9560-3bceeca8a3e3">Declaring Functions by Using Function Role Types for NDIS Drivers</a>.

For information about  _Use_decl_annotations_, see <a href="http://go.microsoft.com/fwlink/p/?linkid=286697">Annotating Function Behavior</a>. 




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff540442">FilterAttach</a>
 

 

