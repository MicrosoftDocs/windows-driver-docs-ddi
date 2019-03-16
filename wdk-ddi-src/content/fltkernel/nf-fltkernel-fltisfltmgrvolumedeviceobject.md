---
UID: NF:fltkernel.FltIsFltMgrVolumeDeviceObject
title: FltIsFltMgrVolumeDeviceObject function (fltkernel.h)
description: The FltIsFltMgrVolumeDeviceObject routine determines whether the given device object belongs to filter manager and if the device object is a volume device object.
old-location: ifsk\fltisfltmgrvolumedeviceobject.htm
tech.root: ifsk
ms.assetid: c4165eab-c62e-436d-b4d4-a1f72ee9c1bd
ms.date: 04/16/2018
ms.keywords: FltApiRef_e_to_o_95cc07b6-722c-4d2a-bec1-57fff9e2c6e3.xml, FltIsFltMgrVolumeDeviceObject, FltIsFltMgrVolumeDeviceObject routine [Installable File System Drivers], fltkernel/FltIsFltMgrVolumeDeviceObject, ifsk.fltisfltmgrvolumedeviceobject
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
req.irql: "<= APC_LEVEL"
topic_type:
- APIRef
- kbSyntax
api_type:
- DllExport
api_location:
- fltmgr.sys
api_name:
- FltIsFltMgrVolumeDeviceObject
product:
- Windows
targetos: Windows
req.typenames: 
---

# FltIsFltMgrVolumeDeviceObject function


## -description


The <b>FltIsFltMgrVolumeDeviceObject</b> routine determines whether the given device object belongs to filter manager and if the device object is a volume device object.


## -parameters




### -param DeviceObject [in]

A pointer to the device object (<a href="https://msdn.microsoft.com/library/windows/hardware/ff543147">DEVICE_OBJECT</a>) to test.


## -returns



The <b>FltIsFltMgrVolumeDeviceObject</b> routine returns <b>TRUE</b> if <i>DeviceObject</i> is a filter manager volume device object; otherwise, it returns <b>FALSE</b>.




## -remarks



None




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff543147">DEVICE_OBJECT</a>
 

 

