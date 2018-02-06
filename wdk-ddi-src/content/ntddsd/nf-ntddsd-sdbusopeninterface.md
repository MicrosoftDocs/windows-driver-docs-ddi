---
UID: NF:ntddsd.SdBusOpenInterface
title: SdBusOpenInterface function
author: windows-driver-content
description: The SdBusOpenInterface routine obtains an interface from the Secure Digital (SD) bus driver.
old-location: sd\sdbusopeninterface.htm
old-project: SD
ms.assetid: a788cd28-81a7-4b8c-b9c5-76dd2b1cd0f3
ms.author: windowsdriverdev
ms.date: 12/18/2017
ms.keywords: ntddsd/SdBusOpenInterface, sd-rtns_44707c61-dadc-4151-b06a-8df3def56ab9.xml, SD.sdbusopeninterface, SdBusOpenInterface function [Buses], SdBusOpenInterface
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: ntddsd.h
req.include-header: Ntddsd.h
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
req.irql: "< DISPATCH_LEVEL"
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	ntddsd.h
apiname:
-	SdBusOpenInterface
product: Windows
targetos: Windows
req.typenames: SD_REQUEST_FUNCTION
---

# SdBusOpenInterface function


## -description


The <b>SdBusOpenInterface</b> routine obtains an interface from the Secure Digital (SD) bus driver.


## -syntax


````
NTSTATUS SdBusOpenInterface(
  _In_  PDEVICE_OBJECT            Pdo,
  _Out_ PSDBUS_INTERFACE_STANDARD InterfaceStandard,
  _In_  USHORT                    Size,
  _In_  USHORT                    Version
);
````


## -parameters




### -param Pdo [in]

Pointer to the physical device object that the SD bus driver created for the SD device that the device driver manages. The system passes this pointer to the device driver when it calls the driver's <a href="https://msdn.microsoft.com/library/windows/hardware/ff540521">AddDevice</a> routine.


### -param InterfaceStandard [out]

Contains, on input, a pointer to a structure of type <a href="https://msdn.microsoft.com/92b8762d-8af3-493c-aa1d-bc245b0cbd83">SDBUS_INTERFACE_STANDARD</a> supplied by the caller. On output, this structure holds pointers to the SD bus interface routines. This structure also contains some context information in its <b>Context</b> member that the caller should pass in every time it calls an interface routine.


### -param Size [in]

Contains the size, in bytes, of the structure pointed to by <i>InterfaceStandard</i>.


### -param Version [in]

Must be set to SDBUS_INTERFACE_VERSION.


## -returns


Returns STATUS_SUCCESS if the operation succeeds, or the appropriate error code if the operation fails. 



## -remarks


An SD card driver should call this routine from its <a href="https://msdn.microsoft.com/library/windows/hardware/ff540521">AddDevice</a> routine.

SD card drivers must call this routine to establish communication with the bus driver. On successful completion of this call, the <b>Context</b> member of the structure pointed to by <i>InterfaceStandard</i> will contain a handle that the driver must pass in when calling methods that belong to the retrieved interface. 



## -see-also

<a href="https://msdn.microsoft.com/92b8762d-8af3-493c-aa1d-bc245b0cbd83">SDBUS_INTERFACE_STANDARD</a>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff540521">AddDevice</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [SD\buses]:%20SdBusOpenInterface function%20 RELEASE:%20(12/18/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

