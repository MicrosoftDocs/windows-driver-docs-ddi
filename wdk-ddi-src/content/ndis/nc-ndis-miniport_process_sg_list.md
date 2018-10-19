---
UID: NC:ndis.MINIPORT_PROCESS_SG_LIST
title: MINIPORT_PROCESS_SG_LIST
author: windows-driver-content
description: A bus-master miniport driver provides a MiniportProcessSGList function to process scatter/gather lists for network data.
old-location: netvista\miniportprocesssglist.htm
tech.root: netvista
ms.assetid: ddd5d14f-f886-40d0-9fc8-eeb37da63ebd
ms.date: 05/02/2018
ms.keywords: MINIPORT_PROCESS_SG_LIST, MINIPORT_PROCESS_SG_LIST callback, MiniportProcessSGList, MiniportProcessSGList callback function [Network Drivers Starting with Windows Vista], ndis/MiniportProcessSGList, ndis_sgdma_ref_e9dec598-19ce-4d50-98e3-508ffbb444bc.xml, netvista.miniportprocesssglist
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
req.irql: DISPATCH_LEVEL
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	UserDefined
api_location:
-	Ndis.h
api_name:
-	MiniportProcessSGList
product:
- Windows
targetos: Windows
req.typenames: 
---

# MINIPORT_PROCESS_SG_LIST callback function


## -description


A bus-master miniport driver provides a
   <i>MiniportProcessSGList</i> function to process scatter/gather lists for network data.
<div class="alert"><b>Note</b>  You must declare the function by using the <b>MINIPORT_PROCESS_SG_LIST</b> type. For more
   information, see the following Examples section.</div><div> </div>

## -parameters




### -param pDO [in]

Miniport drivers should ignore this parameter.


### -param Reserved [in]

Miniport drivers should ignore this parameter.


### -param pSGL [in]

A pointer to a scatter/gather list buffer. This is not necessarily the same buffer as the one the
     driver specified in the call to the 
     <a href="https://msdn.microsoft.com/3fd8d121-a249-433a-a93d-4027a4bfcb61">
     NdisMAllocateNetBufferSGList</a> function


### -param Context [in]

A pointer to a context area that the miniport driver created prior to calling 
     <b>NdisMAllocateNetBufferSGList</b>.


## -returns



None




## -remarks



Miniport drivers call the 
    <a href="https://msdn.microsoft.com/90ce64a2-9140-4b5f-88aa-b4f01a3d0c6f">
    NdisMRegisterScatterGatherDma</a> function to register a 
    <i>MiniportProcessSGList</i> function. When a miniport driver calls 
    <b>NdisMAllocateNetBufferSGList</b> to create a scatter/gather list, NDIS calls HAL to create the list.
    After creating the list, NDIS calls the miniport driver's 
    <i>MiniportProcessSGList</i> function.

When NDIS calls 
    <i>MiniportProcessSGList</i>, the driver can send the NET_BUFFER structure to the hardware. MiniportProcessSGList submits the physical addresses of the scatter/gather list to the NIC's DMA
    and issues a send command to the NIC.

HAL can call 
    <i>MiniportProcessSGList</i> before or after NDIS returns from 
    <b>NdisMAllocateNetBufferSGList</b>. Therefore, driver writers should not assume that the call is made
    within the context of 
    <b>NdisMAllocateNetBufferSGList</b>.

NDIS calls 
    <i>MiniportProcessSGList</i> at IRQL = DISPATCH_LEVEL.

<h3><a id="Examples"></a><a id="examples"></a><a id="EXAMPLES"></a>Examples</h3>
To define a <i>MiniportProcessSGList</i> function, you must first provide a function declaration that identifies the type of function you're defining. Windows provides a set of function types for drivers. Declaring a function using the function types helps <a href="https://msdn.microsoft.com/2F3549EF-B50F-455A-BDC7-1F67782B8DCA">Code Analysis for Drivers</a>, <a href="https://msdn.microsoft.com/74feeb16-387c-4796-987a-aff3fb79b556">Static Driver Verifier</a> (SDV), and other verification tools find errors, and it's a requirement for writing drivers for the Windows operating system.

For example, to define a <i>MiniportProcessSGList</i> function that is named "MyProcessSGList", use the <b>MINIPORT_PROCESS_SG_LIST</b> type as shown in this code example:

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>MINIPORT_PROCESS_SG_LIST MyProcessSGList;</pre>
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
 MyProcessSGList(
    PDEVICE_OBJECT  pDO,
    PVOID  Reserved,
    PSCATTER_GATHER_LIST  pSGL,
    PVOID  Context
    )
  {...}</pre>
</td>
</tr>
</table></span></div>
The <b>MINIPORT_PROCESS_SG_LIST</b> function type is defined in the Ndis.h header file. To more accurately identify errors when you run the code analysis tools, be sure to add the _Use_decl_annotations_ annotation to your function definition.  The _Use_decl_annotations_ annotation ensures that the annotations that are applied to the <b>MINIPORT_PROCESS_SG_LIST</b> function type in the header file are used.  For more information about the requirements for function declarations, see <a href="https://msdn.microsoft.com/232c4272-0bf0-4a4e-9560-3bceeca8a3e3">Declaring Functions by Using Function Role Types for NDIS Drivers</a>.

For information about  _Use_decl_annotations_, see <a href="http://go.microsoft.com/fwlink/p/?linkid=286697">Annotating Function Behavior</a>. 




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff562776">NdisMAllocateNetBufferSGList</a>



<a href="https://msdn.microsoft.com/90ce64a2-9140-4b5f-88aa-b4f01a3d0c6f">
   NdisMRegisterScatterGatherDma</a>
 

 

