---
UID: NF:printerextension.IPrinterExtensionEventArgs.get_ReasonId
title: IPrinterExtensionEventArgs::get_ReasonId method
author: windows-driver-content
description: Gets the reason why the printer extension was activated.
old-location: print\iprinterextensioneventargs_reasonid.htm
old-project: print
ms.assetid: 404E9893-97BA-48A7-87CE-0B4AF46692CE
ms.author: windowsdriverdev
ms.date: 2/22/2018
ms.keywords: IPrinterExtensionEventArgs, printerextension/IPrinterExtensionEventArgs::ReasonId, ReasonId property [Print Devices], IPrinterExtensionEventArgs interface, print.iprinterextensioneventargs_reasonid, IPrinterExtensionEventArgs interface [Print Devices], ReasonId property, printerextension/IPrinterExtensionEventArgs::get_ReasonId, IPrinterExtensionEventArgs.ReasonId, ReasonId property [Print Devices], get_ReasonId, IPrinterExtensionEventArgs::get_ReasonId
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: method
req.header: printerextension.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: Windows 8
req.target-min-winversvr: Windows Server 2012
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: printerextension.h
req.dll: 
req.irql: 
topictype:
-	APIRef
-	kbSyntax
apitype:
-	COM
apilocation:
-	Printerextension.h
apiname:
-	IPrinterExtensionEventArgs.ReasonId
-	IPrinterExtensionEventArgs.get_ReasonId
product: Windows
targetos: Windows
req.typenames: PrintSchemaSelectionType
req.product: Windows 10 or later.
---

# IPrinterExtensionEventArgs::get_ReasonId method


## -description


Gets the reason why the printer extension was activated.

This property is read-only.


## -syntax


````
HRESULT get_ReasonId(
  [out, retval] GUID *pReasonId
);
````


## -parameters


## -remarks




<ul>
<li>
In this mode, preferences for a print job or default print preferences is expected to be displayed.

Guid = {EC8F261F-267C-469F-B5D6-3933023C29CC}

<b>PRINTER_EXTENSION_REASON_PRINT_PREFERENCES</b> = { 0xec8f261f, 0x267c, 0x469f, 0xb5, 0xd6, 0x39, 0x33, 0x2, 0x3c, 0x29, 0xcc };


</li>
<li>
In this mode a status monitor for the print queue is expected to be displayed

Guid = {23BB1328-63DE-4293-915B-A6A23D929ACB}

<b>PRINTER_EXTENSION_REASON_DRIVER_EVENT</b> = { 0x23bb1328, 0x63de, 0x4293, 0x91, 0x5b, 0xa6, 0xa2, 0x3d, 0x92, 0x9a, 0xcb };

</li>
</ul>





## -see-also

<a href="https://msdn.microsoft.com/library/windows/hardware/hh973209">DetailedReasonId</a>



<a href="..\printerextension\nn-printerextension-iprinterextensioneventargs.md">IPrinterExtensionEventArgs</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [print\print]:%20IPrinterExtensionEventArgs::ReasonId property%20 RELEASE:%20(2/22/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

