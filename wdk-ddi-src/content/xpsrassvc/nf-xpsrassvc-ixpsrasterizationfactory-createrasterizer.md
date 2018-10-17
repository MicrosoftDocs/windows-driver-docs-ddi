---
UID: NF:xpsrassvc.IXpsRasterizationFactory.CreateRasterizer
title: IXpsRasterizationFactory::CreateRasterizer
author: windows-driver-content
description: The CreateRasterize method creates an XPS rasterizer object.
old-location: print\ixpsrasterizationfactory_createrasterizer.htm
tech.root: print
ms.assetid: 07d4f1ed-5dbe-47c1-96e8-dfe21e0c1d0d
ms.date: 4/20/2018
ms.keywords: CreateRasterizer, CreateRasterizer method [Print Devices], CreateRasterizer method [Print Devices],IXpsRasterizationFactory interface, IXpsRasterizationFactory interface [Print Devices],CreateRasterizer method, IXpsRasterizationFactory.CreateRasterizer, IXpsRasterizationFactory::CreateRasterizer, print.ixpsrasterizationfactory_createrasterizer, print_xpsrast_5eddcd20-40a0-47da-8b1c-94d17902d783.xml, xpsrassvc/IXpsRasterizationFactory::CreateRasterizer
ms.topic: method
req.header: xpsrassvc.h
req.include-header: 
req.target-type: Desktop
req.target-min-winverclnt: Available in Windows 7 and later versions of the Windows operating system.
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
-	xpsrassvc.h
api_name:
-	IXpsRasterizationFactory.CreateRasterizer
product:
- Windows
targetos: Windows
req.typenames: 
---

# IXpsRasterizationFactory::CreateRasterizer


## -description


The <code>CreateRasterize</code> method creates an XPS rasterizer object.


## -parameters




### -param xpsPage [in, optional]

Pointer to an <b>IXpsOMPage</b> object that represents the XPS fixed page to render. This object encapsulates a FixedPage section from an XPS document. For more information about <b>IXpsOMPage</b>, see <a href="http://go.microsoft.com/fwlink/p/?linkid=146349">IXpsOMPage</a><u>.</u>


### -param DPI [in]

Dots per inch in the rasterized output. This parameter applies to both the x and y dimensions of the output bitmap. The <i>DPI</i> value is the resolution of the device that is to print or display the XPS fixed page.


### -param nonTextRenderingMode [in]

Rendering mode for nontext items in the rasterized output. This parameter indicates whether to generate antialiased output. Set this parameter to one of the following <a href="https://msdn.microsoft.com/library/windows/hardware/ff564291">XPSRAS_RENDERING_MODE</a> enumeration values:

<ul>
<li>
XPSRAS_RENDERING_MODE_ANTIALIASED

</li>
<li>
XPSRAS_RENDERING_MODE_ALIASED

</li>
</ul>

### -param textRenderingMode [in]

Rendering mode for text in the rasterized output. This parameter indicates whether to generate antialiased output. Set this parameter to one of the following XPSRAS_RENDERING_MODE enumeration values:

<ul>
<li>
XPSRAS_RENDERING_MODE_ANTIALIASED

</li>
<li>
XPSRAS_RENDERING_MODE_ALIASED

</li>
</ul>

### -param ppIXPSRasterizer [out, optional]

This parameter points to a location into which the method writes a pointer to the <a href="https://msdn.microsoft.com/1ef99120-2b3b-45aa-bcf7-16bcb9656089">IXpsRasterizer</a> interface of the newly created XPS rasterizer object. If the method fails, it writes <b>NULL</b> to this location and returns an error code.


## -returns



<code>CreateRasterizer</code> returns S_OK if the call was successful. Otherwise, the method returns an error code. Possible error return values include:

<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>E_POINTER</b></dt>
</dl>
</td>
<td width="60%">
Parameter <i>xpsPage</i> or <i>ppIXPSRasterizer</i> is <b>NULL</b>.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>E_INVALIDARG</b></dt>
</dl>
</td>
<td width="60%">
Parameter <i>nonTextRenderingMode</i> or <i>textRenderingMode</i> is not a valid XPSRAS_RENDERING_MODE enumeration value.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>E_OUTOFMEMORY</b></dt>
</dl>
</td>
<td width="60%">
Out of memory.

</td>
</tr>
</table>
 






## -remarks



This method is supported in Windows 7 and later. It is not supported in versions of the Windows operating system before Windows 7.

Typically, an XPSDrv filter in an XPS pipeline calls this method to obtain an XPS rasterizer. It then uses the rasterizer to rasterize the XPS fixed page encapsulated by the object to which the parameter <i>xpsPage</i> points .

The parameter <i>DPI</i> specifies the printer resolution, which is assumed to be the same in both the horizontal and vertical dimensions. The width and height of the XPS fixed page, which can be obtained from the <b>IXpsOMPage::GetPageDimensions</b> method, are expressed in 1/96-inch units. Multiply these width and height values by <i>DPI</i>/96 to determine the width and height, in pixels, of the rasterized page. For more information about <b>IXpsOMPage::GetPageDimensions</b>, see <a href="http://go.microsoft.com/fwlink/p/?linkid=146350">IXpsOMPage</a>. For more information about how the XPS rasterizer object uses the DPI value, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff556365">IXpsRasterizer::RasterizeRect</a>.

If successful, the method creates an XPS rasterizer object and passes to the caller a counted reference to the object's <b>IXpsRasterizer</b> interface. When the object is no longer needed, the caller is responsible for releasing the object by calling the <a href="http://go.microsoft.com/fwlink/p/?linkid=98433">Release</a> method on the object's <b>IXpsRasterizer</b> interface.

If the method fails and <i>ppIXPSRasterizer</i> is non-<b>NULL</b>, the method sets *<i>ppIXPSRasterizer</i> = <b>NULL</b>.

For a code example that calls the <code>CreateRasterizer</code> method, see the XPSRasFilter sample in the WDK. This sample is located in the Src\Print\Xpsrasfilter folder in your WDK installation.




## -see-also




<a href="https://msdn.microsoft.com/559bdc65-282e-42b2-998a-276202376c1e">IXpsRasterizationFactory</a>



<a href="https://msdn.microsoft.com/1ef99120-2b3b-45aa-bcf7-16bcb9656089">IXpsRasterizer</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff556365">IXpsRasterizer::RasterizeRect</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff564291">XPSRAS_RENDERING_MODE</a>
 

 

