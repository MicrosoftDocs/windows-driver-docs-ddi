---
UID: NC:ndis.MINIPORT_ENABLE_INTERRUPT
title: MINIPORT_ENABLE_INTERRUPT
author: windows-driver-content
description: NDIS can call a miniport driver's MiniportEnableInterruptEx handler to enable interrupts for diagnostic and troubleshooting purposes.
old-location: netvista\miniportenableinterruptex.htm
old-project: netvista
ms.assetid: 61edeb80-a686-4b8c-ae19-4757616151ef
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: MINIPORT_ENABLE_INTERRUPT, MiniportEnableInterruptEx, MiniportEnableInterruptEx callback function [Network Drivers Starting with Windows Vista], ndis/MiniportEnableInterruptEx, ndis_interrupts_miniport_functions_ref_4a4172dc-19bc-4405-8fc1-48bb8af2ae8d.xml, netvista.miniportenableinterruptex
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
-	MiniportEnableInterruptEx
product: Windows
targetos: Windows
req.typenames: VIDEO_STREAM_INIT_PARMS, *LPVIDEO_STREAM_INIT_PARMS
---

# MINIPORT_ENABLE_INTERRUPT callback


## -description


NDIS can call a miniport driver's 
   <i>MiniportEnableInterruptEx</i> handler to enable interrupts for diagnostic and troubleshooting
   purposes.
<div class="alert"><b>Note</b>  You must declare the function by using the <b>MINIPORT_ENABLE_INTERRUPT</b> type. For more
   information, see the following Examples section.</div><div> </div>

## -prototype


````
MINIPORT_ENABLE_INTERRUPT MiniportEnableInterruptEx;

VOID MiniportEnableInterruptEx(
  _In_ NDIS_HANDLE MiniportInterruptContext
)
{ ... }
````


## -parameters




### -param MiniportInterruptContext [in]

A handle to a block of context information. The miniport driver supplied this handle in the 
     <i>MiniportInterruptContext</i> parameter that the miniport driver passed to the 
     <a href="..\ndis\nf-ndis-ndismregisterinterruptex.md">
     NdisMRegisterInterruptEx</a> function.


## -returns



None




## -remarks



A miniport driver must provide a
    <i>MiniportEnableInterruptEx</i> handler if the driver calls the 
    <a href="..\ndis\nf-ndis-ndismregisterinterruptex.md">NdisMRegisterInterruptEx</a> function
    to register an interrupt.

Miniport drivers should disable and enable interrupts as explained in the 
    <a href="..\ndis\nc-ndis-miniport_isr.md">MiniportInterrupt</a> and 
    <a href="..\ndis\nc-ndis-miniport_interrupt_dpc.md">MiniportInterruptDpc</a> reference
    pages.

NDIS calls the 
    <i>MiniportEnableInterruptEx</i> and 
    <a href="..\ndis\nc-ndis-miniport_disable_interrupt.md">
    MiniportDisableInterruptEx</a> functions to enable and disable interrupts for diagnostic and
    troubleshooting purposes. Typically, 
    <i>MiniportEnableInterruptEx</i> and 
    <i>MiniportDisableInterruptEx</i> access miniport driver resources that are shared by the 
    <a href="..\ndis\nc-ndis-miniport_isr.md">MiniportInterrupt</a> function.
    Therefore, NDIS calls these handlers at DIRQL.

<h3><a id="Examples"></a><a id="examples"></a><a id="EXAMPLES"></a>Examples</h3>
To define a <i>MiniportEnableInterruptEx</i> function, you must first provide a function declaration that identifies the type of function you're defining. Windows provides a set of function types for drivers. Declaring a function using the function types helps <a href="https://msdn.microsoft.com/2F3549EF-B50F-455A-BDC7-1F67782B8DCA">Code Analysis for Drivers</a>, <a href="https://msdn.microsoft.com/74feeb16-387c-4796-987a-aff3fb79b556">Static Driver Verifier</a> (SDV), and other verification tools find errors, and it's a requirement for writing drivers for the Windows operating system.

For example, to define a <i>MiniportEnableInterruptEx</i> function that is named "MyEnableInterruptEx", use the <b>MINIPORT_ENABLE_INTERRUPT</b> type as shown in this code example:

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>MINIPORT_ENABLE_INTERRUPT MyEnableInterruptEx;</pre>
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
 MyEnableInterruptEx(
    NDIS_HANDLE  MiniportInterruptContext
    )
  {...}</pre>
</td>
</tr>
</table></span></div>
The <b>MINIPORT_ENABLE_INTERRUPT</b> function type is defined in the Ndis.h header file. To more accurately identify errors when you run the code analysis tools, be sure to add the _Use_decl_annotations_ annotation to your function definition.  The _Use_decl_annotations_ annotation ensures that the annotations that are applied to the <b>MINIPORT_ENABLE_INTERRUPT</b> function type in the header file are used.  For more information about the requirements for function declarations, see <a href="https://msdn.microsoft.com/232c4272-0bf0-4a4e-9560-3bceeca8a3e3">Declaring Functions by Using Function Role Types for NDIS Drivers</a>.

For information about  _Use_decl_annotations_, see <a href="http://go.microsoft.com/fwlink/p/?linkid=286697">Annotating Function Behavior</a>. 




## -see-also

<a href="..\ndis\ns-ndis-_ndis_miniport_interrupt_characteristics.md">
   NDIS_MINIPORT_INTERRUPT_CHARACTERISTICS</a>



<a href="..\ndis\nf-ndis-ndismregisterinterruptex.md">NdisMRegisterInterruptEx</a>



<a href="..\ndis\nc-ndis-miniport_disable_interrupt.md">MiniportDisableInterruptEx</a>



<a href="..\ndis\nc-ndis-miniport_isr.md">MiniportInterrupt</a>



<a href="..\ndis\nc-ndis-miniport_interrupt_dpc.md">MiniportInterruptDPC</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20MINIPORT_ENABLE_INTERRUPT callback function%20 RELEASE:%20(2/26/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

