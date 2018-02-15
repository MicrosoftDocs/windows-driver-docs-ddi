---
UID: NC:ndis.NDIS_TIMER_FUNCTION
title: NDIS_TIMER_FUNCTION
author: windows-driver-content
description: The NetTimerCallback function is called by NDIS after a driver sets a one-shot or periodic timer when a timer fires.Note  You must declare the function by using the NDIS_TIMER_FUNCTION type.
old-location: netvista\nettimercallback.htm
old-project: netvista
ms.assetid: 76e59376-58a4-4e35-bac4-ec5938c88cd7
ms.author: windowsdriverdev
ms.date: 1/18/2018
ms.keywords: netvista.nettimercallback, NetTimerCallback callback function [Network Drivers Starting with Windows Vista], NetTimerCallback, NDIS_TIMER_FUNCTION, NDIS_TIMER_FUNCTION, ndis/NetTimerCallback, ndis_timer_ref_9040f7c2-905a-457d-a7c3-07253e2fb3da.xml
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
req.irql: DISPATCH_LEVEL
topictype:
-	APIRef
-	kbSyntax
apitype:
-	UserDefined
apilocation:
-	Ndis.h
apiname:
-	NetTimerCallback
product: Windows
targetos: Windows
req.typenames: "*LPVIDEO_STREAM_INIT_PARMS, VIDEO_STREAM_INIT_PARMS"
---

# NDIS_TIMER_FUNCTION callback


## -description


The 
  <i>NetTimerCallback</i> function is called by NDIS after a driver sets a one-shot or periodic timer when a
  timer fires.
<div class="alert"><b>Note</b>  You must declare the function by using the <b>NDIS_TIMER_FUNCTION</b> type. For more
   information, see the following Examples section.</div><div> </div>

## -prototype


````
NDIS_TIMER_FUNCTION NetTimerCallback;

VOID NetTimerCallback(
  _In_ PVOID SystemSpecific1,
  _In_ PVOID FunctionContext,
  _In_ PVOID SystemSpecific2,
  _In_ PVOID SystemSpecific3
)
{ ... }
````


## -parameters




### -param SystemSpecific1 [in]

A pointer to a system-specific value that is reserved for system use.


### -param FunctionContext [in]

A pointer to a driver-supplied context area that the driver passed to the 
     <a href="..\ndis\nf-ndis-ndissettimerobject.md">NdisSetTimerObject</a> function. If the 
     <i>FunctionContext</i> parameter of 
     <b>NdisSetTimerObject</b> was <b>NULL</b>, NDIS uses the default value that the driver specified in the 
     <a href="..\ndis\ns-ndis-_ndis_timer_characteristics.md">
     NDIS_TIMER_CHARACTERISTICS</a> structure. The driver passed the structure to the 
     <a href="..\ndis\nf-ndis-ndisallocatetimerobject.md">NdisAllocateTimerObject</a> function
     to initialize the associated timer object.


### -param SystemSpecific2 [in]

A pointer to a system-specific value that is reserved for system use.


### -param SystemSpecific3 [in]

A pointer to a system-specific value that is reserved for system use.


## -returns



None




## -remarks



Any NDIS driver can have one or more 
    <i>NetTimerCallback</i> functions. Each such 
    <i>NetTimerCallback</i> function must be associated with a different driver-allocated and initialized
    timer object.

The driver initializes a driver-allocated timer object by calling the 
    <a href="..\ndis\nf-ndis-ndisallocatetimerobject.md">
    NdisAllocateTimerObject</a> function.

A subsequent call to the 
    <a href="..\ndis\nf-ndis-ndissettimerobject.md">NdisSetTimerObject</a> function causes the 
    <i>NetTimerCallback</i> function that is associated with the timer object to be run after a specified
    interval or periodically.

To cancel calls to 
    <i>NetTimerCallback</i>, call the 
    <a href="..\ndis\nf-ndis-ndiscanceltimerobject.md">NdisCancelTimerObject</a> function. NDIS
    might still call 
    <i>NetTimerCallback</i> if the timeout has already expired before the call to 
    <b>NdisCancelTimerObject</b>.

If a 
    <i>NetTimerCallback</i> function shares resources with other driver functions, the driver should
    synchronize access to those resources with a spin lock.

<h3><a id="Examples"></a><a id="examples"></a><a id="EXAMPLES"></a>Examples</h3>
To define a <i>NetTimerCallback</i> function, you must first provide a function declaration that identifies the type of function you're defining. Windows provides a set of function types for drivers. Declaring a function using the function types helps <a href="https://msdn.microsoft.com/2F3549EF-B50F-455A-BDC7-1F67782B8DCA">Code Analysis for Drivers</a>, <a href="https://msdn.microsoft.com/74feeb16-387c-4796-987a-aff3fb79b556">Static Driver Verifier</a> (SDV), and other verification tools find errors, and it's a requirement for writing drivers for the Windows operating system.

For example, to define a <i>NetTimerCallback</i> function that is named "MyTimerCallback", use the <b>NDIS_TIMER_FUNCTION</b> type as shown in this code example:

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>NDIS_TIMER_FUNCTION MyTimerCallback;</pre>
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
 MyTimerCallback(
    PVOID  SystemSpecific1,
    PVOID  FunctionContext,
    PVOID  SystemSpecific2,
    PVOID  SystemSpecific3
    )
  {...}</pre>
</td>
</tr>
</table></span></div>
The <b>NDIS_TIMER_FUNCTION</b> function type is defined in the Ndis.h header file. To more accurately identify errors when you run the code analysis tools, be sure to add the _Use_decl_annotations_ annotation to your function definition.  The _Use_decl_annotations_ annotation ensures that the annotations that are applied to the <b>NDIS_TIMER_FUNCTION</b> function type in the header file are used.  For more information about the requirements for function declarations, see <a href="https://msdn.microsoft.com/232c4272-0bf0-4a4e-9560-3bceeca8a3e3">Declaring Functions by Using Function Role Types for NDIS Drivers</a>.

For information about  _Use_decl_annotations_, see <a href="http://go.microsoft.com/fwlink/p/?linkid=286697">Annotating Function Behavior</a>.




## -see-also

<a href="..\ndis\nf-ndis-ndissettimerobject.md">NdisSetTimerObject</a>



<a href="..\ndis\nf-ndis-ndisallocatetimerobject.md">NdisAllocateTimerObject</a>



<a href="https://msdn.microsoft.com/75f348f7-173f-4799-88aa-1ca50a6df023">Setting and Clearing Timers</a>



<a href="..\ndis\nf-ndis-ndiscanceltimerobject.md">NdisCancelTimerObject</a>



<a href="https://msdn.microsoft.com/2f304f5c-fa70-441e-853e-a48ad70d61a0">Initializing NDIS Timers</a>



<a href="https://msdn.microsoft.com/6a80a55b-4c7e-4a48-8903-0a1fb28af153">Servicing Timers</a>



<a href="..\ndis\ns-ndis-_ndis_timer_characteristics.md">NDIS_TIMER_CHARACTERISTICS</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20NDIS_TIMER_FUNCTION callback function%20 RELEASE:%20(1/18/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

