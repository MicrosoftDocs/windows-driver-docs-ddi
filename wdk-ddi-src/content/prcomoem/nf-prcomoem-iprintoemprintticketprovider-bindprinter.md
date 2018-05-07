---
UID: NF:prcomoem.IPrintOemPrintTicketProvider.BindPrinter
title: IPrintOemPrintTicketProvider::BindPrinter
author: windows-driver-content
description: The IPrintOemPrintTicketProvider::BindPrinter method enables the core driver to associate a set of private namespace uniform resource identifiers (URIs) with a device.
old-location: print\iprintoemprintticketprovider_bindprinter.htm
old-project: print
ms.assetid: 6b31b340-de94-4e6c-a48a-7c1b874eb7cd
ms.author: windowsdriverdev
ms.date: 4/20/2018
ms.keywords: BindPrinter, BindPrinter method [Print Devices], BindPrinter method [Print Devices],IPrintOemPrintTicketProvider interface, IPrintOemPrintTicketProvider interface [Print Devices],BindPrinter method, IPrintOemPrintTicketProvider.BindPrinter, IPrintOemPrintTicketProvider::BindPrinter, prcomoem/IPrintOemPrintTicketProvider::BindPrinter, print.iprintoemprintticketprovider_bindprinter, print_ticket-package_14890643-fabb-4e03-8d1e-08a6ff7f1c9c.xml
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
-	IPrintOemPrintTicketProvider.BindPrinter
product:
- Windows
targetos: Windows
req.typenames: 
---

# IPrintOemPrintTicketProvider::BindPrinter


## -description


The <code>IPrintOemPrintTicketProvider::BindPrinter</code> method enables the core driver to associate a set of private namespace uniform resource identifiers (URIs) with a device. This method also allows the plug-in to cache information (such as the printer handle) that can be used at a later time.


## -parameters




### -param hPrinter [in]

The spooler's print handle, which is supplied by Unidrv. The provider should not close this handle at any time, because the client of the provider is responsible for managing the lifetime of this handle. The provider can cache the print handle; all future calls on this object are relative to the printer that is associated with this handle.


### -param version [in]

The major version number of the print schema. Windows Vista supports only version 1.


### -param pOptions [out]

A pointer to a variable that receives one of the following enumerated values: 





#### OEMPT_DEFAULT

The system places a binary encoding (a binary large object [BLOB]) of the private <a href="https://msdn.microsoft.com/library/windows/hardware/ff552837">DEVMODEW</a> structure into the print ticket in a conversion of a DEVMODEW to a print ticket. 



#### OEMPT_NOSNAPSHOT

The system will not place a binary encoding (a BLOB) of the private DEVMODEW structure into the print ticket in a conversion of a DEVMODEW to a print ticket. Use this value if all of the public and private DEVMODEW members are fully represented in the print ticket.

The OEM object that is being called should set the value pointed to by this parameter.


### -param cNamespaces [out]

A pointer to a variable that receives the number of private namespace URIs that are used in the plug-in. This number represents the count of strings in the array that is pointed to by *<i>ppNamespaces</i>.


### -param ppNamespaces [out]

A pointer to a variable that receives the address of the first element of a BSTR array. The plug-in fills each array position with a namespace URI. For more information about this parameter, see the following Remarks section.


## -returns



<code>IPrintOemPrintTicketProvider::BindPrinter</code> should return one of the following values.

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
<dt><b>E_VERSION_NOT_SUPPORTED</b></dt>
</dl>
</td>
<td width="60%">
The plug-in does not support the version of the print schema that is specified in the <i>version</i> parameter.

</td>
</tr>
</table>
 




## -remarks



The plug-in is responsible for allocating memory for the array that is pointed to by the <i>ppNamespaces</i> parameter and for the namespace URI strings. The array should be allocated by using the <b>CoTaskMemAlloc</b> function; the namespace strings should be allocated by using the <b>SysAllocString</b> function. Both of these functions are described in the Microsoft Windows SDK documentation. The array that is pointed to by the <i>ppNamespaces</i> parameter is not required to contain the namespaces for the Print Schema Keywords or the Print Schema Framework.

Binding to a device enables the provider to cache certain objects and handles that it will need for future print ticket or print capabilities services on that device. For example, the printer handle in <i>hPrinter</i> can be cached. <code>IPrintOemPrintTicketProvider::BindPrinter</code> is guaranteed to be called only once. 

An <b>IPrintTicketProvider</b> object does not have to be able to bind more than once. The print ticket manager always uses different <b>IPrintTicketProvider</b> object instances for binding to different devices. All resources that are acquired in a successful call to <code>IPrintTicketProvider::BindPrinter</code> should be released when the reference count of an <b>IPrintTicketProvider</b> object is zero. (Note that the provider should not close the handle that was passed into the call to <b>BindPrinter</b>). The print ticket manager might create multiple providers for the same device, in different versions, if multiple versions are supported.




## -see-also




<a href="https://msdn.microsoft.com/a32b5ec9-b4f2-4f33-879d-252806bd34ed">IPrintOemPrintTicketProvider</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff553161">IPrintOemPrintTicketProvider::ConvertDevModeToPrintTicket</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff553167">IPrintOemPrintTicketProvider::ConvertPrintTicketToDevMode</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff553170">IPrintOemPrintTicketProvider::GetSupportedVersions</a>
 

 


