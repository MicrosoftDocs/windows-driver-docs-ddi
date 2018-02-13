---
UID: NF:wdfcore.WDF_ALIGN_SIZE_UP
title: WDF_ALIGN_SIZE_UP function
author: windows-driver-content
description: The WDF_ALIGN_SIZE_UP function returns the next-higher buffer size that is aligned to a specified alignment offset.
old-location: wdf\wdf_align_size_up.htm
old-project: wdf
ms.assetid: 68523004-c9f5-4038-985e-702d929cdf04
ms.author: windowsdriverdev
ms.date: 1/11/2018
ms.keywords: wdfcore/WDF_ALIGN_SIZE_UP, WDF_ALIGN_SIZE_UP function, wdf.wdf_align_size_up, kmdf.wdf_align_size_up, WDF_ALIGN_SIZE_UP, DFMemoryObjectRef_48452ee1-3939-48ba-a485-4d503ee052f3.xml
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	LibDef
apilocation:
-	Wdf01000.sys
-	Wdf01000.sys.dll
apiname:
-	WDF_ALIGN_SIZE_UP
product: Windows
targetos: Windows
req.typenames: WDF_DEVICE_SHUTDOWN_FLAGS
req.product: Windows 10 or later.
---

# WDF_ALIGN_SIZE_UP function


## -description


<p class="CCE_Message">[Applies to KMDF and UMDF]

The <b>WDF_ALIGN_SIZE_UP</b> function returns the next-higher buffer size that is aligned to a specified alignment offset.


## -syntax


````
size_t WDF_ALIGN_SIZE_UP(
  _In_ size_t Length,
  _In_ size_t AlignTo
);
````


## -parameters




### -param Length [in]

The length, in bytes, of a <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/using-memory-buffers">memory buffer</a>.


### -param AlignTo [in]

The alignment offset, in bytes. This value must be a power of 2, such as 2, 4, 8, 16, and so on.


## -returns



<b>WDF_ALIGN_SIZE_UP</b> returns the aligned buffer size, in bytes.




## -remarks



Drivers can use <b>WDF_ALIGN_SIZE_UP</b> or <a href="..\wdfcore\nf-wdfcore-wdf_align_size_down.md">WDF_ALIGN_SIZE_DOWN</a> to calculate a buffer size that is aligned to a specified alignment offset. This calculation is useful if your driver must allocate multiple contiguous buffers, if each buffer must begin at an address alignment boundary.

If the value of either input parameter is too large, arithmetic overflow causes <b>WDF_ALIGN_SIZE_UP</b> to return an invalid value that is smaller than <i>Length</i>. Your code should test for this condition.


#### Examples

The following code example receives a buffer size and returns the size (either the current size or the next-higher size) that aligns to a DWORD address boundary.

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>bufferSizeAligned = WDF_ALIGN_SIZE_UP(bufferSize,
                                      sizeof(DWORD));
if (bufferSizeAligned &lt; bufferSize)
{
    // Buffer too large.
    ...
}</pre>
</td>
</tr>
</table></span></div>



## -see-also

<a href="..\wdfcore\nf-wdfcore-wdf_align_size_down.md">WDF_ALIGN_SIZE_DOWN</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [wdf\wdf]:%20WDF_ALIGN_SIZE_UP function%20 RELEASE:%20(1/11/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

