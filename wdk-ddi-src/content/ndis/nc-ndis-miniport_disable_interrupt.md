---
UID: NC:ndis.MINIPORT_DISABLE_INTERRUPT
title: MINIPORT_DISABLE_INTERRUPT
author: windows-driver-content
description: NDIS can call a miniport driver's MiniportDisableInterruptEx handler to disable interrupts for diagnostic and troubleshooting purposes.
old-location: netvista\miniportdisableinterruptex.htm
old-project: netvista
ms.assetid: 6016ab15-56c6-4430-8883-d4cdcdf6116f
ms.author: windowsdriverdev
ms.date: 4/25/2018
ms.keywords: MINIPORT_DISABLE_INTERRUPT, MINIPORT_DISABLE_INTERRUPT callback, MiniportDisableInterruptEx, MiniportDisableInterruptEx callback function [Network Drivers Starting with Windows Vista], ndis/MiniportDisableInterruptEx, ndis_interrupts_miniport_functions_ref_985ddb3d-4a38-4c96-8599-17f211d47b49.xml, netvista.miniportdisableinterruptex
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
req.irql: See Remarks section
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	UserDefined
api_location:
-	Ndis.h
api_name:
-	MiniportDisableInterruptEx
product:
- Windows
targetos: Windows
req.typenames: 
---

# MINIPORT_DISABLE_INTERRUPT callback function


## -description


NDIS can call a miniport driver's 
   <i>MiniportDisableInterruptEx</i> handler to disable interrupts for diagnostic and troubleshooting
   purposes.
<div class="alert"><b>Note</b>  You must declare the function by using the <b>MINIPORT_DISABLE_INTERRUPT</b> type. For more
   information, see the following Examples section.</div><div> </div>

## -parameters




### -param MiniportInterruptContext [in]

A handle to a block of context information. The miniport driver supplied this handle in the 
     <i>MiniportInterruptContext</i> parameter that the miniport driver passed to the 
     <a href="https://msdn.microsoft.com/db0b3d51-5bbb-45fb-8c45-dda8c2212b5f">
     NdisMRegisterInterruptEx</a> function.


## -returns



None




## -remarks



A miniport driver must provide a
    <i>MiniportDisableInterruptEx</i> handler if the driver calls the 
    <a href="https://msdn.microsoft.com/library/windows/hardware/ff563649">NdisMRegisterInterruptEx</a> function
    to register an interrupt.

Miniport drivers should disable and enable interrupts as explained in the 
    <a href="https://msdn.microsoft.com/810503b9-75cd-4b38-ab1f-de240968ded6">MiniportInterrupt</a> and 
    <a href="https://msdn.microsoft.com/345715fb-878c-44d8-bf78-f3add10dd02b">MiniportInterruptDpc</a> reference
    pages.

NDIS calls the 
    <a href="https://msdn.microsoft.com/61edeb80-a686-4b8c-ae19-4757616151ef">MiniportEnableInterruptEx</a> and    
    <i>MiniportDisableInterruptEx</i> functions to enable and disable interrupts for diagnostic and
    troubleshooting purposes. Typically, 
    <i>MiniportEnableInterruptEx</i> and 
    <i>MiniportDisableInterruptEx</i> access miniport driver resources that are shared by the 
    <a href="https://msdn.microsoft.com/810503b9-75cd-4b38-ab1f-de240968ded6">MiniportInterrupt</a> function.
    Therefore, NDIS calls these handlers at DIRQL.

<h3><a id="Examples"></a><a id="examples"></a><a id="EXAMPLES"></a>Examples</h3>
To define a <i>MiniportDisableInterruptEx</i> function, you must first provide a function declaration that identifies the type of function you're defining. Windows provides a set of function types for drivers. Declaring a function using the function types helps <a href="https://msdn.microsoft.com/2F3549EF-B50F-455A-BDC7-1F67782B8DCA">Code Analysis for Drivers</a>, <a href="https://msdn.microsoft.com/74feeb16-387c-4796-987a-aff3fb79b556">Static Driver Verifier</a> (SDV), and other verification tools find errors, and it's a requirement for writing drivers for the Windows operating system.

For example, to define a <i>MiniportDisableInterruptEx</i> function that is named "MyDisableInterruptEx", use the <b>MINIPORT_DISABLE_INTERRUPT</b> type as shown in this code example:

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>MINIPORT_DISABLE_INTERRUPT MyDisableInterruptEx;</pre>
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
 MyDisableInterruptEx(
    NDIS_HANDLE  MiniportInterruptContext
    )
  {...}</pre>
</td>
</tr>
</table></span></div>
The <b>MINIPORT_DISABLE_INTERRUPT</b> function type is defined in the Ndis.h header file. To more accurately identify errors when you run the code analysis tools, be sure to add the _Use_decl_annotations_ annotation to your function definition.  The _Use_decl_annotations_ annotation ensures that the annotations that are applied to the <b>MINIPORT_DISABLE_INTERRUPT</b> function type in the header file are used.  For more information about the requirements for function declarations, see <a href="https://msdn.microsoft.com/232c4272-0bf0-4a4e-9560-3bceeca8a3e3">Declaring Functions by Using Function Role Types for NDIS Drivers</a>.

For information about  _Use_decl_annotations_, see <a href="http://go.microsoft.com/fwlink/p/?linkid=286697">Annotating Function Behavior</a>. 




## -see-also




<a href="https://msdn.microsoft.com/61edeb80-a686-4b8c-ae19-4757616151ef">MiniportEnableInterruptEx</a>



<a href="https://msdn.microsoft.com/810503b9-75cd-4b38-ab1f-de240968ded6">MiniportInterrupt</a>



<a href="https://msdn.microsoft.com/345715fb-878c-44d8-bf78-f3add10dd02b">MiniportInterruptDPC</a>



<a href="https://msdn.microsoft.com/f4176e2d-d8d2-4e75-bccb-0c452da4d703">
   NDIS_MINIPORT_INTERRUPT_CHARACTERISTICS</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff563649">NdisMRegisterInterruptEx</a>
 

 

