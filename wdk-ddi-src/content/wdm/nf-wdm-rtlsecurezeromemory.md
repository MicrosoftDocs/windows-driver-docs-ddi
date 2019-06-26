---
UID: NF:wdm.RtlSecureZeroMemory
title: RtlSecureZeroMemory function (wdm.h)
description: The RtlSecureZeroMemory routine fills a block of memory with zeros in a way that is guaranteed to be secure.
old-location: kernel\rtlsecurezeromemory.htm
tech.root: kernel
ms.assetid: b7a9beaf-5eca-4fb0-af63-06c002297085
ms.date: 04/30/2018
ms.keywords: RtlSecureZeroMemory, RtlSecureZeroMemory routine [Kernel-Mode Driver Architecture], k109_8bcffbc1-2930-416b-a192-b70c477d1910.xml, kernel.rtlsecurezeromemory, wdm/RtlSecureZeroMemory
ms.topic: function
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h
req.target-type: Desktop
req.target-min-winverclnt: Available in Windows Server 2003 and later versions of Windows. (Because the routine is declared inline, the body of the routine can be included in earlier versions of the operating system.)
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
req.irql: Any level (See Remarks section)
topic_type:
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- Wdm.h
api_name:
- RtlSecureZeroMemory
product:
- Windows
targetos: Windows
req.typenames: 
---

# RtlSecureZeroMemory function


## -description


The <b>RtlSecureZeroMemory</b> routine fills a block of memory with zeros in a way that is guaranteed to be secure.


## -parameters




### -param ptr [out]

Pointer to the memory buffer to be filled with zeros.


### -param cnt [in]

Specifies the number of bytes to be filled with zeros.


## -returns



None




## -remarks



The effect of <b>RtlSecureZeroMemory</b> is identical to that of <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdm/nf-wdm-rtlzeromemory">RtlZeroMemory</a>, except that it is guaranteed to zero the memory location, even if it is not subsequently written to. (The compiler can optimize away a call to <b>RtlZeroMemory</b>, if it determines that the caller does not access that memory range again.)

Use <b>RtlSecureZeroMemory</b> to guarantee that sensitive information has been zeroed out. For example, suppose that a function uses a local array variable to store password information. Once the function exits, the password information can remain in the same memory location unless zeroed out by <b>RtlSecureZeroMemory</b>.

<b>RtlSecureZeroMemory</b> is slower than <b>RtlZeroMemory</b>; therefore, if security is not an issue, use <b>RtlZeroMemory</b> instead.

Callers of <b>RtlSecureZeroMemory</b> can be running at any IRQL if the <i>ptr</i> block is in nonpaged pool. Otherwise, the caller must be running at IRQL <= APC_LEVEL.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdm/nf-wdm-rtlfillmemory">RtlFillMemory</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdm/nf-wdm-rtlzeromemory">RtlZeroMemory</a>
 

 

