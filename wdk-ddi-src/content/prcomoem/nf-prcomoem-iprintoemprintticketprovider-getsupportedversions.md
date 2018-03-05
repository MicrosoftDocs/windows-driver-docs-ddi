---
UID: NF:prcomoem.IPrintOemPrintTicketProvider.GetSupportedVersions
title: IPrintOemPrintTicketProvider::GetSupportedVersions method
author: windows-driver-content
description: The IPrintOemPrintTicketProvider::GetSupportedVersions method retrieves major versions of the print schemas that are supported by the plug-in provider.
old-location: print\iprintoemprintticketprovider_getsupportedversions.htm
old-project: print
ms.assetid: bd1ca076-5007-4e38-8e90-4017d7dc8b3f
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: GetSupportedVersions, GetSupportedVersions method [Print Devices], GetSupportedVersions method [Print Devices], IPrintOemPrintTicketProvider interface, GetSupportedVersions,IPrintOemPrintTicketProvider.GetSupportedVersions, IPrintOemPrintTicketProvider, IPrintOemPrintTicketProvider interface [Print Devices], GetSupportedVersions method, IPrintOemPrintTicketProvider::GetSupportedVersions, prcomoem/IPrintOemPrintTicketProvider::GetSupportedVersions, print.iprintoemprintticketprovider_getsupportedversions, print_ticket-package_f20858fb-a11d-45b4-a8db-6a492b761cfc.xml
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
-	Prcomoem.h
api_name:
-	IPrintOemPrintTicketProvider.GetSupportedVersions
product: Windows
targetos: Windows
req.typenames: OEMPTOPTS, *POEMPTOPTS
req.product: Windows 10 or later.
---

# IPrintOemPrintTicketProvider::GetSupportedVersions method


## -description


The <code>IPrintOemPrintTicketProvider::GetSupportedVersions</code> method retrieves major versions of the print schemas that are supported by the plug-in provider.


## -syntax


````
STDMETHOD GetSupportedVersions(
  [in]  HANDLE hPrinter,
  [out] INT    *ppVersions,
  [out] INT    *cVersions
);
````


## -parameters




### -param hPrinter [in]

A handle to the print device.


### -param ppVersions [out]

A pointer to a variable that receives the address of the first element of an array of version numbers. Version numbers in the array can appear in any order. For more information about this parameter, see the following Remarks section.


### -param cVersions [out]

A pointer to a variable that receives the number of elements in the array that is pointed to by *<i>ppVersions</i>. 


## -returns



<code>IPrintOemPrintTicketProvider::GetSupportedVersions</code> should return S_OK if the operation succeeds. Otherwise, this method should return a standard COM error code.




## -remarks



<code>IPrintOemPrintTicketProvider::GetSupportedVersions</code> returns the major version numbers of the print schemas that are supported by the provider interface. (The only currently defined version number is 1.) Providers can omit intermediate versions.

The plug-in is responsible for allocating the array memory that is pointed to by the <i>ppVersions</i> parameter. The plug-in should allocate this memory by using the <b>CoTaskMemAlloc</b> function (described in the Microsoft Windows SDK documentation), but it is not responsible for freeing this memory.

<code>IPrintOemPrintTicketProvider::GetSupportedVersions</code> can be called before the <a href="https://msdn.microsoft.com/library/windows/hardware/ff553151">IPrintOemPrintTicketProvider::BindPrinter</a> method is called. As a result, the OEM plug-in provider should not close the printer handle that is associated with the <i>hPrinter</i> parameter.




## -see-also

<a href="..\prcomoem\nn-prcomoem-iprintoemprintticketprovider.md">IPrintOemPrintTicketProvider</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff553151">IPrintOemPrintTicketProvider::BindPrinter</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [print\print]:%20IPrintOemPrintTicketProvider::GetSupportedVersions method%20 RELEASE:%20(2/26/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

