---
UID: NF:prcomoem.IPrintOemPS2.GetPDEVAdjustment
title: IPrintOemPS2::GetPDEVAdjustment method
author: windows-driver-content
description: The IPrintOemPS2::GetPDEVAdjustment method enables a plug-in to override specific PDEV settings.
old-location: print\iprintoemps2_getpdevadjustment.htm
old-project: print
ms.assetid: 8dc4252f-72d5-47ae-9f43-8006aa71c29d
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: GetPDEVAdjustment method [Print Devices], GetPDEVAdjustment method [Print Devices], IPrintOemPS2 interface, GetPDEVAdjustment,IPrintOemPS2.GetPDEVAdjustment, IPrintOemPS2, IPrintOemPS2 interface [Print Devices], GetPDEVAdjustment method, IPrintOemPS2::GetPDEVAdjustment, prcomoem/IPrintOemPS2::GetPDEVAdjustment, print.iprintoemps2_getpdevadjustment, print_unidrv-pscript_rendering_eca8e6af-1563-4028-9d87-fd014e1e06ee.xml
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
-	IPrintOemPS2.GetPDEVAdjustment
product: Windows
targetos: Windows
req.typenames: OEMPTOPTS, *POEMPTOPTS
req.product: Windows 10 or later.
---

# IPrintOemPS2::GetPDEVAdjustment method


## -description


The <code>IPrintOemPS2::GetPDEVAdjustment</code> method enables a plug-in to override specific <a href="https://msdn.microsoft.com/139a10e9-203b-499b-9291-8537eae9189c">PDEV</a> settings.


## -syntax


````
HRESULT GetPDEVAdjustment(
        PDEVOBJ pdevobj,
        DWORD   dwAdjustType,
        PVOID   pBuf,
        DWORD   cbBuffer,
  [out] BOOL    *pbAdjustmentDone
);
````


## -parameters




### -param pdevobj

Pointer to a <a href="..\printoem\ns-printoem-_devobj.md">DEVOBJ</a> structure.


### -param dwAdjustType

Specifies the type of adjustment asked for. The following flags are currently supported:

<table>
<tr>
<th>Flag</th>
<th>Meaning</th>
</tr>
<tr>
<td>
PDEV_ADJUST_PAPER_MARGIN_TYPE

</td>
<td>
Adjust the paper margin setting that is reported in the PDEV. See the <a href="..\printoem\ns-printoem-_pdev_adjust_paper_margin.md">PDEV_ADJUST_PAPER_MARGIN</a> structure.

</td>
</tr>
<tr>
<td>
PDEV_HOSTFONT_ENABLED_TYPE

</td>
<td>
Enable or disable the Hostfont support feature. See the <a href="..\printoem\ns-printoem-_pdev_hostfont_enabled.md">PDEV_HOSTFONT_ENABLED</a> structure.

</td>
</tr>
<tr>
<td>
PDEV_USE_TRUE_COLOR_TYPE

</td>
<td>
Enable or disable color output for monochrome and color printers. See the <a href="..\printoem\ns-printoem-_pdev_use_true_color.md">PDEV_USE_TRUE_COLOR</a> structure.

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



The <code>IPrintOemPS2::GetPDEVAdjustment</code> method should return S_OK if it recognizes the adjustment type, and S_FALSE if it does not. If the method fails, it should return E_FAIL. The chain of plug-ins is called until either S_OK or a failure code other than E_NOTIMPL is returned. That is, the chain of plug-ins is called until the first plug-in that is capable of handling the adjustment is found.




## -remarks



This function is available in Windows XP and later.

Currently, the Pscript5 driver calls <code>IPrintOemPS2::GetPDEVAdjustment</code> to adjust the paper margin setting, as reported in the PDEV, to enable or disable the Hostfont feature, or to turn PostScript color output on or off. 




## -see-also

<a href="..\printoem\ns-printoem-_pdev_adjust_paper_margin.md">PDEV_ADJUST_PAPER_MARGIN</a>



<a href="..\printoem\ns-printoem-_pdev_hostfont_enabled.md">PDEV_HOSTFONT_ENABLED</a>



<a href="..\printoem\ns-printoem-_pdev_use_true_color.md">PDEV_USE_TRUE_COLOR</a>



<a href="..\prcomoem\nn-prcomoem-iprintoemps2.md">IPrintOemPS2</a>



 

 


