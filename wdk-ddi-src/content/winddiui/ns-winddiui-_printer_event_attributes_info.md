---
UID: NS:winddiui._PRINTER_EVENT_ATTRIBUTES_INFO
title: "_PRINTER_EVENT_ATTRIBUTES_INFO"
author: windows-driver-content
description: The PRINTER_EVENT_ATTRIBUTES_INFO structure contains the former attributes and the new attributes for a printer.
old-location: print\printer_event_attributes_info.htm
old-project: print
ms.assetid: 3c39a515-f4f4-4309-8d4e-461b8835295b
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: "*PPRINTER_EVENT_ATTRIBUTES_INFO, PPRINTER_EVENT_ATTRIBUTES_INFO, PPRINTER_EVENT_ATTRIBUTES_INFO structure pointer [Print Devices], PRINTER_EVENT_ATTRIBUTES_INFO, PRINTER_EVENT_ATTRIBUTES_INFO structure [Print Devices], _PRINTER_EVENT_ATTRIBUTES_INFO, print.printer_event_attributes_info, print_interface-graphics_a4fa57f7-bd03-4c38-9c0f-026da9d3535e.xml, winddiui/PPRINTER_EVENT_ATTRIBUTES_INFO, winddiui/PRINTER_EVENT_ATTRIBUTES_INFO"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: winddiui.h
req.include-header: Winddiui.h
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	winddiui.h
api_name:
-	PRINTER_EVENT_ATTRIBUTES_INFO
product: Windows
targetos: Windows
req.typenames: PRINTER_EVENT_ATTRIBUTES_INFO, *PPRINTER_EVENT_ATTRIBUTES_INFO
req.product: Windows 10 or later.
---

# _PRINTER_EVENT_ATTRIBUTES_INFO structure


## -description


The PRINTER_EVENT_ATTRIBUTES_INFO structure contains the former attributes and the new attributes for a printer.


## -syntax


````
typedef struct _PRINTER_EVENT_ATTRIBUTES_INFO {
  DWORD cbSize;
  DWORD dwOldAttributes;
  DWORD dwNewAttributes;
} PRINTER_EVENT_ATTRIBUTES_INFO, *PPRINTER_EVENT_ATTRIBUTES_INFO;
````


## -struct-fields




### -field cbSize

Specifies the size of this structure.


### -field dwOldAttributes

A set of bits describing the current printer attributes.


### -field dwNewAttributes

A set of bits describing the new printer attributes to be applied to the printer.


## -remarks



The bits in the <b>dwOldAttributes</b> and <b>dwNewAttributes</b> members of this structure are set in accordance with the <b>Attributes</b> member of the PRINTER_INFO_2 structure (defined in the Microsoft Windows SDK documentation).

Because this structure might become larger in future operating system versions, anyone using this structure is advised to check that the value in the <b>cbSize</b> member of this structure is at least as large as the offset of the member to be accessed.




## -see-also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff554182">IPrintOemUI::PrinterEvent</a>



<a href="..\winddiui\nf-winddiui-drvprinterevent.md">DrvPrinterEvent</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [print\print]:%20PRINTER_EVENT_ATTRIBUTES_INFO structure%20 RELEASE:%20(2/26/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

