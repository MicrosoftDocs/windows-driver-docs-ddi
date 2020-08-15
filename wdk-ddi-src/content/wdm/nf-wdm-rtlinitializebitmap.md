---
UID: NF:wdm.RtlInitializeBitMap
title: RtlInitializeBitMap function (wdm.h)
description: The RtlInitializeBitMap routine initializes the header of a bitmap variable.
old-location: kernel\rtlinitializebitmap.htm
tech.root: kernel
ms.assetid: 1e196ad1-5804-4d41-a273-18eb40e8f265
ms.date: 04/30/2018
keywords: ["RtlInitializeBitMap function"]
ms.keywords: RtlInitializeBitMap, RtlInitializeBitMap routine [Kernel-Mode Driver Architecture], k109_2c98c30e-fc9f-422d-bfa8-e0d765677664.xml, kernel.rtlinitializebitmap, wdm/RtlInitializeBitMap
f1_keywords:
 - "wdm/RtlInitializeBitMap"
 - "RtlInitializeBitMap"
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
req.irql: Any IRQL if BitMapHeader is memory-resident; <= APC_LEVEL if BitMapHeader is pageable or on Windows 7 and earlier
topic_type:
- APIRef
- kbSyntax
api_type:
- DllExport
api_location:
- NtosKrnl.exe
- Ntdll.dll
api_name:
- RtlInitializeBitMap
targetos: Windows
req.typenames: 
---

# RtlInitializeBitMap function


## -description


The <b>RtlInitializeBitMap</b> routine initializes the header of a bitmap variable. 


## -parameters




### -param BitMapHeader 
[out]
Pointer to an empty <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/eprocess">RTL_BITMAP</a> structure. 


### -param BitMapBuffer 
[in]
Pointer to caller-allocated memory for the bitmap itself. The base address of this buffer must be ULONG-aligned. The size of the allocated buffer must be an integer multiple of <b>sizeof</b>(ULONG) bytes. 


### -param SizeOfBitMap 
[in]
Specifies the number of bits in the bitmap. This value can be any number of bits that will fit in the buffer allocated for the bitmap. 


## -returns



None




## -remarks



A driver can use a bitmap variable as an economical way to keep track of a set of reusable items. For example, file systems use a bitmap variable to track which clusters/sectors on a disk have already been allocated to hold file data. The system-supplied SCSI port driver uses a bitmap variable to track which queue tags have been assigned to SCSI request blocks (SRBs).

<b>RtlInitializeBitMap</b> must be called before any other <b>Rtl<i>Xxx</i></b> routine that operates on a bitmap variable. The <i>BitMapHeader</i> pointer is an input parameter in all subsequent <b>Rtl<i>Xxx</i></b> calls that operate on the caller's bitmap variable at <i>BitMapBuffer</i>. The caller is responsible for synchronizing access to the bitmap variable.

<b>RtlInitializeBitMap</b> initializes the caller-supplied <b>RTL_BITMAP</b> structure by copying the caller-supplied <i>BitMapBuffer</i> and <i>SizeOfBitMap</i> values into it. Subsequently, the structure can be passed to other routines to manipulate the bitmap. <b>RtlInitializeBitMap</b> does not modify the contents of the bitmap.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/eprocess">RTL_BITMAP</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-rtlarebitsclear">RtlAreBitsClear</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-rtlarebitsset">RtlAreBitsSet</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-rtlcheckbit">RtlCheckBit</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-rtlclearallbits">RtlClearAllBits</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-rtlclearbits">RtlClearBits</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-rtlfindclearbits">RtlFindClearBits</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-rtlfindclearbitsandset">RtlFindClearBitsAndSet</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-rtlfindclearruns">RtlFindClearRuns</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-rtlfindfirstrunclear">RtlFindFirstRunClear</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-rtlfindlastbackwardrunclear">RtlFindLastBackwardRunClear</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-rtlfindlongestrunclear">RtlFindLongestRunClear</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-rtlfindnextforwardrunclear">RtlFindNextForwardRunClear</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-rtlfindsetbits">RtlFindSetBits</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-rtlfindsetbitsandclear">RtlFindSetBitsAndClear</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-rtlnumberofclearbits">RtlNumberOfClearBits</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-rtlnumberofsetbits">RtlNumberOfSetBits</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-rtlsetallbits">RtlSetAllBits</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-rtlsetbits">RtlSetBits</a>
 

 

