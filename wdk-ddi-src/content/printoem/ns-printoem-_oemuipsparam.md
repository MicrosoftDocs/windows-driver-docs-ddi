---
UID: NS:printoem._OEMUIPSPARAM
title: "_OEMUIPSPARAM"
author: windows-driver-content
description: The OEMUIPSPARAM structure is passed to a user interface plug-in's IPrintOemUI::DevicePropertySheets and IPrintOemUI::DocumentPropertySheets methods.
old-location: print\oemuipsparam.htm
old-project: print
ms.assetid: e7708b33-b032-41b9-84f9-6c5b38044f9c
ms.author: windowsdriverdev
ms.date: 2/22/2018
ms.keywords: POEMUIPSPARAM structure pointer [Print Devices], _OEMUIPSPARAM, print_unidrv-pscript_ui_7a4c3f10-5a2d-45da-99e4-bbd6ee0fb8bf.xml, *POEMUIPSPARAM, printoem/POEMUIPSPARAM, OEMUIPSPARAM structure [Print Devices], print.oemuipsparam, OEMUIPSPARAM, POEMUIPSPARAM, printoem/OEMUIPSPARAM
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: printoem.h
req.include-header: Printoem.h
req.target-type: Windows
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	printoem.h
apiname:
-	OEMUIPSPARAM
product: Windows
targetos: Windows
req.typenames: OEMUIPSPARAM, *POEMUIPSPARAM
req.product: Windows 10 or later.
---

# _OEMUIPSPARAM structure


## -description


The OEMUIPSPARAM structure is passed to a user interface plug-in's <a href="https://msdn.microsoft.com/library/windows/hardware/ff554165">IPrintOemUI::DevicePropertySheets</a> and <a href="https://msdn.microsoft.com/library/windows/hardware/ff554173">IPrintOemUI::DocumentPropertySheets</a> methods.


## -syntax


````
typedef struct _OEMUIPSPARAM {
  DWORD     cbSize;
  POEMUIOBJ poemuiobj;
  HANDLE    hPrinter;
  PWSTR     pPrinterName;
  HANDLE    hModule;
  HANDLE    hOEMHeap;
  PDEVMODE  pPublicDM;
  PVOID     pOEMDM;
  PVOID     pOEMUserData;
  DWORD     dwFlags;
  PVOID     pOemEntry;
} OEMUIPSPARAM, *POEMUIPSPARAM;
````


## -struct-fields




### -field cbSize

Size of the OEMUIPSPARAM structure. Supplied by the Unidrv or Pscript5 driver.


### -field poemuiobj

Not used.


### -field hPrinter

Handle to the printer. Supplied by the Unidrv or Pscript5 driver.


### -field pPrinterName

String containing the printer name. Supplied by the Unidrv or Pscript5 driver.


### -field hModule

Handle to the user interface plug-in. Supplied by the Unidrv or Pscript5 driver.


### -field hOEMHeap

Handle to a heap from which space can be allocated by calling the Microsoft Windows SDK <b>HeapAlloc</b> function. Supplied by the Unidrv or Pscript5 driver.


### -field pPublicDM





#### For calls to IPrintOemUI::DocumentPropertySheets:

Caller-supplied pointer to the printer's public DEVMODEW structure.



#### For calls to IPrintOemUI::DevicePropertySheets:

Not used.


### -field pOEMDM





#### For calls to IPrintOemUI::DocumentPropertySheets:

Caller-supplied pointer to the user interface plug-in's private DEVMODEW members.



#### For calls to IPrintOemUI::DevicePropertySheets:

Not used.


### -field pOEMUserData

Pointer, supplied by user interface plug-in, to a location containing private information. This pointer is returned to the plug-in's <a href="..\compstui\nc-compstui-_cpsuicallback.md">_CPSUICALLBACK</a>-typed callback function when a property sheet item has changed.


### -field dwFlags





#### For calls to IPrintOemUI::DocumentPropertySheets:

Contains the contents of the <b>fMode</b> member of the DOCUMENTPROPERTYHEADER structure received by the printer driver's <a href="..\winddiui\nf-winddiui-drvdocumentpropertysheets.md">DrvDocumentPropertySheets</a> function.



#### For calls to IPrintOemUI::DevicePropertySheets:

Contains the contents of the <b>Flags</b> member of the DEVICEPROPERTYHEADER structure received by the printer driver's <a href="..\winddiui\nf-winddiui-drvdevicepropertysheets.md">DrvDevicePropertySheets</a> function.


### -field pOemEntry

Reserved for system use.


## -see-also

<a href="..\winddiui\nf-winddiui-drvdocumentpropertysheets.md">DrvDocumentPropertySheets</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff554173">IPrintOemUI::DocumentPropertySheets</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff554165">IPrintOemUI::DevicePropertySheets</a>



<a href="..\winddiui\nf-winddiui-drvdevicepropertysheets.md">DrvDevicePropertySheets</a>



<a href="..\compstui\nc-compstui-_cpsuicallback.md">_CPSUICALLBACK</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [print\print]:%20OEMUIPSPARAM structure%20 RELEASE:%20(2/22/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

