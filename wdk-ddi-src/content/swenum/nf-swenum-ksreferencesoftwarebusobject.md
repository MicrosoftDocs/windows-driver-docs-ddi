---
UID: NF:swenum.KsReferenceSoftwareBusObject
title: KsReferenceSoftwareBusObject function
author: windows-driver-content
description: The KsReferenceSoftwareBusObject function increments the reference count of the demand-load bus enumerator object's PDO.
old-location: stream\ksreferencesoftwarebusobject.htm
old-project: stream
ms.assetid: 56c7ce80-36da-4991-a640-f87b712f683e
ms.author: windowsdriverdev
ms.date: 2/23/2018
ms.keywords: KsReferenceSoftwareBusObject, KsReferenceSoftwareBusObject function [Streaming Media Devices], ksfunc_38a63d2d-e988-474d-890b-dd9a2aeeaff4.xml, stream.ksreferencesoftwarebusobject, swenum/KsReferenceSoftwareBusObject
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: swenum.h
req.include-header: Swenum.h
req.target-type: Universal
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
req.lib: Ks.lib
req.dll: 
req.irql: 
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	LibDef
api_location:
-	Ks.lib
-	Ks.dll
api_name:
-	KsReferenceSoftwareBusObject
product: Windows
targetos: Windows
req.typenames: STREAM_TIME_REFERENCE, *PSTREAM_TIME_REFERENCE
req.product: Windows 10 or later.
---

# KsReferenceSoftwareBusObject function


## -description


<i>This function is intended for internal use only.</i>

The <b>KsReferenceSoftwareBusObject</b> function increments the reference count of the demand-load bus enumerator object's PDO. 


## -syntax


````
NTSTATUS KsReferenceSoftwareBusObject(
  _In_ KSDEVICE_HEADER Header
);
````


## -parameters




### -param Header [in]

Pointer to the device header (extension) of the demand-load bus enumerator.


## -returns



Returns STATUS_SUCCESS if the request is handled. Otherwise, it returns an appropriate error code.




## -remarks



A minidriver can access this function through the <b>ReferenceDeviceObject</b> member of the BUS_INTERFACE_SWENUM structure.

The device object remains active and enumerated until the reference count returns to 0.




## -see-also

<a href="..\swenum\nf-swenum-ksquerysoftwarebusinterface.md">KsQuerySoftwareBusInterface</a>



<a href="..\swenum\nf-swenum-ksdereferencesoftwarebusobject.md">KsDereferenceSoftwareBusObject</a>



<a href="..\swenum\ns-swenum-_bus_interface_swenum.md">BUS_INTERFACE_SWENUM</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [stream\stream]:%20KsReferenceSoftwareBusObject function%20 RELEASE:%20(2/23/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

