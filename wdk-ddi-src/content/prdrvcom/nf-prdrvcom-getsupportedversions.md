---
UID: NF:prdrvcom.GetSupportedVersions
title: GetSupportedVersions function (prdrvcom.h)
description: The IPrintTicketProvider::GetSupportedVersions method retrieves major version numbers of the print schemas that are supported by the plug-in provider.
old-location: print\iprintticketprovider_getsupportedversions.htm
tech.root: print
ms.assetid: ea22cc52-f47b-4a54-b507-5963faa41c2d
ms.date: 04/20/2018
ms.keywords: GetSupportedVersions, GetSupportedVersions method [Print Devices], GetSupportedVersions method [Print Devices],IPrintTicketProvider interface, IPrintTicketProvider interface [Print Devices],GetSupportedVersions method, IPrintTicketProvider::GetSupportedVersions, prdrvcom/IPrintTicketProvider::GetSupportedVersions, print.iprintticketprovider_getsupportedversions, print_ticket-package_3c9ed7b7-a38f-49b2-a7fc-7fc78aa39a27.xml
ms.topic: function
f1_keywords:
 - "prdrvcom/IPrintTicketProvider.GetSupportedVersions"
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
- APIRef
- kbSyntax
api_type:
- COM
api_location:
- Prdrvcom.h
api_name:
- IPrintTicketProvider.GetSupportedVersions
product:
- Windows
targetos: Windows
req.typenames: 
---

# GetSupportedVersions function


## -description


The <code>IPrintTicketProvider::GetSupportedVersions</code> method retrieves major version numbers of the print schemas that are supported by the plug-in provider.


## -parameters




### -param hPrinter [in]

A handle to the print device.


### -param ppVersions




### -param cVersions [out]

A pointer to a variable that receives the number of elements in the array that is pointed to by *<i>ppVersions</i>. 


#### - ppVersions[] [out]

A pointer to a variable that receives the address of the first element of an array of version numbers. Version numbers in the array can appear in any order. For more information about this parameter, see the following Remarks section.


## -returns



<code>IPrintTicketProvider::GetSupportedVersions</code> should return S_OK if the operation succeeds. If this method fails because of lack of memory or other resources, it should return a standard COM error code.




## -remarks



<code>IPrintTicketProvider::GetSupportedVersions</code> returns the major version numbers of the print schemas that are supported by the provider interface. (The only currently defined version number is 1.) Providers can omit intermediate versions

The plug-in is responsible for allocating the array memory that is pointed to by the <i>ppVersions</i> parameter. The plug-in should allocate this memory by using the <b>CoTaskMemAlloc</b> function (described in the Microsoft Windows SDK documentation), but the plug-in is not responsible for freeing this memory.

Because <code>IPrintTicketProvider::GetSupportedVersions</code> can be called before the <a href="https://docs.microsoft.com/previous-versions/windows/hardware/drivers/ff554354(v=vs.85)">IPrintTicketProvider::BindPrinter</a> method is called, the OEM plug-in provider must check version support based on the handle that is passed in the <i>hPrinter</i> parameter. As a result, the OEM plug-in provider should not close the printer handle that is associated with <i>hPrinter</i>.




## -see-also




<a href="https://docs.microsoft.com/previous-versions/windows/hardware/drivers/ff554375(v=vs.85)">IPrintTicketProvider</a>



<a href="https://docs.microsoft.com/previous-versions/windows/hardware/drivers/ff554354(v=vs.85)">IPrintTicketProvider::BindPrinter</a>
 

 

