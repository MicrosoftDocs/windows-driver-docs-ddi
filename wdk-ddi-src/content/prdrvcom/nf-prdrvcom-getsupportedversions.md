---
UID: NF:prdrvcom.GetSupportedVersions
title: GetSupportedVersions function
author: windows-driver-content
description: The IPrintTicketProvider::GetSupportedVersions method retrieves major version numbers of the print schemas that are supported by the plug-in provider.
old-location: print\iprintticketprovider_getsupportedversions.htm
old-project: print
ms.assetid: ea22cc52-f47b-4a54-b507-5963faa41c2d
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: GetSupportedVersions, GetSupportedVersions method [Print Devices], GetSupportedVersions method [Print Devices], IPrintTicketProvider interface, IPrintTicketProvider interface [Print Devices], GetSupportedVersions method, IPrintTicketProvider::GetSupportedVersions, prdrvcom/IPrintTicketProvider::GetSupportedVersions, print.iprintticketprovider_getsupportedversions, print_ticket-package_3c9ed7b7-a38f-49b2-a7fc-7fc78aa39a27.xml
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: prdrvcom.h
req.include-header: Prdrvcom.h
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
-	Prdrvcom.h
api_name:
-	IPrintTicketProvider.GetSupportedVersions
product: Windows
targetos: Windows
req.typenames: SHIMOPTS, *PSHIMOPTS
req.product: Windows 10 or later.
---

# GetSupportedVersions function


## -description


The <code>IPrintTicketProvider::GetSupportedVersions</code> method retrieves major version numbers of the print schemas that are supported by the plug-in provider.


## -parameters




### -param hPrinter [in]

A handle to the print device.


### -param ppVersions

TBD


### -param cVersions [out]

A pointer to a variable that receives the number of elements in the array that is pointed to by *<i>ppVersions</i>. 


#### - ppVersions[] [out]

A pointer to a variable that receives the address of the first element of an array of version numbers. Version numbers in the array can appear in any order. For more information about this parameter, see the following Remarks section.


## -returns



<code>IPrintTicketProvider::GetSupportedVersions</code> should return S_OK if the operation succeeds. If this method fails because of lack of memory or other resources, it should return a standard COM error code.




## -remarks



<code>IPrintTicketProvider::GetSupportedVersions</code> returns the major version numbers of the print schemas that are supported by the provider interface. (The only currently defined version number is 1.) Providers can omit intermediate versions

The plug-in is responsible for allocating the array memory that is pointed to by the <i>ppVersions</i> parameter. The plug-in should allocate this memory by using the <b>CoTaskMemAlloc</b> function (described in the Microsoft Windows SDK documentation), but the plug-in is not responsible for freeing this memory.

Because <code>IPrintTicketProvider::GetSupportedVersions</code> can be called before the <a href="https://msdn.microsoft.com/library/windows/hardware/ff554354">IPrintTicketProvider::BindPrinter</a> method is called, the OEM plug-in provider must check version support based on the handle that is passed in the <i>hPrinter</i> parameter. As a result, the OEM plug-in provider should not close the printer handle that is associated with <i>hPrinter</i>.




## -see-also




<a href="https://msdn.microsoft.com/4eb3c193-377b-4e51-a97b-50c6fdaa1b08">IPrintTicketProvider</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff554354">IPrintTicketProvider::BindPrinter</a>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [print\print]:%20IPrintTicketProvider::GetSupportedVersions method%20 RELEASE:%20(2/26/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

