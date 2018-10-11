---
UID: NF:wdfcore.WDF_ALIGN_SIZE_DOWN
title: WDF_ALIGN_SIZE_DOWN function
author: windows-driver-content
description: The WDF_ALIGN_SIZE_DOWN function returns the next-lower buffer size that is aligned to a specified alignment offset.
old-location: wdf\wdf_align_size_down.htm
tech.root: wdf
ms.assetid: b93c6420-b981-4bfe-b841-921cbe76f643
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: DFMemoryObjectRef_2b1a76a0-3de8-4cfd-8a87-83a883a6fa95.xml, WDF_ALIGN_SIZE_DOWN, WDF_ALIGN_SIZE_DOWN function, kmdf.wdf_align_size_down, wdf.wdf_align_size_down, wdfcore/WDF_ALIGN_SIZE_DOWN
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: wdfcore.h
req.include-header: Wdf.h
req.target-type: Universal
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 1.0
req.umdf-ver: 2.0
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Wdf01000.sys (see Framework Library Versioning.)
req.dll: 
req.irql: Any IRQL.
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	LibDef
api_location:
-	Wdf01000.sys
-	Wdf01000.sys.dll
api_name:
-	WDF_ALIGN_SIZE_DOWN
product:
- Windows
targetos: Windows
req.typenames: 
---

# WDF_ALIGN_SIZE_DOWN function


## -description


<p class="CCE_Message">[Applies to KMDF and UMDF]</p>

The <b>WDF_ALIGN_SIZE_DOWN</b> function returns the next-lower buffer size that is aligned to a specified alignment offset.


## -parameters




### -param Length [in]

The length, in bytes, of a <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/using-memory-buffers">memory buffer</a>.


### -param AlignTo [in]

The alignment offset, in bytes. This value must be a power of 2, such as 2, 4, 8, 16, and so on.


## -returns



WDF_ALIGN_SIZE_DOWN returns the aligned buffer size, in bytes.




## -remarks



Drivers can use <a href="https://msdn.microsoft.com/library/windows/hardware/ff551217">WDF_ALIGN_SIZE_UP</a> or <b>WDF_ALIGN_SIZE_DOWN</b> to calculate a buffer size that is aligned to a specified alignment offset. This calculation is useful if your driver must allocate multiple contiguous buffers, if each buffer must begin at an address alignment boundary.


#### Examples

The following code example receives a buffer size and returns the size (either the current size or the next-lower size) that aligns to a DWORD address boundary.

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>bufferSizeAligned = WDF_ALIGN_SIZE_DOWN(bufferSize,
                                        sizeof(DWORD));</pre>
</td>
</tr>
</table></span></div>



## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff551217">WDF_ALIGN_SIZE_UP</a>
 

 

