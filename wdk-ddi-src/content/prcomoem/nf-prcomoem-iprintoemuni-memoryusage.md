---
UID: NF:prcomoem.IPrintOemUni.MemoryUsage
title: IPrintOemUni::MemoryUsage
author: windows-driver-content
description: The IPrintOemUni::MemoryUsage method can be used with Unidrv-supported printers to specify the amount of memory required for use by a rendering plug-in's IPrintOemUni::ImageProcessing method.
old-location: print\iprintoemuni_memoryusage.htm
old-project: print
ms.assetid: bdf9c43d-d747-40e8-86ba-976f3f6a19d6
ms.author: windowsdriverdev
ms.date: 4/20/2018
ms.keywords: IPrintOemUni interface [Print Devices],MemoryUsage method, IPrintOemUni.MemoryUsage, IPrintOemUni::MemoryUsage, MemoryUsage, MemoryUsage method [Print Devices], MemoryUsage method [Print Devices],IPrintOemUni interface, prcomoem/IPrintOemUni::MemoryUsage, print.iprintoemuni_memoryusage, print_unidrv-pscript_rendering_3c23be3a-ed61-452d-8bd9-0b9137ea777f.xml
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: method
req.header: prcomoem.h
req.include-header: Prcomoem.h
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
req.lib: 
req.dll: 
req.irql: 
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	COM
api_location:
-	prcomoem.h
api_name:
-	IPrintOemUni.MemoryUsage
product:
- Windows
targetos: Windows
req.typenames: 
---

# IPrintOemUni::MemoryUsage


## -description


The <code>IPrintOemUni::MemoryUsage</code> method can be used with Unidrv-supported printers to specify the amount of memory required for use by a rendering plug-in's <a href="https://msdn.microsoft.com/library/windows/hardware/ff554261">IPrintOemUni::ImageProcessing</a> method.


## -parameters




### -param pdevobj

Caller-supplied pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/ff547573">DEVOBJ</a> structure.


### -param pMemoryUsage

Caller-supplied pointer to an <a href="https://msdn.microsoft.com/library/windows/hardware/ff558669">OEMMEMORYUSAGE</a> structure.


## -returns



The method must return one of the following values.

<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>S_OK</b></dt>
</dl>
</td>
<td width="60%">
The operation succeeded.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>E_FAIL</b></dt>
</dl>
</td>
<td width="60%">
The operation failed.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>E_NOTIMPL</b></dt>
</dl>
</td>
<td width="60%">
The method is not implemented.

</td>
</tr>
</table>
 




## -remarks



The <code>IPrintOemUni::MemoryUsage</code> method's purpose is to help the Unidrv driver determine the optimum size for the GDI drawing surface, based on the memory requirements of the <a href="https://msdn.microsoft.com/library/windows/hardware/ff554261">IPrintOemUni::ImageProcessing</a> method. Implementation of the <code>IPrintOemUni::MemoryUsage</code> method is optional.

The <code>IPrintOemUni::MemoryUsage</code> method should return two values, as follows:

<ul>
<li>
The amount of permanently-allocated, fixed-sized memory that the <b>IPrintOemUni::ImageProcessing</b> method needs to allocate.

This value is returned in the <b>dwFixedMemoryUsage</b> member of the <a href="https://msdn.microsoft.com/library/windows/hardware/ff558669">OEMMEMORYUSAGE</a> structure.

</li>
<li>
The amount of memory required to hold a bitmap after the <b>IPrintOemUni::ImageProcessing</b> method has finished processing it.

The rendering plug-in either returns this processed bitmap to Unidrv, or spools it. The amount of memory required to store the processed bitmap is returned in the <b>dwPercentMemoryUsage</b> member of the OEMMEMORYUSAGE structure, and is expressed as a percentage of the source bitmap's size.

</li>
</ul>
The value returned in the <b>dwPercentMemoryUsage</b> member should include, in addition to the processed bitmap's size, the amount of any additional memory allocations that are dependent on the size of the source bitmap.

The <b>dwMaxBandSize</b> member of the OEMMEMORYUSAGE structure is supplied by Unidrv and specifies the default maximum band size.

Before the Unidrv driver creates a drawing surface, it requests GDI to determine the optimum size for image banding bitmaps, based on available system memory. This optimum memory space must be shared, for each banding bitmap, between a source bitmap that is passed to the <b>IPrintOemUni::ImageProcessing</b> method and a (typically smaller) processed bitmap that the method either returns or outputs. Unidrv calls the rendering plug-in's <code>IPrintOemUni::MemoryUsage</code> method, if it exists, and uses the result to calculate how best to divide the optimum memory space.

For example, suppose GDI reports that the optimum amount of memory to use for drawing is 6 megabytes (contained in the OEMMEMORYUSAGE structure's <b>dwMaxBandSize</b> member), while the rendering plug-in's <code>IPrintOemUni::MemoryUsage</code> method returns values of zero for <b>dwFixedMemoryUsage</b> and 50 for <b>dwPercentMemoryUsage</b>. The value of 50 means that the <b>IPrintOemUni::ImageProcessing</b> method's output bitmaps will be 50 percent smaller than the source bitmaps. Therefore, Unidrv will allocate a source bitmap size of 4 megabytes, thus causing output bitmaps to be 2 megabytes.

If an <code>IPrintOemUni::MemoryUsage</code> method is not provided, Unidrv allocates all the optimum available space to the source bitmap. This is acceptable if the <b>IPrintOemUni::ImageProcessing</b> method returns the processed bitmap in the memory space allocated for the source bitmap. However, if a rendering plug-in's <b>IPrintOemUni::ImageProcessing</b> method does allocate space for a destination bitmap but does not provide an <code>IPrintOemUni::MemoryUsage</code> method, the result is that more memory will be allocated for bitmaps than the optimum available size, potentially causing performance degradation.

The <code>IPrintOemUni::MemoryUsage</code> method is optional. If a rendering plug-in implements this method, the plug-in's <a href="https://msdn.microsoft.com/library/windows/hardware/ff554253">IPrintOemUni::GetImplementedMethod</a> method must return S_OK when it receives "MemoryUsage" as input.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff547573">DEVOBJ</a>



<a href="https://msdn.microsoft.com/097366a0-2ded-435c-9b63-2b736b716032">IPrintOemUni</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff554261">IPrintOemUni::ImageProcessing</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff558669">OEMMEMORYUSAGE</a>
 

 

