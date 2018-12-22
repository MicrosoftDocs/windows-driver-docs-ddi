---
UID: NF:hbaapi.HBA_GetWrapperLibraryAttributes
title: HBA_GetWrapperLibraryAttributes function
description: The HBA_GetWrapperLibraryAttributes routine retrieves the attributes of the fibre channel HBA API library that are operating system-specific.
old-location: storage\hba_getwrapperlibraryattributes.htm
tech.root: storage
ms.assetid: c40b8f20-65e9-4e43-a402-14bd30f15975
ms.date: 03/29/2018
ms.keywords: HBA_GetWrapperLibraryAttributes, HBA_GetWrapperLibraryAttributes routine [Storage Devices], fibreHBA_rtns_98e62721-8cee-4799-b25f-bf01b52d966c.xml, hbaapi/HBA_GetWrapperLibraryAttributes, storage.hba_getwrapperlibraryattributes
ms.topic: function
req.header: hbaapi.h
req.include-header: Hbaapi.h
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
req.lib: Hbaapi.lib
req.dll: Hbaapi.dll
req.irql: 
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	DllExport
api_location:
-	Hbaapi.dll
api_name:
-	HBA_GetWrapperLibraryAttributes
product:
- Windows
targetos: Windows
req.typenames: 
---

# HBA_GetWrapperLibraryAttributes function


## -description


The <b>HBA_GetWrapperLibraryAttributes</b> routine retrieves the attributes of the fibre channel HBA API library that are operating system-specific. 


## -parameters




### -param Attributes [out]

Pointer, on return, to a structure of type <a href="https://msdn.microsoft.com/library/windows/hardware/ff556119">HBA_LibraryAttributes</a> that holds the attributes of the wrapper library.


## -returns



The <b>HBA_GetWrapperLibraryAttributes</b> routine returns a value that indicates the version of the specification with which the library is compliant. A value of 1 indicates version 1 of the specification. A value of 2 indicates version 2 of the specification. All other values are reserved until the future versions of the specification are published.




## -remarks



The <b>HBA_GetWrapperLibraryAttributes</b> routine, as defined by the T11 committee's <i>Fibre Channel HBA API</i> specification, retrieves information about a system-supplied HBA API library, and the related routine <a href="https://msdn.microsoft.com/library/windows/hardware/ff556112">HBA_GetVendorLibraryAttributes</a> reports the characteristics of a system-supplied wrapper library that works with the vendor library to provide the fibre channel HBA API. 

In particular, the <b>HBA_GetWrapperLibraryAttributes</b> routine allows the caller to determine whether a compatible library is installed. 

Microsoft supplies both libraries, so currently they return the same information. 




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff556112">HBA_GetVendorLibraryAttributes</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff556119">HBA_LibraryAttributes</a>
 

 

