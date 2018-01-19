---
UID: NN:printerextension.IPrinterExtensionEventArgs
title: IPrinterExtensionEventArgs
author: windows-driver-content
description: Represents the context for the desktop printer extension activation.
old-location: print\iprinterextensioneventargs.htm
old-project: print
ms.assetid: 77850B5A-4E24-4057-B87F-D964620ABF94
ms.author: windowsdriverdev
ms.date: 1/8/2018
ms.keywords: IPrintSchemaTicket2, IPrintSchemaTicket2::GetParameterInitializer, GetParameterInitializer
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: interface
req.header: printerextension.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: Windows 8
req.target-min-winversvr: Windows Server 2012
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: IPrinterExtensionEventArgs
req.alt-loc: Printerextension.h
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
req.typenames: PrintSchemaSelectionType
req.product: Windows 10 or later.
---

# IPrinterExtensionEventArgs interface



## -description
Represents the context for the desktop printer extension activation.



## -inheritance
The <b xmlns:loc="http://microsoft.com/wdcml/l10n">IPrinterExtensionEventArgs</b> interface inherits from <a href="..\printerextension\nn-printerextension-iprinterextensioncontext.md">IPrinterExtensionContext</a>. <b>IPrinterExtensionEventArgs</b> also has these types of members:

The <b xmlns:loc="http://microsoft.com/wdcml/l10n">IPrinterExtensionEventArgs</b> interface has these properties.


<a href="https://msdn.microsoft.com/library/windows/hardware/hh973208">BidiNotification</a>


Read-only

Gets the text of the bidirectional communication (Bidi) notification, if applicable.


<a href="https://msdn.microsoft.com/library/windows/hardware/hh973209">DetailedReasonId</a>


Read-only

Gets a more detailed activation reason than what can be retrieved from  <a href="https://msdn.microsoft.com/library/windows/hardware/hh973210">ReasonId</a>.


<a href="https://msdn.microsoft.com/library/windows/hardware/hh973210">ReasonId</a>


Read-only

Gets the reason why the printer extension was activated.


<a href="https://msdn.microsoft.com/library/windows/hardware/ff554564">Request</a>


Read-only

Gets the <a href="..\printerextension\nn-printerextension-iprinterextensionrequest.md">IPrinterExtensionRequest</a> object for the current event.


<a href="https://msdn.microsoft.com/library/windows/hardware/hh973212">SourceApplication</a>


Read-only

Gets the name of the application that invoked the printer extension.


<a href="https://msdn.microsoft.com/library/windows/hardware/hh973213">WindowModal</a>


Read-only

Gets the run mode parameter that determines whether or not the printer extension should be run as modal.


<a href="https://msdn.microsoft.com/library/windows/hardware/hh973214">WindowParent</a>


Read-only

Gets the handle of the parent window.

 


## -remarks


## -see-also
<dl>
<dt>
<a href="..\printerextension\nn-printerextension-iprinterextensioncontext.md">IPrinterExtensionContext</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/4E20303A-BEB3-4928-BA5A-356D978FA2BE">V4 Printer Driver Property Bags</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [print\print]:%20IPrinterExtensionEventArgs interface%20 RELEASE:%20(1/8/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

