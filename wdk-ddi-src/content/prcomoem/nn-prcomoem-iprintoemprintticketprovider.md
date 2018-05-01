---
UID: NN:prcomoem.IPrintOemPrintTicketProvider
title: IPrintOemPrintTicketProvider
author: windows-driver-content
description: This section describes the methods that are defined for the IPrintOemPrintTicketProvider COM interface.
old-location: print\iprintoemprintticketprovider_interface.htm
old-project: print
ms.assetid: a32b5ec9-b4f2-4f33-879d-252806bd34ed
ms.author: windowsdriverdev
ms.date: 4/20/2018
ms.keywords: IPrintOemPrintTicketProvider, IPrintOemPrintTicketProvider interface [Print Devices], IPrintOemPrintTicketProvider interface [Print Devices],described, prcomoem/IPrintOemPrintTicketProvider, print.iprintoemprintticketprovider_interface, print_ticket-package_73ff5919-5d89-4fe1-b10f-03f2b14b716f.xml
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: interface
req.header: prcomoem.h
req.include-header: 
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
req.lib: NtosKrnl.lib
req.dll: NtosKrnl.exe
req.irql: 
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	COM
api_location:
-	prcomoem.h
api_name:
-	IPrintOemPrintTicketProvider
product: Windows
targetos: Windows
req.typenames: 
---

# IPrintOemPrintTicketProvider interface


## -description


This section describes the methods that are defined for the <b>IPrintOemPrintTicketProvider</b> COM interface.


## -inheritance

The <b xmlns:loc="http://microsoft.com/wdcml/l10n">IPrintOemPrintTicketProvider</b> interface inherits from the <a href="https://msdn.microsoft.com/33f1d79a-33fc-4ce5-a372-e08bda378332">IUnknown</a> interface. <b>IPrintOemPrintTicketProvider</b> also has these types of members:
<ul>
<li><a href="https://docs.microsoft.com/">Methods</a></li>
</ul>

## -members

The <b>IPrintOemPrintTicketProvider</b> interface has these methods.
<table class="members" id="memberListMethods">
<tr>
<th align="left" width="37%">Method</th>
<th align="left" width="63%">Description</th>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/bd1ca076-5007-4e38-8e90-4017d7dc8b3f">GetSupportedVersions</a>
</td>
<td align="left" width="63%">
The <code>IPrintOemPrintTicketProvider::GetSupportedVersions</code> method retrieves major versions of the print schemas that are supported by the plug-in provider.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/ff553151">IPrintOemPrintTicketProvider::BindPrinter</a>
</td>
<td align="left" width="63%">
The <code>IPrintOemPrintTicketProvider::BindPrinter</code> method enables the core driver to associate a set of private namespace uniform resource identifiers (URIs) with a device. This method also allows the plug-in to cache information (such as the printer handle) that can be used at a later time.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/ff553158">IPrintOemPrintTicketProvider::CompletePrintCapabilities</a>
</td>
<td align="left" width="63%">
The <code>IPrintOemPrintTicketProvider::CompletePrintCapabilities</code> method fills in the remaining entries of the specified print capabilities document. 

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/ff553161">IPrintOemPrintTicketProvider::ConvertDevModeToPrintTicket</a>
</td>
<td align="left" width="63%">
The <code>IPrintOemPrintTicketProvider::ConvertDevModeToPrintTicket</code> method converts a <a href="https://msdn.microsoft.com/library/windows/hardware/ff552837">DEVMODEW</a> structure into a print ticket. 

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/ff553167">IPrintOemPrintTicketProvider::ConvertPrintTicketToDevMode</a>
</td>
<td align="left" width="63%">
The <code>IPrintOemPrintTicketProvider::ConvertPrintTicketToDevMode</code> method converts a print ticket to a <a href="https://msdn.microsoft.com/library/windows/hardware/ff552837">DEVMODEW</a> structure. 

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/ff553168">IPrintOemPrintTicketProvider::ExpandIntentOptions</a>
</td>
<td align="left" width="63%">
The <code>IPrintOemPrintTicketProvider::ExpandIntentOptions</code> method enables the plug-in to expand printer options (such as photo printing) into individual feature settings in the print ticket. 

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/ff553178">IPrintOemPrintTicketProvider::PublishPrintTicketHelperInterface</a>
</td>
<td align="left" width="63%">
The <code>IPrintOemPrintTicketProvider::PublishPrintTicketHelperInterface</code> method publishes the print ticket helper interface for either Unidrv or Pscript5 user interface (UI) plug-ins.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/ff553180">IPrintOemPrintTicketProvider::QueryDeviceDefaultNamespace</a>
</td>
<td align="left" width="63%">
The <code>IPrintOemPrintTicketProvider::QueryDeviceDefaultNamespace</code> method queries the device for its default namespace uniform resource identifier (URI).

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/ff553184">IPrintOemPrintTicketProvider::ValidatePrintTicket</a>
</td>
<td align="left" width="63%">
The <code>IPrintOemPrintTicketProvider::ValidatePrintTicket</code> method validates a print ticket.

</td>
</tr>
</table> 

