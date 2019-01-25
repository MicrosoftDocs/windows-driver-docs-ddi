---
UID: NF:prcomoem.IPrintOemUIMXDC.AdjustImageableArea
title: IPrintOemUIMXDC::AdjustImageableArea (prcomoem.h)
description: The IPrintOemUIMXDC::AdjustImageableArea method enables an XPS filter pipeline driver to use UnidrvUI.dll or PS5UI.dll to support configuration of the printable area, including orientation and direction of rotation.
old-location: print\iprintoemuimxdc_adjustimageablearea.htm
tech.root: print
ms.assetid: a698fcb9-1285-4201-9b49-e79dcda66043
ms.date: 04/20/2018
ms.keywords: AdjustImageableArea, AdjustImageableArea method [Print Devices], AdjustImageableArea method [Print Devices],IPrintOemUIMXDC interface, IPrintOemUIMXDC interface [Print Devices],AdjustImageableArea method, IPrintOemUIMXDC.AdjustImageableArea, IPrintOemUIMXDC::AdjustImageableArea, prcomoem/IPrintOemUIMXDC::AdjustImageableArea, print.iprintoemuimxdc_adjustimageablearea, print_unidrv-pscript_ui_c6e35081-e9d3-4d55-85be-e0d5b48bc39c.xml
ms.topic: method
req.header: prcomoem.h
req.include-header: Prcomoem.h
req.target-type: Desktop
req.target-min-winverclnt: Available with Windows Vista and later versions of Unidrvui.dll and Ps5ui.dll, which are redistributable. This method is also available for XPSDrv drivers in Microsoft Windows XP if you have installed the XPS Essentials Pack.
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
-	IPrintOemUIMXDC.AdjustImageableArea
product:
- Windows
targetos: Windows
req.typenames: 
---

# IPrintOemUIMXDC::AdjustImageableArea


## -description


The <code>IPrintOemUIMXDC::AdjustImageableArea</code> method enables an XPS filter pipeline driver to use UnidrvUI.dll or PS5UI.dll to support configuration of the printable area, including orientation and direction of rotation.


## -parameters




### -param hPrinter

A handle to the printer that is currently being queried.


### -param cbDevMode

The size of the <a href="https://msdn.microsoft.com/b2369876-9a79-40c8-8d27-c8b9d8e68e6b">DEVMODE</a> structure, in bytes, including appended data.


### -param pDevMode

A pointer to the DEVMODE structure that contains the current device settings.


### -param cbOEMDM

The number of bytes in the vendor-provided section of the DEVMODE structure.


### -param pOEMDM

A pointer to the data that is contained in the vendor portion of the DEVMODE structure that <i>pDevMode</i> points to.


### -param prclImageableArea

A pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/ff569236">RECTL</a> structure that contains the printable area. This parameter is populated by UnidrvUI.dll or PS5UI.dll with data from the corresponding GPD or PPD, before the parameter is passed to the plug-in. The plug-in can then update this data before returning. 


## -returns



<code>AdjustImageableArea</code> returns S_OK if this method succeeds. Otherwise, this method should return E_NOTIMPL if the plug-in does not support the method, or any appropriate failure value if the plug-in cannot complete the operation. For more information, see the following Remarks section.




## -remarks



The <i>prclImageableArea</i> parameter is IN OUT. All other parameters for this method are input only.

If the plug-in cannot complete the operation, it should return an appropriate failure HRESULT value, which willcause the current print job to fail.




## -see-also




<a href="https://msdn.microsoft.com/4a70c0a7-9de7-48ed-a678-64832f078018">IPrintOemUIMXDC</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff569236">RECTL</a>
 

 

