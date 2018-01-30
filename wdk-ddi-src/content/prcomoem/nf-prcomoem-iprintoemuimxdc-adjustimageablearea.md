---
UID: NF:prcomoem.IPrintOemUIMXDC.AdjustImageableArea
title: IPrintOemUIMXDC::AdjustImageableArea method
author: windows-driver-content
description: The IPrintOemUIMXDC::AdjustImageableArea method enables an XPS filter pipeline driver to use UnidrvUI.dll or PS5UI.dll to support configuration of the printable area, including orientation and direction of rotation.
old-location: print\iprintoemuimxdc_adjustimageablearea.htm
old-project: print
ms.assetid: a698fcb9-1285-4201-9b49-e79dcda66043
ms.author: windowsdriverdev
ms.date: 1/18/2018
ms.keywords: IPrintOemUIMXDC::AdjustImageableArea, print.iprintoemuimxdc_adjustimageablearea, prcomoem/IPrintOemUIMXDC::AdjustImageableArea, AdjustImageableArea, IPrintOemUIMXDC, AdjustImageableArea method [Print Devices], IPrintOemUIMXDC interface, IPrintOemUIMXDC interface [Print Devices], AdjustImageableArea method, AdjustImageableArea method [Print Devices], print_unidrv-pscript_ui_c6e35081-e9d3-4d55-85be-e0d5b48bc39c.xml
ms.prod: windows-hardware
ms.technology: windows-devices
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
-	IPrintOemUIMXDC.AdjustImageableArea
product: Windows
targetos: Windows
req.typenames: OEMPTOPTS, *POEMPTOPTS
req.product: Windows 10 or later.
---

# IPrintOemUIMXDC::AdjustImageableArea method


## -description


The <code>IPrintOemUIMXDC::AdjustImageableArea</code> method enables an XPS filter pipeline driver to use UnidrvUI.dll or PS5UI.dll to support configuration of the printable area, including orientation and direction of rotation.


## -syntax


````
HRESULT AdjustImageableArea(
         HANDLE   hPrinter,
         DWORD    cbDevMode,
   const PDEVMODE pDevMode,
         DWORD    cbOEMDM,
   const PVOID    pOEMDM,
         PRECTL   prclImageableArea
);
````


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

<a href="https://msdn.microsoft.com/library/windows/hardware/ff569236">RECTL</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [print\print]:%20IPrintOemUIMXDC::AdjustImageableArea method%20 RELEASE:%20(1/18/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

