---
UID: NF:ursdevice.UrsIoResourceListAppendDescriptor
title: UrsIoResourceListAppendDescriptor function
author: windows-driver-content
description: Appends the specified resource descriptor to the specified I/O resource list object that maintains resource descriptors for the host or function role.
old-location: buses\ursioresourcelistappenddescriptor.htm
old-project: usbref
ms.assetid: 80AE8211-EA8F-4967-A496-39053CD578D1
ms.author: windowsdriverdev
ms.date: 4/25/2018
ms.keywords: UrsIoResourceListAppendDescriptor, UrsIoResourceListAppendDescriptor function [Buses], buses.ursioresourcelistappenddescriptor, ursdevice/UrsIoResourceListAppendDescriptor
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: ursdevice.h
req.include-header: Urscx.h
req.target-type: Windows
req.target-min-winverclnt: Windows 10
req.target-min-winversvr: Windows Server 2016
req.kmdf-ver: 1.15
req.umdf-ver: 
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Urscxstub.lib
req.dll: 
req.irql: PASSIVE_LEVEL
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	LibDef
api_location:
-	Urscxstub.lib
-	Urscxstub.dll
api_name:
-	UrsIoResourceListAppendDescriptor
product:
- Windows
targetos: Windows
req.typenames: 
---

# UrsIoResourceListAppendDescriptor function


## -description


Appends the specified resource descriptor to the specified I/O resource list object that maintains resource descriptors for the
    host or function role.


## -parameters




### -param IoResourceList [in]

 A role's I/O resource list object to which the resource descriptor is appended. This object is allocated by the framework and passed to the client driver when the framework invokes the driver's <a href="https://msdn.microsoft.com/library/windows/hardware/mt595921">EVT_URS_DEVICE_FILTER_RESOURCE_REQUIREMENTS</a> implementation.


### -param Descriptor [in]

A pointer to  IO_RESOURCE_DESCRIPTOR that contains the resource descriptor for the role.


## -returns



The method returns STATUS_SUCCESS if the operation succeeds. Otherwise, this method might return an appropriate <a href="https://msdn.microsoft.com/7792201b-63bb-4db5-803d-2af02893d505">NTSTATUS</a> error code. 




## -remarks



After the client driver calls <a href="https://msdn.microsoft.com/library/windows/hardware/mt628012">UrsDeviceInitialize</a>, the framework allocates memory for the <i>resource requirements list</i>. When the USB dual-role class extension  invokes the client driver's implementation of <a href="https://msdn.microsoft.com/library/windows/hardware/mt595921">EVT_URS_DEVICE_FILTER_RESOURCE_REQUIREMENTS</a>, it passes a WDFIORESREQLIST handle to that requirements list along with URSIORESLIST handles for host and function role <i>resource lists</i>. In the implementation, the client driver is expected to enumerate through the requirements list and add the resource descriptor (if it wants to use that resource)  to the resource list for each role.

To add a resource descriptors for a role, the driver calls <b>UrsIoResourceListAppendDescriptor</b> and specifies the descriptor and the resource list to which the resource must be added. 

For a code example, see <a href="https://msdn.microsoft.com/library/windows/hardware/mt595921">EVT_URS_DEVICE_FILTER_RESOURCE_REQUIREMENTS</a>.

For more information about resource requirements lists, see <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/hardware-resources-for-kmdf-drivers">Handling Hardware Resources</a>.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/mt595921">EVT_URS_DEVICE_FILTER_RESOURCE_REQUIREMENTS</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/mt628012">UrsDeviceInitialize</a>
 

 

