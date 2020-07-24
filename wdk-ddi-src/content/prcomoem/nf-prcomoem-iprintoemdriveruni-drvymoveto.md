---
UID: NF:prcomoem.IPrintOemDriverUni.DrvYMoveTo
title: IPrintOemDriverUni::DrvYMoveTo (prcomoem.h)
description: The IPrintOemDriverUni::DrvYMoveTo method is provided by the Unidrv driver so that a rendering plug-in can notify the driver of cursor y-position changes.
old-location: print\iprintoemdriveruni_drvymoveto.htm
tech.root: print
ms.assetid: ce9b1622-4c02-4496-82ca-cefa49d531da
ms.date: 04/20/2018
keywords: ["IPrintOemDriverUni::DrvYMoveTo"]
ms.keywords: DrvYMoveTo, DrvYMoveTo method [Print Devices], DrvYMoveTo method [Print Devices],IPrintOemDriverUni interface, IPrintOemDriverUni interface [Print Devices],DrvYMoveTo method, IPrintOemDriverUni.DrvYMoveTo, IPrintOemDriverUni::DrvYMoveTo, prcomoem/IPrintOemDriverUni::DrvYMoveTo, print.iprintoemdriveruni_drvymoveto, print_unidrv-pscript_rendering_ebfa0991-ad14-4303-9702-2b19962da5e6.xml
f1_keywords:
 - "prcomoem/IPrintOemDriverUni.DrvYMoveTo"
 - "IPrintOemDriverUni.DrvYMoveTo"
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
- APIRef
- kbSyntax
api_type:
- COM
api_location:
- prcomoem.h
api_name:
- IPrintOemDriverUni.DrvYMoveTo
targetos: Windows
req.typenames: 
---

# IPrintOemDriverUni::DrvYMoveTo


## -description


The <code>IPrintOemDriverUni::DrvYMoveTo</code> method is provided by the Unidrv driver so that a <a href="https://docs.microsoft.com/windows-hardware/drivers/print/rendering-plug-ins">rendering plug-in</a> can notify the driver of cursor y-position changes.


## -parameters




### -param pdevobj

Caller-supplied pointer to a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/printoem/ns-printoem-_devobj">DEVOBJ</a> structure.


### -param y

Caller-supplied value representing the number of units the cursor should be moved. The unit is defined by the MV_GRAPHICS flags in <i>dwFlags</i>.


### -param dwFlags

One or more of the following caller-supplied bit flags:

<table>
<tr>
<th>Flag</th>
<th>Definition</th>
</tr>
<tr>
<td>
MV_GRAPHICS

</td>
<td>
If set, the <i>y</i> parameter's value is expressed in dots, based on the printer's current resolution. For example, if the y resolution is 150 DPI and <i>y</i> is 75, the movement is ?? inch.

If not set, the <i>y</i> parameter's value is expressed in master units. For example, if the y master unit is 600 and <i>y</i> is 300, the movement is ?? inch.

</td>
</tr>
<tr>
<td>
MV_PHYSICAL

</td>
<td>
If set, the <i>y</i> parameter's value is relative to the cursor origin.

If not set, the <i>y</i> parameter's value is relative to the printable area's origin.

Cannot be set if MV_RELATIVE is set.

</td>
</tr>
<tr>
<td>
MV_RELATIVE

</td>
<td>
If set, specifies that the cursor should be moved <i>y</i> units from its current position.

If not set, specifies that the cursor should be moved <i>y</i> units from its origin.

</td>
</tr>
<tr>
<td>
MV_UPDATE

</td>
<td>
If set, specifies that Unidrv should update its current calculation of the cursor position without actually moving the cursor. (Should be set if <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/prcomoem/nf-prcomoem-iprintoemuni-imageprocessing">IPrintOemUni::ImageProcessing</a> has moved the cursor.)

If not set, specifies that Unidrv should update its current calculation of the cursor position and also move the cursor.

</td>
</tr>
</table>
 


### -param piResult [out]

Receives the method-supplied result of subtracting the actual new cursor position from the requested new cursor position. This value might be zero, but it is always nonnegative.


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



The <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/prcomoem/nf-prcomoem-iprintoemdriveruni-drvxmoveto">IPrintOemDriverUni::DrvXMoveTo</a> and <code>IPrintOemDriverUni::DrvYMoveTo</code> methods allow a rendering plug-in to send image data to the printer spooler without causing the printer driver to lose track of the printer's cursor position. If you provide an <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/prcomoem/nf-prcomoem-iprintoemuni-imageprocessing">IPrintOemUni::ImageProcessing</a> method that sends image data directly to the print spooler instead of returning it to the printer driver, the method should call <code>IPrintOemDriverUni::DrvXMoveTo</code> and <code>IPrintOemDriverUni::DrvYMoveTo</code>.

Either of two techniques can be used for updating the cursor position:

<ul>
<li>
Whenever an <b>IPrintOemUni::ImageProcessing</b> method needs to update the cursor position, it can call <code>IPrintOemDriverUni::DrvXMoveTo</code> or <code>IPrintOemDriverUni::DrvYMoveTo</code> with the MV_UPDATE flag cleared. This causes Unidrv to send cursor commands to the print spooler and to update its internal calculation of the current cursor position.

</li>
<li>
The <b>IPrintOemUni::ImageProcessing</b> method can update the cursor by sending cursor commands directly to the print spooler. When the method has finished its spooling operation, it can call <code>IPrintOemDriverUni::DrvXMoveTo</code> or <code>IPrintOemDriverUni::DrvYMoveTo</code> with the MV_UPDATE flag set. This causes Unidrv to update its internal calculation of the current cursor position without sending cursor commands to the print spooler.

</li>
</ul>


