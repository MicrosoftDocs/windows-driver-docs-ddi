---
UID: NF:prcomoem.IPrintOemPrintTicketProvider.QueryDeviceDefaultNamespace
title: IPrintOemPrintTicketProvider::QueryDeviceDefaultNamespace method
author: windows-driver-content
description: The IPrintOemPrintTicketProvider::QueryDeviceDefaultNamespace method queries the device for its default namespace uniform resource identifier (URI).
old-location: print\iprintoemprintticketprovider_querydevicedefaultnamespace.htm
old-project: print
ms.assetid: 1af15e59-8796-48e2-ab18-a450db3086d3
ms.author: windowsdriverdev
ms.date: 1/8/2018
ms.keywords: IPrintOemPrintTicketProvider, IPrintOemPrintTicketProvider::QueryDeviceDefaultNamespace, QueryDeviceDefaultNamespace
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
req.alt-api: IPrintOemPrintTicketProvider.QueryDeviceDefaultNamespace
req.alt-loc: prcomoem.h
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
req.typenames: OEMPTOPTS, *POEMPTOPTS
req.product: Windows 10 or later.
---

# IPrintOemPrintTicketProvider::QueryDeviceDefaultNamespace method



## -description
The <code>IPrintOemPrintTicketProvider::QueryDeviceDefaultNamespace</code> method queries the device for its default namespace uniform resource identifier (URI).



## -syntax

````
HRESULT QueryDeviceDefaultNamespace(
  [out] BSTR *pbstrNamespaceUri
);
````


## -parameters

### -param pbstrNamespaceUri [out]

A pointer to a BSTR that receives the namespace URI. The plug-in places the namespace URI in the buffer that is pointed to by <i>pbstrNamespaceUri</i>. <code>IPrintOemPrintTicketProvider::QueryDeviceDefaultNamespace</code> is responsible for allocating the string by means of a call to <b>SysAllocString</b> (described in the Microsoft Windows SDK documentation), but the caller is responsible for freeing the string.


## -returns
<code>IPrintOemPrintTicketProvider::QueryDeviceDefaultNamespace</code> should return one of the following values.
<dl>
<dt><b>S_OK</b></dt>
</dl>The operation succeeded.
<dl>
<dt><b>E_NOTIMPL</b></dt>
</dl>The plug-in does not intend to override the default namespace that the core driver generated from the plug-in's provider.

 


## -remarks
The plug-in should specify the name of the private namespace URI that the core driver should use to handle any features that are defined in the GPD file or PPD file that the core driver does not recognize. The plug-in might specify a set of namespaces as a result of the call to the <a href="https://msdn.microsoft.com/library/windows/hardware/ff553151">IPrintOemPrintTicketProvider::BindPrinter</a> method. The purpose of the <code>IPrintOemPrintTicketProvider::QueryDeviceDefaultNamespace</code> is to inform the core driver about which of these namespaces is to be used as the default namespace. The core driver associates all of the features that it does not recognize with this default namespace, and places any such features in the print ticket. 


## -see-also
<dl>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff553151">IPrintOemPrintTicketProvider::BindPrinter</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [print\print]:%20IPrintOemPrintTicketProvider::QueryDeviceDefaultNamespace method%20 RELEASE:%20(1/8/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

