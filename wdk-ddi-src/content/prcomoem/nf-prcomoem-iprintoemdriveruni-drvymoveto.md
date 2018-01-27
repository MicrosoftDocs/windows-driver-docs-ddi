---
UID: NF:prcomoem.IPrintOemDriverUni.DrvYMoveTo
title: IPrintOemDriverUni::DrvYMoveTo method
author: windows-driver-content
description: The IPrintOemDriverUni::DrvYMoveTo method is provided by the Unidrv driver so that a rendering plug-in can notify the driver of cursor y-position changes.
old-location: print\iprintoemdriveruni_drvymoveto.htm
old-project: print
ms.assetid: ce9b1622-4c02-4496-82ca-cefa49d531da
ms.author: windowsdriverdev
ms.date: 1/18/2018
ms.keywords: print_unidrv-pscript_rendering_ebfa0991-ad14-4303-9702-2b19962da5e6.xml, IPrintOemDriverUni, prcomoem/IPrintOemDriverUni::DrvYMoveTo, IPrintOemDriverUni::DrvYMoveTo, print.iprintoemdriveruni_drvymoveto, DrvYMoveTo, DrvYMoveTo method [Print Devices], IPrintOemDriverUni interface [Print Devices], DrvYMoveTo method, DrvYMoveTo method [Print Devices], IPrintOemDriverUni interface
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
req.lib: prcomoem.h
req.dll: 
req.irql: 
topictype: 
-	APIRef
-	kbSyntax
apitype: 
-	COM
apilocation: 
-	prcomoem.h
apiname: 
-	IPrintOemDriverUni.DrvYMoveTo
product: Windows
targetos: Windows
req.typenames: *POEMPTOPTS, OEMPTOPTS
req.product: Windows 10 or later.
---

# IPrintOemDriverUni::DrvYMoveTo method


## -description


The <code>IPrintOemDriverUni::DrvYMoveTo</code> method is provided by the Unidrv driver so that a <a href="https://msdn.microsoft.com/e55ca083-2790-4929-9e5b-6fce49eb0404">rendering plug-in</a> can notify the driver of cursor y-position changes.


## -syntax


````
HRESULT DrvYMoveTo(
        PDEVOBJ pdevobj,
        INT     y,
        DWORD   dwFlags,
  [out] INT     *piResult
);
````


## -parameters




### -param pdevobj

Caller-supplied pointer to a <a href="..\printoem\ns-printoem-_devobj.md">DEVOBJ</a> structure.


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
If set, specifies that Unidrv should update its current calculation of the cursor position without actually moving the cursor. (Should be set if <a href="https://msdn.microsoft.com/library/windows/hardware/ff554261">IPrintOemUni::ImageProcessing</a> has moved the cursor.)

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


The <a href="https://msdn.microsoft.com/library/windows/hardware/ff553141">IPrintOemDriverUni::DrvXMoveTo</a> and <code>IPrintOemDriverUni::DrvYMoveTo</code> methods allow a rendering plug-in to send image data to the printer spooler without causing the printer driver to lose track of the printer's cursor position. If you provide an <a href="https://msdn.microsoft.com/library/windows/hardware/ff554261">IPrintOemUni::ImageProcessing</a> method that sends image data directly to the print spooler instead of returning it to the printer driver, the method should call <code>IPrintOemDriverUni::DrvXMoveTo</code> and <code>IPrintOemDriverUni::DrvYMoveTo</code>.

Either of two techniques can be used for updating the cursor position:
<ul>
<li>
Whenever an <b>IPrintOemUni::ImageProcessing</b> method needs to update the cursor position, it can call <code>IPrintOemDriverUni::DrvXMoveTo</code> or <code>IPrintOemDriverUni::DrvYMoveTo</code> with the MV_UPDATE flag cleared. This causes Unidrv to send cursor commands to the print spooler and to update its internal calculation of the current cursor position.

</li>
<li>
The <b>IPrintOemUni::ImageProcessing</b> method can update the cursor by sending cursor commands directly to the print spooler. When the method has finished its spooling operation, it can call <code>IPrintOemDriverUni::DrvXMoveTo</code> or <code>IPrintOemDriverUni::DrvYMoveTo</code> with the MV_UPDATE flag set. This causes Unidrv to update its internal calculation of the current cursor position without sending cursor commands to the print spooler.

</li>
</ul>

