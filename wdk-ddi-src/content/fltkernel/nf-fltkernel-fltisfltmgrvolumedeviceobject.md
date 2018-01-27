---
UID: NF:fltkernel.FltIsFltMgrVolumeDeviceObject
title: FltIsFltMgrVolumeDeviceObject function
author: windows-driver-content
description: The FltIsFltMgrVolumeDeviceObject routine determines whether the given device object belongs to filter manager and if the device object is a volume device object.
old-location: ifsk\fltisfltmgrvolumedeviceobject.htm
old-project: ifsk
ms.assetid: c4165eab-c62e-436d-b4d4-a1f72ee9c1bd
ms.author: windowsdriverdev
ms.date: 1/9/2018
ms.keywords: FltIsFltMgrVolumeDeviceObject, FltIsFltMgrVolumeDeviceObject routine [Installable File System Drivers], ifsk.fltisfltmgrvolumedeviceobject, fltkernel/FltIsFltMgrVolumeDeviceObject, FltApiRef_e_to_o_95cc07b6-722c-4d2a-bec1-57fff9e2c6e3.xml
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: fltkernel.h
req.include-header: Fltkernel.h
req.target-type: Universal
req.target-min-winverclnt: Available in Vista or later versions of the Windows operating system.
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
req.lib: FltMgr.lib
req.dll: Fltmgr.sys
req.irql: <= APC_LEVEL
topictype: 
-	APIRef
-	kbSyntax
apitype: 
-	DllExport
apilocation: 
-	fltmgr.sys
apiname: 
-	FltIsFltMgrVolumeDeviceObject
product: Windows
targetos: Windows
req.typenames: EXpsFontRestriction
---

# FltIsFltMgrVolumeDeviceObject function


## -description


The <b>FltIsFltMgrVolumeDeviceObject</b> routine determines whether the given device object belongs to filter manager and if the device object is a volume device object.


## -syntax


````
BOOLEAN FltIsFltMgrVolumeDeviceObject(
  _In_ PDEVICE_OBJECT DeviceObject
);
````


## -parameters




### -param DeviceObject [in]

A pointer to the device object (<a href="..\wdm\ns-wdm-_device_object.md">DEVICE_OBJECT</a>) to test.


## -returns


The <b>FltIsFltMgrVolumeDeviceObject</b> routine returns <b>TRUE</b> if <i>DeviceObject</i> is a filter manager volume device object; otherwise, it returns <b>FALSE</b>.



## -remarks


None



## -see-also

<a href="..\wdm\ns-wdm-_device_object.md">DEVICE_OBJECT</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [ifsk\ifsk]:%20FltIsFltMgrVolumeDeviceObject routine%20 RELEASE:%20(1/9/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

