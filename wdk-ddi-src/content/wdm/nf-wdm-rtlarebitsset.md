---
UID: NF:wdm.RtlAreBitsSet
title: RtlAreBitsSet function
author: windows-driver-content
description: The RtlAreBitsSet routine determines whether a given range of bits within a bitmap variable is set.
old-location: kernel\rtlarebitsset.htm
old-project: kernel
ms.assetid: 7343f619-cf89-4768-b488-fe95f1da749d
ms.author: windowsdriverdev
ms.date: 1/4/2018
ms.keywords: RtlAreBitsSet
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
req.alt-api: RtlAreBitsSet
req.alt-loc: NtosKrnl.exe
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: NtosKrnl.lib
req.dll: NtosKrnl.exe
req.irql: <= APC_LEVEL (See Remarks section)
req.typenames: WORK_QUEUE_TYPE
req.product: Windows 10 or later.
---

# RtlAreBitsSet function



## -description
The <b>RtlAreBitsSet</b> routine determines whether a given range of bits within a bitmap variable is set. 



## -syntax

````
BOOLEAN RtlAreBitsSet(
  _In_ PRTL_BITMAP BitMapHeader,
  _In_ ULONG       StartingIndex,
  _In_ ULONG       Length
);
````


## -parameters

### -param BitMapHeader [in]

A pointer to the <a href="https://msdn.microsoft.com/library/windows/hardware/ff563614">RTL_BITMAP</a> structure that describes the bitmap. This structure must have been initialized by the <a href="..\wdm\nf-wdm-rtlinitializebitmap.md">RtlInitializeBitMap</a> routine. 


### -param StartingIndex [in]

Specifies the start of the bit range to be tested. This is a zero-based value indicating the position of the first bit in the range. 


### -param Length [in]

Specifies how many bits to test. 


## -returns
<b>RtlAreBitsSet</b> returns <b>TRUE</b> if <i>Length </i>consecutive bits beginning at <i>StartingIndex</i> are set (that is, all the bits from <i>StartingIndex </i>to (<i>StartingIndex </i>+ <i>Length</i>)). It returns <b>FALSE</b> if any bit in the given range is clear, if the given range is not a proper subset of the bitmap, or if the given <i>Length</i> is zero. 


## -remarks
Callers of <b>RtlAreBitsSet</b> must be running at IRQL &lt;= APC_LEVEL if the memory that contains the bitmap variable is pageable or the memory at <i>BitMapHeader</i> is pageable. Otherwise, <b>RtlAreBitsSet</b> can be called at any IRQL.


## -see-also
<dl>
<dt>
<a href="..\wdm\nf-wdm-rtlarebitsclear.md">RtlAreBitsClear</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff563614">RTL_BITMAP</a>
</dt>
<dt>
<a href="..\wdm\nf-wdm-rtlcheckbit.md">RtlCheckBit</a>
</dt>
<dt>
<a href="..\wdm\nf-wdm-rtlfindsetbits.md">RtlFindSetBits</a>
</dt>
<dt>
<a href="..\wdm\nf-wdm-rtlinitializebitmap.md">RtlInitializeBitMap</a>
</dt>
<dt>
<a href="..\wdm\nf-wdm-rtlsetallbits.md">RtlSetAllBits</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20RtlAreBitsSet routine%20 RELEASE:%20(1/4/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

