---
UID: NF:prcomoem.IPrintOemPrintTicketProvider.QueryDeviceDefaultNamespace
title: IPrintOemPrintTicketProvider::QueryDeviceDefaultNamespace method
author: windows-driver-content
description: The IPrintOemPrintTicketProvider::QueryDeviceDefaultNamespace method queries the device for its default namespace uniform resource identifier (URI).
old-location: print\iprintoemprintticketprovider_querydevicedefaultnamespace.htm
old-project: print
ms.assetid: 1af15e59-8796-48e2-ab18-a450db3086d3
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: IPrintOemPrintTicketProvider, IPrintOemPrintTicketProvider interface [Print Devices], QueryDeviceDefaultNamespace method, IPrintOemPrintTicketProvider::QueryDeviceDefaultNamespace, QueryDeviceDefaultNamespace, QueryDeviceDefaultNamespace method [Print Devices], QueryDeviceDefaultNamespace method [Print Devices], IPrintOemPrintTicketProvider interface, QueryDeviceDefaultNamespace,IPrintOemPrintTicketProvider.QueryDeviceDefaultNamespace, prcomoem/IPrintOemPrintTicketProvider::QueryDeviceDefaultNamespace, print.iprintoemprintticketprovider_querydevicedefaultnamespace, print_ticket-package_9b7bc4a4-a8db-4bef-b592-b6774c8d9fb2.xml
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
req.lib: prcomoem.h
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
-	IPrintOemPrintTicketProvider.QueryDeviceDefaultNamespace
product: Windows
targetos: Windows
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

<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>S_OK</b></dt>
</dl>
</td>
<td width="60%">
The operation succeeded.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>E_NOTIMPL</b></dt>
</dl>
</td>
<td width="60%">
The plug-in does not intend to override the default namespace that the core driver generated from the plug-in's provider.

</td>
</tr>
</table>
 




## -remarks



The plug-in should specify the name of the private namespace URI that the core driver should use to handle any features that are defined in the GPD file or PPD file that the core driver does not recognize. The plug-in might specify a set of namespaces as a result of the call to the <a href="https://msdn.microsoft.com/library/windows/hardware/ff553151">IPrintOemPrintTicketProvider::BindPrinter</a> method. The purpose of the <code>IPrintOemPrintTicketProvider::QueryDeviceDefaultNamespace</code> is to inform the core driver about which of these namespaces is to be used as the default namespace. The core driver associates all of the features that it does not recognize with this default namespace, and places any such features in the print ticket. 

<div class="alert"><b>Note</b>    When <code>IPrintOemPrintTicketProvider::QueryDeviceDefaultNamespace</code> returns, the core driver is responsible for adding the private namespace URI that the plug-in has specified (in *<i>pbstrNamespaceUri</i>) to the root node of the DOM document. The core driver also must define a prefix for the private namespace that the plug-in should use when the plug-in adds a new node to the print ticket under the plug-in's private namespace. The plug-in should not define its own prefix for this default private namespace URI.</div>
<div> </div>



## -see-also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff553151">IPrintOemPrintTicketProvider::BindPrinter</a>



<a href="..\prcomoem\nn-prcomoem-iprintoemprintticketprovider.md">IPrintOemPrintTicketProvider</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [print\print]:%20IPrintOemPrintTicketProvider::QueryDeviceDefaultNamespace method%20 RELEASE:%20(2/26/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

