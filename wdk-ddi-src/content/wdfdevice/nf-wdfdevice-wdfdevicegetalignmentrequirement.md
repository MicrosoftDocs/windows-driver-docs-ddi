---
UID: NF:wdfdevice.WdfDeviceGetAlignmentRequirement
title: WdfDeviceGetAlignmentRequirement function
author: windows-driver-content
description: The WdfDeviceGetAlignmentRequirement method retrieves a device's address alignment requirement for memory transfer operations.
old-location: wdf\wdfdevicegetalignmentrequirement.htm
old-project: wdf
ms.assetid: 531f5e99-0e04-47dd-86bb-c35aa549c63a
ms.author: windowsdriverdev
ms.date: 2/20/2018
ms.keywords: WdfDeviceGetAlignmentRequirement method, WdfDeviceGetAlignmentRequirement, kmdf.wdfdevicegetalignmentrequirement, wdfdevice/WdfDeviceGetAlignmentRequirement, DFDeviceObjectGeneralRef_c7135427-9887-44e5-8380-28ebef4174a9.xml, wdf.wdfdevicegetalignmentrequirement
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: wdfdevice.h
req.include-header: Wdf.h
req.target-type: Universal
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 1.0
req.umdf-ver: 
req.ddi-compliance: DriverCreate, KmdfIrql, KmdfIrql2
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Wdf01000.sys (see Framework Library Versioning.)
req.dll: 
req.irql: "<= DISPATCH_LEVEL"
topictype:
-	APIRef
-	kbSyntax
apitype:
-	LibDef
apilocation:
-	Wdf01000.sys
-	Wdf01000.sys.dll
apiname:
-	WdfDeviceGetAlignmentRequirement
product: Windows
targetos: Windows
req.typenames: WDF_STATE_NOTIFICATION_TYPE
req.product: Windows 10 or later.
---

# WdfDeviceGetAlignmentRequirement function


## -description


<p class="CCE_Message">[Applies to KMDF only]

The <b>WdfDeviceGetAlignmentRequirement</b> method retrieves a device's address alignment requirement for memory transfer operations.


## -syntax


````
ULONG WdfDeviceGetAlignmentRequirement(
  _In_ WDFDEVICE Device
);
````


## -parameters




### -param Device [in]

A handle to a framework device object.


## -returns



<b>WdfDeviceGetAlignmentRequirement</b> returns the device's current alignment requirement. This value is one of the FILE_<i>XXXX</i>_ALIGNMENT constants that are defined in <i>wdm.h</i>.

A bug check occurs if the driver supplies an invalid object handle.




## -see-also

<a href="..\wdfdevice\nf-wdfdevice-wdfdevicesetalignmentrequirement.md">WdfDeviceSetAlignmentRequirement</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [wdf\wdf]:%20WdfDeviceGetAlignmentRequirement method%20 RELEASE:%20(2/20/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

