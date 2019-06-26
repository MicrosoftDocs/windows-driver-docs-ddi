---
UID: NF:prcomoem.IPrintOemUni3.GetPDEVAdjustment
title: IPrintOemUni3::GetPDEVAdjustment (prcomoem.h)
description: The IPrintOemUni3::GetPDEVAdjustment method enables a plug-in to override specific PDEV settings.
old-location: print\iprintoemuni3_getpdevadjustment.htm
tech.root: print
ms.assetid: bb7d7248-9520-4bc8-8483-b05b78608fc7
ms.date: 04/20/2018
ms.keywords: GetPDEVAdjustment, GetPDEVAdjustment method [Print Devices], GetPDEVAdjustment method [Print Devices],IPrintOemUni3 interface, IPrintOemUni3 interface [Print Devices],GetPDEVAdjustment method, IPrintOemUni3.GetPDEVAdjustment, IPrintOemUni3::GetPDEVAdjustment, prcomoem/IPrintOemUni3::GetPDEVAdjustment, print.iprintoemuni3_getpdevadjustment, print_unidrv-pscript_rendering_d30dca0e-9e1d-4d42-9f9d-e6abd364da96.xml
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
- APIRef
- kbSyntax
api_type:
- COM
api_location:
- prcomoem.h
api_name:
- IPrintOemUni3.GetPDEVAdjustment
product:
- Windows
targetos: Windows
req.typenames: 
---

# IPrintOemUni3::GetPDEVAdjustment


## -description


The <code>IPrintOemUni3::GetPDEVAdjustment</code> method enables a plug-in to override specific <a href="https://docs.microsoft.com/windows-hardware/drivers/">PDEV</a> settings.


## -parameters




### -param pdevobj

Pointer to a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/printoem/ns-printoem-_devobj">DEVOBJ</a> structure.


### -param dwAdjustType

Specifies the type of adjustment asked for. The following flags are currently supported.

<table>
<tr>
<th>Flag</th>
<th>Meaning</th>
</tr>
<tr>
<td>
PDEV_ADJUST_GRAPHICS_RESOLUTION_TYPE

</td>
<td>
Adjust the graphics resolution setting that is reported in the PDEV structure. For more information, see the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/printoem/ns-printoem-_pdev_adjust_graphics_resolution">PDEV_ADJUST_GRAPHICS RESOLUTION</a> structure.

</td>
</tr>
<tr>
<td>
PDEV_IMAGEABLE_ORIGIN_AREA_TYPE

</td>
<td>
Adjust the imageable origin area that is reported in the PDEV structure. For more information, see the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/printoem/ns-printoem-_pdev_adjust_imageable_origin_area">PDEV_ADJUST_IMAGEABLE_ORIGIN_AREA</a> structure.

</td>
</tr>
<tr>
<td>
PDEV_ADJUST_PHYSICAL_PAPER_SIZE_TYPE

</td>
<td>
Adjust the physical paper size that is reported in the PDEV structure. For more information, see the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/printoem/ns-printoem-_pdev_adjust_physical_paper_size">PDEV_ADJUST_PAPER_PHYSICAL_SIZE</a> structure.

</td>
</tr>
</table>
 


### -param pBuf

Pointer to a structure that contains the planned settings that are used if there is no change. These structures are listed in the preceding table. The plug-in can overwrite the settings in the relevant structure.


### -param cbBuffer

Specifies the size, in bytes, of the structure pointed to by <i>pBuf</i>.


### -param pbAdjustmentDone [out]

Pointer to a memory location that the plug-in sets to <b>TRUE</b> when it actually changes a value in the buffer. This may be used by the driver for optimizations.


## -returns



The <code>IPrintOemUni3::GetPDEVAdjustment</code> method should return S_OK if it recognizes the adjustment type, and S_FALSE if it does not. If the method fails, it should return E_FAIL. The chain of plug-ins is called until either S_OK or a failure code other than E_NOTIMPL is returned. That is, the chain of plug-ins is called until the first plug-in that is capable of handling the adjustment is found.




## -remarks



This function is available in Windows Vista and later.

Currently, the Unidrv driver calls <code>IPrintOemUni3::GetPDEVAdjustment</code> to adjust the graphics resolution setting, as reported in the PDEV, to adjust the imageable origin area, or to adjust the physical paper size.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/prcomoem/nn-prcomoem-iprintoemuni3">IPrintOemUni3</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/printoem/ns-printoem-_pdev_adjust_graphics_resolution">PDEV_ADJUST_GRAPHICS RESOLUTION</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/printoem/ns-printoem-_pdev_adjust_imageable_origin_area">PDEV_ADJUST_IMAGEABLE_ORIGIN_AREA</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/printoem/ns-printoem-_pdev_adjust_paper_margin">PDEV_ADJUST_PAPER_MARGIN</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/printoem/ns-printoem-_pdev_adjust_physical_paper_size">PDEV_ADJUST_PAPER_PHYSICAL_SIZE</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/printoem/ns-printoem-_pdev_hostfont_enabled">PDEV_HOSTFONT_ENABLED</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/printoem/ns-printoem-_pdev_use_true_color">PDEV_USE_TRUE_COLOR</a>
 

 

