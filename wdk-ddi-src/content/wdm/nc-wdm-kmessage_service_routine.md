---
UID: NC:wdm.KMESSAGE_SERVICE_ROUTINE
title: KMESSAGE_SERVICE_ROUTINE
author: windows-driver-content
description: An InterruptMessageService routine services a message-signaled interrupt.
old-location: kernel\interruptmessageservice.htm
old-project: kernel
ms.assetid: f84e1835-33a4-4300-8701-ed73249f8119
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: kernel.interruptmessageservice, InterruptMessageService routine [Kernel-Mode Driver Architecture], InterruptMessageService, KMESSAGE_SERVICE_ROUTINE, KMESSAGE_SERVICE_ROUTINE, wdm/InterruptMessageService, DrvrRtns_1f39517a-fa8b-44a4-9e6c-2ecc428cd416.xml
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h
req.target-type: Desktop
req.target-min-winverclnt: See Remarks section.
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
-	InterruptMessageService
product: Windows
targetos: Windows
req.typenames: "*PWDI_TYPE_PMK_NAME, WDI_TYPE_PMK_NAME"
req.product: Windows 10 or later.
---

# KMESSAGE_SERVICE_ROUTINE callback


## -description


An <i>InterruptMessageService</i> routine services a message-signaled interrupt.


## -prototype


````
KMESSAGE_SERVICE_ROUTINE InterruptMessageService;

BOOLEAN InterruptMessageService(
  _In_ struct _KINTERRUPT *Interrupt,
  _In_ PVOID              ServiceContext,
  _In_ ULONG              MessageId
)
{ ... }
````


## -parameters




### -param Interrupt [in]

A pointer to the <a href="https://msdn.microsoft.com/library/windows/hardware/ff554237">KINTERRUPT</a> structure for the interrupt. The driver received this pointer in the call to the <a href="..\wdm\nf-wdm-ioconnectinterruptex.md">IoConnectInterruptEx</a> routine that registered the driver's <i>InterruptMessageService</i> routine.


### -param ServiceContext [in]

The <i>ServiceContext</i> value that the driver passed to <a href="..\wdm\nf-wdm-ioconnectinterruptex.md">IoConnectInterruptEx</a> when the <i>InterruptMessageService</i> routine was registered.


### -param MessageID








#### - MessageId [in]

The message ID for the interrupt. This value is the index for the interrupt's entry in the <b>MessageInfo</b> member array in the <a href="..\wdm\ns-wdm-_io_interrupt_message_info.md">IO_INTERRUPT_MESSAGE_INFO</a> structure that describes the driver's message-signaled interrupts.


## -returns



The <i>InterruptMessageService</i> routine returns <b>TRUE</b> if the interrupt is one handled by the <i>InterruptMessageService</i> routine. Otherwise, it returns <b>FALSE</b>.




## -remarks



Drivers use <a href="..\wdm\nf-wdm-ioconnectinterruptex.md">IoConnectInterruptEx</a> to register an <i>InterruptMessageService</i> routine to handle their message-signaled interrupts. A driver can subsequently unregister the routine by calling <a href="..\wdm\nf-wdm-iodisconnectinterruptex.md">IoDisconnectInterruptEx</a>. Message-signaled interrupts are supported starting with Windows Vista.

The system can call an <i>InterruptMessageService</i> routine even when the routine's interrupt has not occurred. For example, if a message-signaled interrupt is shared, <i>InterruptMessageService</i> can be called for interrupts belonging to other devices. The routine must check whether the value for the <i>ServiceContext</i> parameter matches the value passed to <b>IoConnectInterruptEx</b>. If the value does match, <i>InterruptMessageService</i> handles the interrupt and returns <b>TRUE</b>. Otherwise, <i>InterruptMessageService</i> does not handle the interrupt and returns <b>FALSE</b>.

Note that if the system receives multiple identical interrupts over a short time interval, it can combine these into a single call to <i>InterruptMessageService</i>. The routine must be written to handle multiple identical interrupts within a single call.

Message-signaled interrupts are similar in behavior to edge-triggered interrupts. The device sends an interrupt request but does not receive any hardware acknowledgment that the request was received.

An <i>InterruptMessageService</i> executes at an IRQL greater than or equal to the maximum device IRQL (DIRQL) for every interrupt the routine handles.


#### Examples

To define an <i>InterruptMessageService</i> callback routine, you must first provide a function declaration that identifies the type of callback routine you're defining. Windows provides a set of callback function types for drivers. Declaring a function using the callback function types helps <a href="https://msdn.microsoft.com/2F3549EF-B50F-455A-BDC7-1F67782B8DCA">Code Analysis for Drivers</a>, <a href="https://msdn.microsoft.com/74feeb16-387c-4796-987a-aff3fb79b556">Static Driver Verifier</a> (SDV), and other verification tools find errors, and it's a requirement for writing drivers for the Windows operating system.

For example, to define an <i>InterruptMessageService</i> callback routine that is named <code>MyInterruptMessageService</code>, use the KMESSAGE_SERVICE_ROUTINE type as shown in this code example:

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>KMESSAGE_SERVICE_ROUTINE MyInterruptMessageService;</pre>
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
BOOLEAN
  MyInterruptMessageService(
    struct _KINTERRUPT  *Interrupt,
    PVOID  ServiceContext,
    ULONG  MessageId 
    )
  {
      // Function body
  }</pre>
</td>
</tr>
</table></span></div>
The KMESSAGE_SERVICE_ROUTINE function type is defined in the Wdm.h header file. To more accurately identify errors when you run the code analysis tools, be sure to add the _Use_decl_annotations_ annotation to your function definition. The _Use_decl_annotations_ annotation ensures that the annotations that are applied to the KMESSAGE_SERVICE_ROUTINE function type in the header file are used. For more information about the requirements for function declarations, see <a href="https://msdn.microsoft.com/3260b53e-82be-4dbc-8ac5-d0e52de77f9d">Declaring Functions by Using Function Role Types for WDM Drivers</a>. For information about _Use_decl_annotations_, see <a href="http://go.microsoft.com/fwlink/p/?linkid=286697">Annotating Function Behavior</a>.

<div class="code"></div>



## -see-also

<a href="..\wdm\nf-wdm-ioconnectinterruptex.md">IoConnectInterruptEx</a>



<a href="..\wdm\ns-wdm-_io_interrupt_message_info.md">IO_INTERRUPT_MESSAGE_INFO</a>



<a href="..\wdm\nf-wdm-iodisconnectinterruptex.md">IoDisconnectInterruptEx</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20InterruptMessageService routine%20 RELEASE:%20(2/16/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

