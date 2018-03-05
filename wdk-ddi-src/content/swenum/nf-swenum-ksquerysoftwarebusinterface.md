---
UID: NF:swenum.KsQuerySoftwareBusInterface
title: KsQuerySoftwareBusInterface function
author: windows-driver-content
description: The KsQuerySoftwareBusInterface function creates a buffer from the paged pool and copies the reference string associated with the demand-load bus enumerator object's PDO into the buffer.
old-location: stream\ksquerysoftwarebusinterface.htm
old-project: stream
ms.assetid: 2a4dd5a8-e9cc-4404-8031-5091ff2aa50d
ms.author: windowsdriverdev
ms.date: 2/23/2018
ms.keywords: KsQuerySoftwareBusInterface, KsQuerySoftwareBusInterface function [Streaming Media Devices], ksfunc_58ad39a9-6e7b-416b-9ca6-a5a92bb0a7fc.xml, stream.ksquerysoftwarebusinterface, swenum/KsQuerySoftwareBusInterface
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: swenum.h
req.include-header: Swenum.h
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
req.lib: NtosKrnl.exe
req.dll: 
req.irql: 
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	swenum.h
api_name:
-	KsQuerySoftwareBusInterface
product: Windows
targetos: Windows
req.typenames: STREAM_TIME_REFERENCE, *PSTREAM_TIME_REFERENCE
req.product: Windows 10 or later.
---

# KsQuerySoftwareBusInterface function


## -description


<i>This function is intended for internal use only.</i>

The <b>KsQuerySoftwareBusInterface</b> function creates a buffer from the paged pool and copies the reference string associated with the demand-load bus enumerator object's PDO into the buffer. It is the caller's responsibility to free the buffer using <a href="..\ntddk\nf-ntddk-exfreepool.md">ExFreePool</a>. 


## -syntax


````
NTSTATUS KsQuerySoftwareBusInterface(
  _In_  PDEVICE_OBJECT        PnpDeviceObject,
  _Out_ PBUS_INTERFACE_SWENUM BusInterface
);
````


## -parameters




### -param PnpDeviceObject [in]

Pointer to the demand-load bus enumerator's device object.


### -param BusInterface [out]

Pointer to the demand-load bus enumerator's interface.


## -returns



Returns STATUS_SUCCESS if the request is handled. Otherwise, it returns an appropriate error code.




## -remarks



A minidriver can access this function through the <b>QueryReferenceString</b> member of the BUS_INTERFACE_SWENUM structure.




## -see-also

<a href="..\swenum\nf-swenum-ksreferencesoftwarebusobject.md">KsReferenceSoftwareBusObject</a>



<a href="..\swenum\nf-swenum-ksdereferencesoftwarebusobject.md">KsDereferenceSoftwareBusObject</a>



<a href="..\swenum\ns-swenum-_bus_interface_swenum.md">BUS_INTERFACE_SWENUM</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [stream\stream]:%20KsQuerySoftwareBusInterface function%20 RELEASE:%20(2/23/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

