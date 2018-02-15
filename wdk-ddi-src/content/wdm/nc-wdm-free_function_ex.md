---
UID: NC:wdm.FREE_FUNCTION_EX
title: FREE_FUNCTION_EX
author: windows-driver-content
description: The LookasideListFreeEx routine frees the storage for a lookaside-list entry when a client tries to insert the entry into a lookaside list that is full.
old-location: kernel\lookasidelistfreeex.htm
old-project: kernel
ms.assetid: 2cc2fc91-eb14-4f15-a8ad-c35b4667406f
ms.author: windowsdriverdev
ms.date: 1/4/2018
ms.keywords: kernel.lookasidelistfreeex, LookasideListFreeEx routine [Kernel-Mode Driver Architecture], LookasideListFreeEx, FREE_FUNCTION_EX, FREE_FUNCTION_EX, wdm/LookasideListFreeEx, DrvrRtns_8e1790bd-6b06-4eed-afec-eb8055f2cbde.xml
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	UserDefined
apilocation:
-	Wdm.h
apiname:
-	LookasideListFreeEx
product: Windows
targetos: Windows
req.typenames: "*PWDI_TYPE_PMK_NAME, WDI_TYPE_PMK_NAME"
req.product: Windows 10 or later.
---

# FREE_FUNCTION_EX callback


## -description


The <i>LookasideListFreeEx</i> routine frees the storage for a lookaside-list entry when a client tries to insert the entry into a lookaside list that is full. 


## -prototype


````
FREE_FUNCTION_EX LookasideListFreeEx;

VOID LookasideListFreeEx(
  _In_    PVOID              Buffer,
  _Inout_ PLOOKASIDE_LIST_EX Lookaside
)
{ ... }
````


## -parameters




### -param Buffer [in]

A pointer to the lookaside-list entry that is to be freed. 


### -param Lookaside [in, out]

A pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/ff554329">LOOKASIDE_LIST_EX</a> structure that describes the lookaside list. This structure was previously initialized by the <a href="..\wdm\nf-wdm-exinitializelookasidelistex.md">ExInitializeLookasideListEx</a> routine. 


## -returns



None




## -remarks



A driver that creates a lookaside list can implement a <i>LookasideListFreeEx</i> routine to free previously allocated buffers when the list becomes full and can contain no more buffers. A buffer that is not in use is stored as an entry in the list. All entries in a lookaside list are buffers of a uniform size, which the driver specifies when the list is initialized.

The driver supplies a pointer to a custom <i>LookasideListFreeEx</i> routine as an input parameter in the <b>ExInitializeLookasideListEx</b> call that initializes the lookaside list. If the driver sets this parameter to <b>NULL</b>, the lookaside list uses a default deallocation routine instead.

A driver calls the <a href="..\wdm\nf-wdm-exfreetolookasidelistex.md">ExFreeToLookasideListEx</a> routine to insert a previously allocated entry into a lookaside list. If the list is full (that is, if the list already contains the system-determined maximum number of entries), <b>ExFreeToLookasideListEx</b> calls <i>LookasideListFreeEx</i> to free the storage for the entry.

The <i>LookasideListFreeEx</i> routine can use the <i>Lookaside</i> parameter to access private context data that the driver has associated with the lookaside list. For more information, see the code example in <a href="..\wdm\nf-wdm-exinitializelookasidelistex.md">ExInitializeLookasideListEx</a>.

For more information about lookaside lists, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff565416">Using Lookaside Lists</a>.

The <i>LookasideListFreeEx</i> routine is called at the same IRQL as the call to <b>ExFreeToLookasideListEx</b> that frees the entry. For a call to free an entry that resides in paged memory, the caller must be running IRQL &lt;= APC_LEVEL. For a call to free an entry that resides in nonpaged memory, the caller must be running IRQL &lt;= DISPATCH_LEVEL.


#### Examples

To define a <i>LookasideListFreeEx</i> callback routine, you must first provide a function declaration that identifies the type of callback routine you're defining. Windows provides a set of callback function types for drivers. Declaring a function using the callback function types helps <a href="https://msdn.microsoft.com/2F3549EF-B50F-455A-BDC7-1F67782B8DCA">Code Analysis for Drivers</a>, <a href="https://msdn.microsoft.com/74feeb16-387c-4796-987a-aff3fb79b556">Static Driver Verifier</a> (SDV), and other verification tools find errors, and it's a requirement for writing drivers for the Windows operating system.

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
The FREE_FUNCTION_EX function type is defined in the Wdm.h header file. To more accurately identify errors when you run the code analysis tools, be sure to add the _Use_decl_annotations_ annotation to your function definition. The _Use_decl_annotations_ annotation ensures that the annotations that are applied to the FREE_FUNCTION_EX function type in the header file are used. For more information about the requirements for function declarations, see <a href="https://msdn.microsoft.com/3260b53e-82be-4dbc-8ac5-d0e52de77f9d">Declaring Functions by Using Function Role Types for WDM Drivers</a>. For information about _Use_decl_annotations_, see <a href="http://go.microsoft.com/fwlink/p/?linkid=286697">Annotating Function Behavior</a>.

<div class="code"></div>



## -see-also

<a href="..\wdm\nf-wdm-exfreetolookasidelistex.md">ExFreeToLookasideListEx</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff554329">LOOKASIDE_LIST_EX</a>



<a href="..\wdm\nf-wdm-exinitializelookasidelistex.md">ExInitializeLookasideListEx</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20LookasideListFreeEx routine%20 RELEASE:%20(1/4/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

