---
UID: NF:hbaapi.HBA_GetVendorLibraryAttributes
title: HBA_GetVendorLibraryAttributes function
author: windows-driver-content
description: The HBA_GetVendorLibraryAttributes routine retrieves the vendor-specific attributes of the fibre channel HBA API library.
old-location: storage\hba_getvendorlibraryattributes.htm
old-project: storage
ms.assetid: 43c55364-1f73-4413-99fb-27c85600d7a6
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: storage.hba_getvendorlibraryattributes, hbaapi/HBA_GetVendorLibraryAttributes, HBA_GetVendorLibraryAttributes, HBA_GetVendorLibraryAttributes routine [Storage Devices], fibreHBA_rtns_d690dcf4-4ef6-4aea-80dc-846649ed3142.xml
ms.prod: windows-hardware
ms.technology: windows-devices
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	DllExport
apilocation:
-	Hbaapi.dll
apiname:
-	HBA_GetVendorLibraryAttributes
product: Windows
targetos: Windows
req.typenames: HBA_WWNTYPE
---

# HBA_GetVendorLibraryAttributes function


## -description


The <b>HBA_GetVendorLibraryAttributes</b> routine retrieves the vendor-specific attributes of the fibre channel HBA API library.


## -syntax


````
HBA_UINT32 HBA_API HBA_GetVendorLibraryAttributes(
  _In_  HBA_UINT32            AdapterIndex,
  _Out_ HBA_LIBRARYATTRIBUTES *Attributes
);
````


## -parameters




### -param AdapterIndex [in]

Contains an adapter index that identifies which library to query. Each library is associated with one or more HBAs. This routine uses an index to identify the HBA so that the caller does not have to open the adapter to obtain a name or handle. The HBA API library can be associated with more than one HBA, so the same library attributes might be retrieved for different HBAs. The adapter index must be within the range of values returned by <a href="..\hbaapi\nf-hbaapi-hba_getnumberofadapters.md">HBA_GetNumberOfAdapters</a>. 


### -param Attributes [out]

Pointer, on return, to a structure of type <a href="..\hbaapi\ns-hbaapi-hba_libraryattributes.md">HBA_LibraryAttributes</a> that holds the attributes of the library associated with the adapter referenced by <i>AdapterIndex</i>.


## -returns



The <b>HBA_GetVendorLibraryAttributes</b> routine returns a value that indicates the version of the specification with which the library is compliant. A value of 1 indicates version 1 of the specification. A value of 2 indicates version 2 of the specification. All other values are reserved until the future versions of the specification are published.




## -remarks



The <b>HBA_GetVendorLibraryAttributes</b> routine, as defined by the T11 committee's <i>Fibre Channel HBA API</i> specification, retrieves information about a vendor-supplied HBA API library, and the related routine <a href="..\hbaapi\nf-hbaapi-hba_getwrapperlibraryattributes.md">HBA_GetWrapperLibraryAttributes</a> reports the characteristics of a system-supplied wrapper library that works with the vendor library to provide the fibre channel HBA API. 

In particular, the <b>HBA_GetVendorLibraryAttributes</b> routine allows the caller to determine whether a compatible library is installed.

Microsoft supplies both libraries, so currently they return the same information. 




## -see-also

<a href="..\hbaapi\nf-hbaapi-hba_getwrapperlibraryattributes.md">HBA_GetWrapperLibraryAttributes</a>



<a href="..\hbaapi\nf-hbaapi-hba_getnumberofadapters.md">HBA_GetNumberOfAdapters</a>



<a href="..\hbaapi\ns-hbaapi-hba_libraryattributes.md">HBA_LibraryAttributes</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20HBA_GetVendorLibraryAttributes routine%20 RELEASE:%20(2/16/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

