---
UID: NF:wdm.KeMemoryBarrier
title: KeMemoryBarrier function
author: windows-driver-content
description: The KeMemoryBarrier routine creates a barrier at its position in the code&#8212;across which the compiler and the processor cannot move any operations.
old-location: kernel\kememorybarrier.htm
old-project: kernel
ms.assetid: e6ffb893-a79f-4cc0-9052-667b835f4ad3
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: wdm/KeMemoryBarrier, KeMemoryBarrier routine [Kernel-Mode Driver Architecture], kernel.kememorybarrier, k105_972df62d-6449-40d7-9bfa-0c420cf8f106.xml, KeMemoryBarrier
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h
req.target-type: Desktop
req.target-min-winverclnt: 
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
req.lib: NtosKrnl.exe
req.dll: 
req.irql: Any level
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	wdm.h
apiname:
-	KeMemoryBarrier
product: Windows
targetos: Windows
req.typenames: WORK_QUEUE_TYPE
req.product: Windows 10 or later.
---

# KeMemoryBarrier function


## -description


The <b>KeMemoryBarrier</b> routine creates a barrier at its position in the code—across which the compiler and the processor cannot move any operations.


## -syntax


````
VOID KeMemoryBarrier(void);
````


## -parameters






## -returns



None




## -remarks



The <b>KeMemoryBarrier</b> routine inserts a memory barrier into your code. This barrier guarantees that every operation that appears in the source code before the call to <b>KeMemoryBarrier</b> will complete before any operation that appears after the call.

The implementation of the <b>KeMemoryBarrier</b> routine depends on the processor architecture. For example, for an x86 processor, the Wdm.h header file defines <b>KeMemoryBarrier</b> to be the following inline function:

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>FORCEINLINE
VOID
KeMemoryBarrier (
    VOID
    )
{
    LONG Barrier;

    __asm {
        xchg Barrier, eax
    }
}</pre>
</td>
</tr>
</table></span></div>
In this definition, the braces that follow the <b>__asm</b> keyword contain inline assembly code. The compiler optimizer cannot move an instruction from a position before the inline assembly code to a position after the inline assembly code, and vice versa. In addition, the <b>xchg</b> instruction implicitly includes the <b>lock</b> prefix, which forces the processor hardware to complete the memory operations for all instructions that precede the <b>xchg</b> instruction before it initiates memory operations for instructions that follow the <b>xchg</b> instruction.

<b>KeMemoryBarrier</b> prevents both the compiler and the processor from moving operations across the barrier. To prevent only the compiler from moving operations, call <a href="https://msdn.microsoft.com/library/windows/hardware/ff552973">KeMemoryBarrierWithoutFence</a>. 




## -see-also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff552973">KeMemoryBarrierWithoutFence</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20KeMemoryBarrier routine%20 RELEASE:%20(2/16/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

