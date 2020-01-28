---
UID: NF:ntifs.KeGetProcessorNumberFromIndex
title: KeGetProcessorNumberFromIndex function (ntifs.h)
description: The KeGetProcessorNumberFromIndex routine converts a systemwide processor index to a group number and a group-relative processor number.
old-location: kernel\kegetprocessornumberfromindex.htm
tech.root: kernel
ms.assetid: a6c9a7fa-8fef-4d6d-aab5-e712c49c0144
ms.date: 04/30/2018
ms.keywords: KeGetProcessorNumberFromIndex, KeGetProcessorNumberFromIndex routine [Kernel-Mode Driver Architecture], k105_c0b567bd-4436-4f6a-87a2-86d8b165e2dc.xml, kernel.kegetprocessornumberfromindex, wdm/KeGetProcessorNumberFromIndex
f1_keywords:
 - "ntifs/KeGetProcessorNumberFromIndex"
req.header: ntifs.h
req.include-header: Ntddk.h, Wdm.h, Ntddk.h, Ntifs.h
req.target-type: Universal
req.target-min-winverclnt: Available in Windows 7 and later versions of Windows.
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
req.dll: NtosKrnl.exe
req.irql: Any level
topic_type:
- APIRef
- kbSyntax
api_type:
- DllExport
api_location:
- NtosKrnl.exe
api_name:
- KeGetProcessorNumberFromIndex
product:
- Windows
targetos: Windows
req.typenames: 
---

# KeGetProcessorNumberFromIndex function


## -description


The <b>KeGetProcessorNumberFromIndex</b> routine converts a systemwide processor index to a group number and a group-relative processor number.


## -parameters




### -param ProcIndex [in]

A systemwide processor index. If a multiprocessor system contains a total of <i>n</i> logical processors, valid processor indexes range from 0 to <i>n</i>-1. 


### -param ProcNumber [out]

A pointer to a caller-allocated <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/miniport/ns-miniport-_processor_number">PROCESSOR_NUMBER</a> structure into which the routine writes the group number and group-relative processor number of the processor that is identified by <i>ProcIndex</i>. 


## -returns



<b>KeGetProcessorNumberFromIndex</b> returns STATUS_SUCCESS if the call is successful. Possible error return values include the following:

<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INVALID_PARAMETER</b></dt>
</dl>
</td>
<td width="60%">
The <i>ProcIndex</i> parameter value is not a valid processor index.

</td>
</tr>
</table>
 




## -remarks



This routine accepts as input a processor index that identifies the processor across the entire multiprocessor system. The output value is a <b>PROCESSOR_NUMBER</b> structure that identifies a processor by its group number and its processor number within the group.

For example, if a multiprocessor system contains two groups, and each group contains 64 logical processors, the processor numbers in each group range from 0 to 63, but the systemwide processor indexes range from 0 to 127.

To obtain the total number of active logical processors in the system, call the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddk/nf-ntddk-kequeryactiveprocessorcountex">KeQueryActiveProcessorCountEx</a> routine.

The <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntifs/nf-ntifs-kegetprocessorindexfromnumber">KeGetProcessorIndexFromNumber</a> routine converts a group number and a group-relative processor number to a systemwide processor index.


#### Examples

The following code example uses the <b>KeQueryActiveProcessorCountEx</b> and <b>KeGetProcessorNumberFromIndex</b> routines to enumerate all active logical processors in the system:

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>ULONG Count;
ULONG ProcIndex;
PROCESSOR_NUMBER ProcNumber;

Count = KeQueryActiveProcessorCountEx(ALL_PROCESSOR_GROUPS);
for (ProcIndex = 0; ProcIndex < Count; ProcIndex += 1)
{
    KeGetProcessorNumberFromIndex(ProcIndex, &ProcNumber);

    // Do something with the contents of ProcNumber.
    ...
}</pre>
</td>
</tr>
</table></span></div>
The constant value ALL_PROCESSOR_GROUPS is defined in Winnt.h and Ntdef.h. 

<div class="code"></div>



## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntifs/nf-ntifs-kegetprocessorindexfromnumber">KeGetProcessorIndexFromNumber</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddk/nf-ntddk-kequeryactiveprocessorcountex">KeQueryActiveProcessorCountEx</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/miniport/ns-miniport-_processor_number">PROCESSOR_NUMBER</a>
 

 

