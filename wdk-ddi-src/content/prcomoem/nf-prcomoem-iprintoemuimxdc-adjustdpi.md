---
UID: NF:prcomoem.IPrintOemUIMXDC.AdjustDPI
title: IPrintOemUIMXDC::AdjustDPI method
author: windows-driver-content
description: The IPrintOemUIMXDC::AdjustDPI method enables an XPS filter pipeline driver to use UnidrvUI.dll or PS5UI.dll to support configuration of image resolution.
old-location: print\iprintoemuimxdc_adjustdpi.htm
old-project: print
ms.assetid: d725d917-08fb-4e11-824c-795e35782a06
ms.author: windowsdriverdev
ms.date: 1/18/2018
ms.keywords: IPrintOemUIMXDC interface [Print Devices], AdjustDPI method, AdjustDPI, print_unidrv-pscript_ui_cd41d40c-f5a8-467f-be0d-00453886ebd1.xml, IPrintOemUIMXDC::AdjustDPI, print.iprintoemuimxdc_adjustdpi, IPrintOemUIMXDC, prcomoem/IPrintOemUIMXDC::AdjustDPI, AdjustDPI method [Print Devices], AdjustDPI method [Print Devices], IPrintOemUIMXDC interface
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
-	IPrintOemUIMXDC.AdjustDPI
product: Windows
targetos: Windows
req.typenames: OEMPTOPTS, *POEMPTOPTS
req.product: Windows 10 or later.
---

# IPrintOemUIMXDC::AdjustDPI method


## -description


The <code>IPrintOemUIMXDC::AdjustDPI</code> method enables an XPS filter pipeline driver to use UnidrvUI.dll or PS5UI.dll to support configuration of image resolution.


## -syntax


````
HRESULT AdjustDPI(
         HANDLE   hPrinter,
         DWORD    cbDevMode,
   const PDEVMODE pDevMode,
         DWORD    cbOEMDM,
   const PVOID    pOEMDM,
         PLONG    pDPI
);
````


## -parameters




### -param hPrinter

A handle to the printer that is currently being queried.


### -param cbDevMode

The size of the <a href="https://msdn.microsoft.com/b2369876-9a79-40c8-8d27-c8b9d8e68e6b">DEVMODE</a> structure, including appended data.


### -param pDevMode

A pointer to the DEVMODE structure that contains the current device settings.


### -param cbOEMDM

The number of bytes in the vendor-provided section of the DEVMODE structure.


### -param pOEMDM

A pointer to the data that is contained in the vendor portion of the DEVMODE structure that <i>pDevMode</i> points to.


### -param pDPI

A pointer to the current resolution, in dots per inch (DPI), assuming square pixels. If this parameter is configured, its returned value must be a positive integer.


## -returns


<code>AdjustDPI</code> returns S_OK if the method succeeds. Otherwise, this method should return E_NOTIMPL if the plug-in does not support the method, or any appropriate failure value if the plug-in cannot complete the operation. For more information, see the following Remarks section.



## -remarks


The <i>pDPI</i> parameter is IN OUT. All other parameters for this function are input only.

If the plug-in cannot complete the operation, it should return an appropriate failure HRESULT, which causes the current print job to fail.


