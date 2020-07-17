---
UID: NC:wdm.FREE_FUNCTION_EX
title: FREE_FUNCTION_EX (wdm.h)
description: The LookasideListFreeEx routine frees the storage for a lookaside-list entry when a client tries to insert the entry into a lookaside list that is full.
old-location: kernel\lookasidelistfreeex.htm
tech.root: kernel
ms.assetid: 2cc2fc91-eb14-4f15-a8ad-c35b4667406f
ms.date: 04/30/2018
keywords: ["FREE_FUNCTION_EX callback function"]
ms.keywords: DrvrRtns_8e1790bd-6b06-4eed-afec-eb8055f2cbde.xml, FREE_FUNCTION_EX, LookasideListFreeEx, LookasideListFreeEx routine [Kernel-Mode Driver Architecture], kernel.lookasidelistfreeex, wdm/LookasideListFreeEx
f1_keywords:
 - "wdm/LookasideListFreeEx"
 - "LookasideListFreeEx"
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h
req.target-type: Desktop
req.target-min-winverclnt: Supported in Windows Vista and later versions of Windows.
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
req.irql: See Remarks section.
topic_type:
- APIRef
- kbSyntax
api_type:
- UserDefined
api_location:
- Wdm.h
api_name:
- LookasideListFreeEx
product:
- Windows
targetos: Windows
req.typenames: 
---

# FREE_FUNCTION_EX callback function


## -description


The <i>LookasideListFreeEx</i> routine frees the storage for a lookaside-list entry when a client tries to insert the entry into a lookaside list that is full. 


## -parameters




### -param Buffer [in]

A pointer to the lookaside-list entry that is to be freed. 


### -param Lookaside [in, out]

A pointer to a <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/eprocess">LOOKASIDE_LIST_EX</a> structure that describes the lookaside list. This structure was previously initialized by the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-exinitializelookasidelistex">ExInitializeLookasideListEx</a> routine. 


## -remarks



A driver that creates a lookaside list can implement a <i>LookasideListFreeEx</i> routine to free previously allocated buffers when the list becomes full and can contain no more buffers. A buffer that is not in use is stored as an entry in the list. All entries in a lookaside list are buffers of a uniform size, which the driver specifies when the list is initialized.

The driver supplies a pointer to a custom <i>LookasideListFreeEx</i> routine as an input parameter in the <b>ExInitializeLookasideListEx</b> call that initializes the lookaside list. If the driver sets this parameter to <b>NULL</b>, the lookaside list uses a default deallocation routine instead.

A driver calls the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-exfreetolookasidelistex">ExFreeToLookasideListEx</a> routine to insert a previously allocated entry into a lookaside list. If the list is full (that is, if the list already contains the system-determined maximum number of entries), <b>ExFreeToLookasideListEx</b> calls <i>LookasideListFreeEx</i> to free the storage for the entry.

The <i>LookasideListFreeEx</i> routine can use the <i>Lookaside</i> parameter to access private context data that the driver has associated with the lookaside list. For more information, see the code example in <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-exinitializelookasidelistex">ExInitializeLookasideListEx</a>.

For more information about lookaside lists, see <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/using-lookaside-lists">Using Lookaside Lists</a>.

The <i>LookasideListFreeEx</i> routine is called at the same IRQL as the call to <b>ExFreeToLookasideListEx</b> that frees the entry. For a call to free an entry that resides in paged memory, the caller must be running IRQL <= APC_LEVEL. For a call to free an entry that resides in nonpaged memory, the caller must be running IRQL <= DISPATCH_LEVEL.


#### Examples

To define a <i>LookasideListFreeEx</i> callback routine, you must first provide a function declaration that identifies the type of callback routine you're defining. Windows provides a set of callback function types for drivers. Declaring a function using the callback function types helps <a href="https://docs.microsoft.com/windows-hardware/drivers/devtest/code-analysis-for-drivers">Code Analysis for Drivers</a>, <a href="https://docs.microsoft.com/windows-hardware/drivers/devtest/static-driver-verifier">Static Driver Verifier</a> (SDV), and other verification tools find errors, and it's a requirement for writing drivers for the Windows operating system.

For example, to define a <i>LookasideListFreeEx</i> callback routine that is named <code>MyLookasideListFreeEx</code>, use the FREE_FUNCTION_EX type as shown in this code example:

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>FREE_FUNCTION_EX MyLookasideListFreeEx;</pre>
</td>
</tr>
</table></span></div>
Then, implement your callback routine as follows:

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>_Use_decl_annotations_
VOID
  MyLookasideListFreeEx(
    PVOID  Buffer,
    PLOOKASIDE_LIST_EX  Lookaside
    )
  {
      // Function body
  }</pre>
</td>
</tr>
</table></span></div>
The FREE_FUNCTION_EX function type is defined in the Wdm.h header file. To more accurately identify errors when you run the code analysis tools, be sure to add the _Use_decl_annotations_ annotation to your function definition. The _Use_decl_annotations_ annotation ensures that the annotations that are applied to the FREE_FUNCTION_EX function type in the header file are used. For more information about the requirements for function declarations, see <a href="https://docs.microsoft.com/windows-hardware/drivers/devtest/declaring-functions-using-function-role-types-for-wdm-drivers">Declaring Functions by Using Function Role Types for WDM Drivers</a>. For information about _Use_decl_annotations_, see <a href="https://go.microsoft.com/fwlink/p/?linkid=286697">Annotating Function Behavior</a>.

<div class="code"></div>



## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-exfreetolookasidelistex">ExFreeToLookasideListEx</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-exinitializelookasidelistex">ExInitializeLookasideListEx</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/eprocess">LOOKASIDE_LIST_EX</a>
 

 

