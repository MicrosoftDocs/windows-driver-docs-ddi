---
UID: NF:hbaapi.HBA_GetVendorLibraryAttributes
title: HBA_GetVendorLibraryAttributes function (hbaapi.h)
description: The HBA_GetVendorLibraryAttributes routine retrieves the vendor-specific attributes of the fibre channel HBA API library.
old-location: storage\hba_getvendorlibraryattributes.htm
tech.root: storage
ms.assetid: 43c55364-1f73-4413-99fb-27c85600d7a6
ms.date: 03/29/2018
ms.keywords: HBA_GetVendorLibraryAttributes, HBA_GetVendorLibraryAttributes routine [Storage Devices], fibreHBA_rtns_d690dcf4-4ef6-4aea-80dc-846649ed3142.xml, hbaapi/HBA_GetVendorLibraryAttributes, storage.hba_getvendorlibraryattributes
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
-	HBA_GetVendorLibraryAttributes
product:
- Windows
targetos: Windows
req.typenames: 
---

# HBA_GetVendorLibraryAttributes function


## -description


The <b>HBA_GetVendorLibraryAttributes</b> routine retrieves the vendor-specific attributes of the fibre channel HBA API library.


## -parameters




### -param AdapterIndex [in]

Contains an adapter index that identifies which library to query. Each library is associated with one or more HBAs. This routine uses an index to identify the HBA so that the caller does not have to open the adapter to obtain a name or handle. The HBA API library can be associated with more than one HBA, so the same library attributes might be retrieved for different HBAs. The adapter index must be within the range of values returned by <a href="https://msdn.microsoft.com/library/windows/hardware/ff556101">HBA_GetNumberOfAdapters</a>. 


### -param Attributes [out]

Pointer, on return, to a structure of type <a href="https://msdn.microsoft.com/library/windows/hardware/ff556119">HBA_LibraryAttributes</a> that holds the attributes of the library associated with the adapter referenced by <i>AdapterIndex</i>.


## -returns



The <b>HBA_GetVendorLibraryAttributes</b> routine returns a value that indicates the version of the specification with which the library is compliant. A value of 1 indicates version 1 of the specification. A value of 2 indicates version 2 of the specification. All other values are reserved until the future versions of the specification are published.




## -remarks



The <b>HBA_GetVendorLibraryAttributes</b> routine, as defined by the T11 committee's <i>Fibre Channel HBA API</i> specification, retrieves information about a vendor-supplied HBA API library, and the related routine <a href="https://msdn.microsoft.com/library/windows/hardware/ff556115">HBA_GetWrapperLibraryAttributes</a> reports the characteristics of a system-supplied wrapper library that works with the vendor library to provide the fibre channel HBA API. 

In particular, the <b>HBA_GetVendorLibraryAttributes</b> routine allows the caller to determine whether a compatible library is installed.

Microsoft supplies both libraries, so currently they return the same information. 




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff556101">HBA_GetNumberOfAdapters</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff556115">HBA_GetWrapperLibraryAttributes</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff556119">HBA_LibraryAttributes</a>
 

 

