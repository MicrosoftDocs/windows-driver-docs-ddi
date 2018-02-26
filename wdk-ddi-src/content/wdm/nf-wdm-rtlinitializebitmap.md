---
UID: NF:wdm.RtlInitializeBitMap
title: RtlInitializeBitMap function
author: windows-driver-content
description: The RtlInitializeBitMap routine initializes the header of a bitmap variable.
old-location: kernel\rtlinitializebitmap.htm
old-project: kernel
ms.assetid: 1e196ad1-5804-4d41-a273-18eb40e8f265
ms.author: windowsdriverdev
ms.date: 2/24/2018
ms.keywords: ",  , B, I, M, R, RtlInitializeBitMap, RtlInitializeBitMap routine [Kernel-Mode Driver Architecture], a, e, i, k109_2c98c30e-fc9f-422d-bfa8-e0d765677664.xml, kernel.rtlinitializebitmap, l, n, p, t, wdm/RtlInitializeBitMap, z"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h
req.target-type: Universal
req.target-min-winverclnt: Available starting with Windows 2000.
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
req.lib: NtosKrnl.lib
req.dll: NtosKrnl.exe (kernel mode); Ntdll.dll (user mode)
req.irql: "<= APC_LEVEL (see Remarks section)"
topictype:
-	APIRef
-	kbSyntax
apitype:
-	DllExport
apilocation:
-	NtosKrnl.exe
-	Ntdll.dll
apiname:
-	RtlInitializeBitMap
product: Windows
targetos: Windows
req.typenames: WORK_QUEUE_TYPE
req.product: Windows 10 or later.
---

# RtlInitializeBitMap function


## -description


The <b>RtlInitializeBitMap</b> routine initializes the header of a bitmap variable. 


## -syntax


````
VOID RtlInitializeBitMap(
  _Out_ PRTL_BITMAP BitMapHeader,
  _In_  PULONG      BitMapBuffer,
  _In_  ULONG       SizeOfBitMap
);
````


## -parameters




### -param BitMapHeader [out]

Pointer to an empty <a href="https://msdn.microsoft.com/library/windows/hardware/ff563614">RTL_BITMAP</a> structure. 


### -param BitMapBuffer [in]

Pointer to caller-allocated memory for the bitmap itself. The base address of this buffer must be ULONG-aligned. The size of the allocated buffer must be an integer multiple of <b>sizeof</b>(ULONG) bytes. 


### -param SizeOfBitMap [in]

Specifies the number of bits in the bitmap. This value can be any number of bits that will fit in the buffer allocated for the bitmap. 


## -returns



None




## -remarks



A driver can use a bitmap variable as an economical way to keep track of a set of reusable items. For example, file systems use a bitmap variable to track which clusters/sectors on a disk have already been allocated to hold file data. The system-supplied SCSI port driver uses a bitmap variable to track which queue tags have been assigned to SCSI request blocks (SRBs).

<b>RtlInitializeBitMap</b> must be called before any other <b>Rtl<i>Xxx</i></b> routine that operates on a bitmap variable. The <i>BitMapHeader</i> pointer is an input parameter in all subsequent <b>Rtl<i>Xxx</i></b> calls that operate on the caller's bitmap variable at <i>BitMapBuffer</i>. The caller is responsible for synchronizing access to the bitmap variable.

<b>RtlInitializeBitMap</b> initializes the caller-supplied <b>RTL_BITMAP</b> structure by copying the caller-supplied <i>BitMapBuffer</i> and <i>SizeOfBitMap</i> values into it. Subsequently, the structure can be passed to other routines to manipulate the bitmap. <b>RtlInitializeBitMap</b> does not modify the contents of the bitmap.

Callers of <b>RtlInitializeBitMap</b>, and callers of other <b>Rtl<i>Xxx</i></b> routines that operate on an initialized bitmap variable, must be running at IRQL &lt;= APC_LEVEL if the memory that contains the bitmap variable is pageable or the memory at <i>BitmapHeader</i> is pageable. Otherwise, <b>RtlInitializeBitMap</b> can be called at any IRQL.




## -see-also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff563614">RTL_BITMAP</a>



<a href="..\wdm\nf-wdm-rtlfindlastbackwardrunclear.md">RtlFindLastBackwardRunClear</a>



<a href="..\wdm\nf-wdm-rtlfindnextforwardrunclear.md">RtlFindNextForwardRunClear</a>



<a href="..\wdm\nf-wdm-rtlarebitsset.md">RtlAreBitsSet</a>



<a href="..\wdm\nf-wdm-rtlfindclearruns.md">RtlFindClearRuns</a>



<a href="..\wdm\nf-wdm-rtlarebitsclear.md">RtlAreBitsClear</a>



<a href="..\wdm\nf-wdm-rtlsetallbits.md">RtlSetAllBits</a>



<a href="..\wdm\nf-wdm-rtlfindsetbitsandclear.md">RtlFindSetBitsAndClear</a>



<a href="..\wdm\nf-wdm-rtlfindsetbits.md">RtlFindSetBits</a>



<a href="..\wdm\nf-wdm-rtlfindclearbitsandset.md">RtlFindClearBitsAndSet</a>



<a href="..\wdm\nf-wdm-rtlclearbits.md">RtlClearBits</a>



<a href="..\wdm\nf-wdm-rtlfindlongestrunclear.md">RtlFindLongestRunClear</a>



<a href="..\wdm\nf-wdm-rtlcheckbit.md">RtlCheckBit</a>



<a href="..\wdm\nf-wdm-rtlnumberofsetbits.md">RtlNumberOfSetBits</a>



<a href="..\wdm\nf-wdm-rtlclearallbits.md">RtlClearAllBits</a>



<a href="..\wdm\nf-wdm-rtlfindfirstrunclear.md">RtlFindFirstRunClear</a>



<a href="..\wdm\nf-wdm-rtlfindclearbits.md">RtlFindClearBits</a>



<a href="..\wdm\nf-wdm-rtlsetbits.md">RtlSetBits</a>



<a href="..\wdm\nf-wdm-rtlnumberofclearbits.md">RtlNumberOfClearBits</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20RtlInitializeBitMap routine%20 RELEASE:%20(2/24/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

