---
UID: NF:xpsrassvc.IXpsRasterizationFactory.CreateRasterizer
title: IXpsRasterizationFactory::CreateRasterizer method
author: windows-driver-content
description: The CreateRasterize method creates an XPS rasterizer object.
old-location: print\ixpsrasterizationfactory_createrasterizer.htm
old-project: print
ms.assetid: 07d4f1ed-5dbe-47c1-96e8-dfe21e0c1d0d
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: CreateRasterizer method [Print Devices], CreateRasterizer method [Print Devices], IXpsRasterizationFactory interface, CreateRasterizer,IXpsRasterizationFactory.CreateRasterizer, IXpsRasterizationFactory, IXpsRasterizationFactory interface [Print Devices], CreateRasterizer method, IXpsRasterizationFactory::CreateRasterizer, print.ixpsrasterizationfactory_createrasterizer, print_xpsrast_5eddcd20-40a0-47da-8b1c-94d17902d783.xml, xpsrassvc/IXpsRasterizationFactory::CreateRasterizer
ms.prod: windows-hardware
ms.technology: windows-devices
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
req.lib: xpsrassvc.h
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
product: Windows
targetos: Windows
req.typenames: XPSRAS_BACKGROUND_COLOR
req.product: Windows 10 or later.
---

# IXpsRasterizationFactory::CreateRasterizer method


## -description


The <code>CreateRasterize</code> method creates an XPS rasterizer object.


## -syntax


````
HRESULT CreateRasterizer(
  [in, optional]  IXpsOMPage            *xpsPage,
  [in]            FLOAT                 DPI,
  [in]            XPSRAS_RENDERING_MODE nonTextRenderingMode,
  [in]            XPSRAS_RENDERING_MODE textRenderingMode,
  [out, optional] IXpsRasterizer        **ppIXPSRasterizer
);
````


## -parameters




### -param xpsPage [in, optional]

Pointer to an <b>IXpsOMPage</b> object that represents the XPS fixed page to render. This object encapsulates a FixedPage section from an XPS document. For more information about <b>IXpsOMPage</b>, see <a href="http://go.microsoft.com/fwlink/p/?linkid=146349">IXpsOMPage</a><u>.</u>


### -param DPI [in]

Dots per inch in the rasterized output. This parameter applies to both the x and y dimensions of the output bitmap. The <i>DPI</i> value is the resolution of the device that is to print or display the XPS fixed page.


### -param nonTextRenderingMode [in]

Rendering mode for nontext items in the rasterized output. This parameter indicates whether to generate antialiased output. Set this parameter to one of the following <a href="..\xpsrassvc\ne-xpsrassvc-__midl___midl_itf_xpsrassvc_0000_0001_0001.md">XPSRAS_RENDERING_MODE</a> enumeration values:

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

This parameter points to a location into which the method writes a pointer to the <a href="..\xpsrassvc\nn-xpsrassvc-ixpsrasterizer.md">IXpsRasterizer</a> interface of the newly created XPS rasterizer object. If the method fails, it writes <b>NULL</b> to this location and returns an error code.


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

<a href="..\xpsrassvc\nn-xpsrassvc-ixpsrasterizationfactory.md">IXpsRasterizationFactory</a>



<a href="..\xpsrassvc\ne-xpsrassvc-__midl___midl_itf_xpsrassvc_0000_0001_0001.md">XPSRAS_RENDERING_MODE</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff556365">IXpsRasterizer::RasterizeRect</a>



<a href="..\xpsrassvc\nn-xpsrassvc-ixpsrasterizer.md">IXpsRasterizer</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [print\print]:%20IXpsRasterizationFactory::CreateRasterizer method%20 RELEASE:%20(2/26/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

